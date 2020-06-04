# Testing With Jest

## First Some Terminology

The following definition list is from https://martinfowler.com/articles/mocksArentStubs.html by Martin Fowler

- **Dummy** objects are passed around but never actually used. Usually they are just
  used to fill parameter lists.

- **Fake** objects actually have working implementations, but usually take some
  shortcut which makes them not suitable for production (an in memory
  database is a good example).

- **Stubs** provide canned answers to calls made during the test, usually not responding at all to anything outside what's programmed in for the test.

- **Spies** are stubs that also record some information based on how they were called. One form of this might be an email service that records how many messages it was sent.

- **Mocks** are what we are talking about here: objects pre-programmed with expectations which form a specification of the calls they are expected to receive.

## Anatomy of a Test
```js
describe("Tests for Math Suite", ()=> {
  
  test("addition works", ()=> {
    expect(2 + 2).toBe(4);
  });
  
  test("division works, ()=> {
    expect(12/4).toBe(3);
  });
  
});
```
Let's break this down:

`describe` is used to wrap a group of tests that are related in some way.  The first argument is a string describing the test group.  The second argument is the function execute the group of tests in.  In this case all these tests are for basic math operations.  `describe` *must* contain at least one test or the suite will fail.

`test` is used to initiate a test.  The first argument describes the test.  The second argument is a function that fires the test.

`expect` is used to match its statement `2 + 2` to the expected output `4`;

`toBe` is a matcher.  There are a bunch of matchers in Jest.  `toBe` is probably the most frequently used.


## Utils

Within our project we have `js/utils.js`. It's likely that this
could be broken out into more files under a
`utils` directory. This way we can group math/string/currency
utils etc. _Each and every_ util needs a unit test. If you cannot
reason about writing a unit tests for a util, then there is a chance the
util is written incorrectly. Since all utils for now are in
`utils.js` the test file is `utils.test.js`

```js
test('AddClass adds the given class', ()=> {

  document.body.innerHTML = `<div id="myDiv"></div>`;

  const div = document.getElementById('myDiv');

  addClass('cool-class', div);

  expect(div.classList.contains('cool-class')).toBe(true);

});
```

## Services

## DOM Manipulation
