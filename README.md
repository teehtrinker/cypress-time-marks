# cypress-time-marks ![cypress version](https://img.shields.io/badge/cypress-11.2.0-brightgreen)

> Custom Cypress commands to measure elapsed time

```js
cy.timeMark('start').wait(1500).timeSince('start').wait(500).timeSince('start')
```

![Time marks](./images/marks.png)

See [spec.cy.js](./cypress/e2e/spec.cy.js)

## Install

Add this plugin as a dev dependency

```
# if using NPM
$ npm i -D cypress-time-marks
# if using Yarn
$ yarn add -D cypress-time-marks
```

Import this plugin from the spec file or from the support file

```js
// cypress/e2e/spec.cy.js or cypress/support/e2e.js
import 'cypress-time-marks'
```

This should give you two new custom commands `cy.timeMark(name)` and `cy.timeSince(name)`.

## Options

### labels

You can log a label when using `cy.timeSince(name, label)`

```js
cy.timeMark('start')
  .wait(1500)
  .timeSince('start', 'initial wait')
  .wait(500)
  .timeSince('start', 'final load')
```

![Time marks with labels](./images/labels.png)

### time limit warning

You can pass a time limit after the mark name to warn if the elapsed time is longer than the limit. It won't fail the test, but it will change the icon to warn you.

```js
cy.timeMark('start')
  .wait(100)
  .timeSince('start', 'under time limit', 200)
  .wait(500)
  .timeSince('start', 'over time limit', 200)
  .timeSince('start', 200)
```

![Time limit warnings](./images/time-limit.png)

## See also

- [cypress-timestamps](https://github.com/bahmutov/cypress-timestamps) plugin

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
[open issue](https://github.com/bahmutov/cypress-time-marks/issues) on Github
