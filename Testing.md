<h1>Testing With Jest</h1>

<section>
  <h2>First Some Terminology:</h2>
  <p>
    The following definition list is from
    <cite>
      https://martinfowler.com/articles/mocksArentStubs.html
    </cite>
    <sup>
      by Martin Fowler
    </sup>
  </p>
  <dl>
    <dt>
      Dummy
    </dt>
    <dd>
      objects are passed around but never actually used. Usually they are just
      used to fill parameter lists.
    </dd>
    <dt>
      Fake
    </dt>
    <dd>
      objects actually have working implementations, but usually take some
      shortcut which makes them not suitable for production (an in memory
      database is a good example).
    </dd>
    <dt>
      Stubs
    </dt>
    <dd>
      provide canned answers to calls made during the test, usually not
      responding at all to anything outside what's programmed in for the test.
    </dd>
    <dt>
      Spies
    </dt>
    <dd>
      are stubs that also record some information based on how they were called.
      One form of this might be an email service that records how many messages
      it was sent.
    </dd>
    <dt>
      Mocks
    </dt>
    <dd>
      are what we are talking about here: objects pre-programmed with
      expectations which form a specification of the calls they are expected to
      receive.
    </dd>
  </dl>
</section>
<section>
  <h2>Utils</h2>
  <p>
    Within our project we have <code>js/utils.js</code>. It's likely that this
    could be broken out into more files under a
    <strong>utils</strong> directory. This way we can group math/string/currency
    utils etc. <i>Each and every</i> util needs a unit test. If you cannot
    reason about writing a unit tests for a util, then there is a chance the
    util is written incorrectly. Since all utils for now are in
    <code>utils.js</code>, the test file is <code>utils.test.js</code>
  </p>
  <p>
      Utils should accept input and produce a certain output or mutation.  Therefore the unit tests written should be fairly straight forward.
      <pre>
          <code>
              text('AddClass adds the given class', ()=> {
                document.body.innerHTML = `<div id="myDiv"></div>`
              });
              const div = document.getElementById('myDiv');
              addClass('cool-class', div);
              expect(div.classList.contains('cool-class')).toBe(true);
          </code>
      </pre>
  </p>
</section>
<section>
  <h2>Services</h2>
  <p></p>
</section>
<section>
  <h2>DOM Logic</h2>
  <p></p>
</section>
