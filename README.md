<h1 align="center">Welcome to react-csp 👋</h1>
<p>
  <img src="https://img.shields.io/badge/version-1.0.0-blue.svg?cacheSeconds=2592000" />
  <a href="https://github.com/YIZHUANG/react-csp">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" target="_blank" />
  </a>
</p>

> A npm package/plugin that generates Content Security Policy for create-react-app without eject or rewired.

### 🏠 [Homepage](https://github.com/YIZHUANG/react-csp)

## Install

```sh
npm install react-csp --save-dev
Or
npm install react-csp -g
```

## Prerequisite

1. Make sure you have nodejs 8+ installed.
2. Your react is generated with create-react-app
3. index.html should be located in `public/index.html`

## Usage

Create a file named either csp.json or csp.js in the root directory of your project.

React folder structure:

```
root:
  csp.js
  .gitignore
  package.json
  public/index.html
  src/index.js
  rest of the files...
```

The content in the file should be similar to the following:

```
module.exports = {
  dev: {
  "default-src": ["'self'"],
  "style-src": [
    "'self'",
    "https://*.google.com",
  ]
  },
  prod: {
  "default-src": "'self'",  // can be either a string or an array.
  "style-src": [
    "'self'",
    "https://*.facebook.com",
    "connect-src": [
      "'self'",
      "https://mybackend.com"
    ]
  ]
  }
}

```

For more config, please refer to [MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP).

For dev environment:

Run `react-csp dev` in the command line.

For prod environment:
Run `react-csp prod` in the command line.

The recommented approach is to put the following in your package.json:

```
{
  "scripts": {
    "build": "react-csp dev && react-scripts build"
  }
}
```

## Run tests

```sh
npm run test
```

## Author

👤 **YIZHUANG**

- Github: [@YIZHUANG](https://github.com/YIZHUANG)

## Show your support

Give a ⭐️ if this project helped you!

---

_This Project including README, LICENSE, package.json, contributing etc was generated with ❤️ by [git-repo-npm-bootster](https://github.com/YIZHUANG/git-repo-npm-bootster)_