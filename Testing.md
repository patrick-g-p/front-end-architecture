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
    <p>Within our project we have `js/utils.js`. It's likely that this could
        be broken out into more files under a `utils` directory. This way we can group
        math/string/currency utils etc. _Each and every_ util needs a unit test. If you
        cannot reason about writing a unit tests for a util, then the util is probably
        poorly written. Since all utils for now are in `utils.js`, the test file is
        `utils.test.js`</p>
</section> 
<section>
    <h2>Services</h2>
    <p></p>
</section> 
<section>
    <h2>DOM Logic</h2>
    <p></p>
</section> 
