# cypress-cdp [![ci](https://github.com/bahmutov/cypress-cdp/actions/workflows/ci.yml/badge.svg?branch=main&event=push)](https://github.com/bahmutov/cypress-cdp/actions/workflows/ci.yml) ![cypress version](https://img.shields.io/badge/cypress-9.5.4-brightgreen)

> A custom Cypress command to wrap the remote debugger protocol low level command

Read the blog post [When Can The Test Click](https://glebbahmutov.com/blog/when-can-the-test-click/)

## Install

## API

### CDP

#### CDP example 1

```js
const selector = 'button#one'
cy.CDP('Runtime.evaluate', {
  expression: 'frames[0].document.querySelector("' + selector + '")',
}).should((v) => {
  expect(v.result).to.have.property('objectId')
})
```

### hasEventListeners

#### hasEventListeners example

```js
// any event listeners are attached
cy.hasEventListeners('button#one')
// "click" event listeners are attached
cy.hasEventListeners('button#one', { type: 'click' })
```

## Small print

Author: Gleb Bahmutov &lt;gleb.bahmutov@gmail.com&gt; &copy; 2022

- [@bahmutov](https://twitter.com/bahmutov)
- [glebbahmutov.com](https://glebbahmutov.com)
- [blog](https://glebbahmutov.com/blog)
- [videos](https://www.youtube.com/glebbahmutov)
- [presentations](https://slides.com/bahmutov)
- [cypress.tips](https://cypress.tips)
- [Cypress Tips & Tricks Newsletter](https://cypresstips.substack.com/)
- [my Cypress courses](https://cypress.tips/courses)

License: MIT - do anything with the code, but don't blame me if it does not work.

Support: if you find any problems with this module, email / tweet /
[open issue](https://github.com/bahmutov/cypress-cdp/issues) on Github

## MIT License

Copyright (c) 2022 Gleb Bahmutov &lt;gleb.bahmutov@gmail.com&gt;

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the "Software"), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.
