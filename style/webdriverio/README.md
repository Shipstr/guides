WebDriverIO
===========

* Name files descriptively by what they test. Try to group files with other similar files that are already there.
* Prefer expect-style asserts over should. Good: `expect(foo).to.eql('bar')` Bad: `foo.should.eql('bar')`
* Avoid testing against full URLs containing "localhost:3000". Good: `expect(browser.getUrl).to match('/some/path')` Bad: `expect(browser.getUrl).to match('http://localhost:3000/some/path')`
