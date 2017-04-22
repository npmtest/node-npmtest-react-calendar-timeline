# npmtest-react-calendar-timeline

#### basic test coverage for  [react-calendar-timeline (v0.11.1)](https://github.com/namespace-ee/react-calendar-timeline)  [![npm package](https://img.shields.io/npm/v/npmtest-react-calendar-timeline.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-react-calendar-timeline) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-react-calendar-timeline.svg)](https://travis-ci.org/npmtest/node-npmtest-react-calendar-timeline)

#### react calendar timeline

[![NPM](https://nodei.co/npm/react-calendar-timeline.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/react-calendar-timeline)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-react-calendar-timeline/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-react-calendar-timeline/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-react-calendar-timeline/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-react-calendar-timeline/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-react-calendar-timeline/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-react-calendar-timeline/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-react-calendar-timeline/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-react-calendar-timeline/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-react-calendar-timeline/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-react-calendar-timeline/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-react-calendar-timeline/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-react-calendar-timeline/build/test-report.html](https://npmtest.github.io/node-npmtest-react-calendar-timeline/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-react-calendar-timeline/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-react-calendar-timeline/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-react-calendar-timeline/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-react-calendar-timeline/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-react-calendar-timeline/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-react-calendar-timeline/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-react-calendar-timeline/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-react-calendar-timeline/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "react-calendar-timeline",
    "version": "0.11.1",
    "description": "react calendar timeline",
    "main": "modules/index.js",
    "scripts": {
        "clean": "rimraf -rf ./build",
        "watch": "npm run clean && node scripts/watch.js",
        "build": "npm run clean && npm run build:dev && npm run build:prod",
        "build:dev": "echo 'DEV - BUILD' && webpack --config webpack.config.js",
        "build:prod": "echo 'PROD - BUILD' && webpack --config webpack.config.prod.js",
        "release": "npm run build && babel src --out-dir build && cp README.md build/ && node scripts/release.js",
        "module": "./node_modules/.bin/babel src --out-dir modules && sass src/lib/Timeline.scss:modules/lib/Timeline.css && sed -i '.bak' 's/Timeline\\.scss/Timeline\\.css/g' modules/lib/Timeline.js && rm modules/lib/Timeline.js.bak",
        "lint": "eslint --ext .js,.jsx src",
        "lintfix": "eslint --ext .js,.jsx src --fix",
        "upgrade:patch": "npm version patch",
        "preversion": "npm run module && npm run lint",
        "postversion": "git push origin 'git rev-parse --abbrev-ref HEAD' && git push origin 'git describe'",
        "npm:publish:next": "npm run release && cd build && npm publish --tag next",
        "npm:publish:latest": "npm run release && cd build && npm publish",
        "info": "npm info react-calendar-timeline",
        "start": "./node_modules/.bin/webpack-dev-server --inline --hot --host 0.0.0.0"
    },
    "homepage": "https://github.com/namespace-ee/react-calendar-timeline",
    "repository": {
        "type": "git",
        "url": "https://github.com/namespace-ee/react-calendar-timeline.git"
    },
    "author": "Marius Andra <marius.andra@gmail.com>",
    "contributors": [
        "Stanisław Chmiela <sjchmiela@gmail.com>"
    ],
    "license": "MIT",
    "keywords": [
        "react",
        "reactjs",
        "react-component",
        "timeline"
    ],
    "standard": {
        "parser": "babel-eslint"
    },
    "dependencies": {
        "interact.js": "^1.2.6",
        "react-pure-render": "^1.0.2"
    },
    "peerDependencies": {
        "interact.js": "*",
        "moment": "*",
        "react": "^0.14.8 || ^15.0.1",
        "react-dom": "^0.14.8 || ^15.0.1"
    },
    "devDependencies": {
        "babel-cli": "^6.7.5",
        "babel-core": "~6.18.2",
        "babel-eslint": "^7.1.1",
        "babel-loader": "~6.2.4",
        "babel-plugin-add-module-exports": "^0.2.1",
        "babel-preset-es2015": "^6.6.0",
        "babel-preset-react": "^6.5.0",
        "babel-preset-stage-0": "^6.5.0",
        "css-loader": "~0.26.0",
        "es5-shim": "~4.5.9",
        "eslint": "^3.10.2",
        "eslint-config-standard": "^6.2.1",
        "eslint-plugin-promise": "^3.4.0",
        "eslint-plugin-react": "^6.7.1",
        "eslint-plugin-standard": "^2.0.1",
        "extract-text-webpack-plugin": "^1.0.1",
        "jasmine": "~2.5.2",
        "jasmine-core": "~2.5.2",
        "karma": "~1.3.0",
        "karma-jasmine": "~1.0.2",
        "karma-phantomjs-launcher": "~1.0.2",
        "karma-sourcemap-loader": "~0.3.7",
        "karma-webpack": "~1.8.0",
        "moment": "^2.11.1",
        "node-sass": "^3.4.2",
        "react": "^15.0.1",
        "react-addons-perf": "^15.0.1",
        "react-dom": "^15.0.1",
        "react-hot-loader": "^3.0.0-beta.6",
        "rimraf": "^2.5.0",
        "sass-loader": "~4.0.2",
        "style-loader": "~0.13.0",
        "webpack": "~1.13.3",
        "webpack-dev-server": "~1.16.2"
    },
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
