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
