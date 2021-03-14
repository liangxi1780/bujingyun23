This project was bootstrapped with [Create React App](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f54465a96299ef38079519a6db696a1ab86 

Below you will find some information on how to perform common tasks. 
You can find the most recent version of this guide [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f54175dcf4022272d46432bc52032c162a3807dc3262eae80f226621247fbae6fabda6276f79d243306c600be681cc8e090bafa404158b7b22dbf81edff54aaf826 

## Table of Contents

- [Updating to New Releases](#updating-to-new-releases)
- [Sending Feedback](#sending-feedback)
- [Folder Structure](#folder-structure)
- [Available Scripts](#available-scripts)
  - [npm start](#npm-start)
  - [npm test](#npm-test)
  - [npm run build](#npm-run-build)
  - [npm run eject](#npm-run-eject)
- [Supported Browsers](#supported-browsers)
- [Supported Language Features and Polyfills](#supported-language-features-and-polyfills)
- [Syntax Highlighting in the Editor](#syntax-highlighting-in-the-editor)
- [Displaying Lint Output in the Editor](#displaying-lint-output-in-the-editor)
- [Debugging in the Editor](#debugging-in-the-editor)
- [Formatting Code Automatically](#formatting-code-automatically)
- [Changing the Page ` `](#changing-the-page-title)
- [Installing a Dependency](#installing-a-dependency)
- [Importing a Component](#importing-a-component)
- [Code Splitting](#code-splitting)
- [Adding a Stylesheet](#adding-a-stylesheet)
- [Post-Processing CSS](#post-processing-css)
- [Adding a CSS Preprocessor (Sass, Less etc.)](#adding-a-css-preprocessor-sass-less-etc)
- [Adding Images, Fonts, and Files](#adding-images-fonts-and-files)
- [Using the `public` Folder](#using-the-public-folder)
  - [Changing the HTML](#changing-the-html)
  - [Adding Assets Outside of the Module System](#adding-assets-outside-of-the-module-system)
  - [When to Use the `public` Folder](#when-to-use-the-public-folder)
- [Using Global Variables](#using-global-variables)
- [Adding Bootstrap](#adding-bootstrap)
  - [Using a Custom Theme](#using-a-custom-theme)
- [Adding Flow](#adding-flow)
- [Adding a Router](#adding-a-router)
- [Adding Custom Environment Variables](#adding-custom-environment-variables)
  - [Referencing Environment Variables in the HTML](#referencing-environment-variables-in-the-html)
  - [Adding Temporary Environment Variables In Your Shell](#adding-temporary-environment-variables-in-your-shell)
  - [Adding Development Environment Variables In `.env`](#adding-development-environment-variables-in-env)
- [Can I Use Decorators?](#can-i-use-decorators)
- [Fetching Data with AJAX Requests](#fetching-data-with-ajax-requests)
- [Integrating with an API Backend](#integrating-with-an-api-backend)
  - [Node](#node)
  - [Ruby on Rails](#ruby-on-rails)
- [Proxying API Requests in Development](#proxying-api-requests-in-development)
  - ["Invalid Host Header" Errors After Configuring Proxy](#invalid-host-header-errors-after-configuring-proxy)
  - [Configuring the Proxy Manually](#configuring-the-proxy-manually)
  - [Configuring a WebSocket Proxy](#configuring-a-websocket-proxy)
- [Using HTTPS in Development](#using-https-in-development)
- [Generating Dynamic ` ` Tags on the Server](#generating-dynamic-meta-tags-on-the-server)
- [Pre-Rendering into Static HTML Files](#pre-rendering-into-static-html-files)
- [Injecting Data from the Server into the Page](#injecting-data-from-the-server-into-the-page)
- [Running Tests](#running-tests)
  - [Filename Conventions](#filename-conventions)
  - [Command Line Interface](#command-line-interface)
  - [Version Control Integration](#version-control-integration)
  - [Writing Tests](#writing-tests)
  - [Testing Components](#testing-components)
  - [Using Third Party Assertion Libraries](#using-third-party-assertion-libraries)
  - [Initializing Test Environment](#initializing-test-environment)
  - [Focusing and Excluding Tests](#focusing-and-excluding-tests)
  - [Coverage Reporting](#coverage-reporting)
  - [Continuous Integration](#continuous-integration)
  - [Disabling jsdom](#disabling-jsdom)
  - [Snapshot Testing](#snapshot-testing)
  - [Editor Integration](#editor-integration)
- [Debugging Tests](#debugging-tests)
  - [Debugging Tests in Chrome](#debugging-tests-in-chrome)
  - [Debugging Tests in Visual Studio Code](#debugging-tests-in-visual-studio-code)
- [Developing Components in Isolation](#developing-components-in-isolation)
  - [Getting Started with Storybook](#getting-started-with-storybook)
  - [Getting Started with Styleguidist](#getting-started-with-styleguidist)
- [Publishing Components to npm](#publishing-components-to-npm)
- [Making a Progressive Web App](#making-a-progressive-web-app)
  - [Opting Out of Caching](#opting-out-of-caching)
  - [Offline-First Considerations](#offline-first-considerations)
  - [Progressive Web App Metadata](#progressive-web-app-metadata)
- [Analyzing the Bundle Size](#analyzing-the-bundle-size)
- [Deployment](#deployment)
  - [Static Server](#static-server)
  - [Other Solutions](#other-solutions)
  - [Serving Apps with Client-Side Routing](#serving-apps-with-client-side-routing)
  - [Building for Relative Paths](#building-for-relative-paths)
  - [Azure](#azure)
  - [Firebase](#firebase)
  - [GitHub Pages](#github-pages)
  - [Heroku](#heroku)
  - [Netlify](#netlify)
  - [Now](#now)
  - [S3 and CloudFront](#s3-and-cloudfront)
  - [Surge](#surge)
- [Advanced Configuration](#advanced-configuration)
- [Troubleshooting](#troubleshooting)
  - [`npm start` doesn’t detect changes](#npm-start-doesnt-detect-changes)
  - [`npm test` hangs on macOS Sierra](#npm-test-hangs-on-macos-sierra)
  - [`npm run build` exits too early](#npm-run-build-exits-too-early)
  - [`npm run build` fails on Heroku](#npm-run-build-fails-on-heroku)
  - [`npm run build` fails to minify](#npm-run-build-fails-to-minify)
  - [Moment.js locales are missing](#momentjs-locales-are-missing)
- [Alternatives to Ejecting](#alternatives-to-ejecting)
- [Something Missing?](#something-missing)

## Updating to New Releases

Create React App is divided into two packages:

* `create-react-app` is a global command-line utility that you use to create new projects.
* `react-scripts` is a development dependency in the generated projects (including this one).

You almost never need to update `create-react-app` itself: it delegates all the setup to `react-scripts`.

When you run `create-react-app`, it always creates the project with the latest version of `react-scripts` so you’ll get all the new features and improvements in newly created apps automatically.

To update an existing project to a new version of `react-scripts`, [open the changelog](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f54175dcf4022272d46432bc52032c162a39ec9507ffbf01277cf6cfdf1648a0458  find the version you’re currently on (check `package.json` in this folder if you’re not sure), and apply the migration instructions for the newer versions.

In most cases bumping the `react-scripts` version in `package.json` and running `npm install` in this folder should be enough, but it’s good to consult the [changelog](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f54175dcf4022272d46432bc52032c162a37b2da9bd7918ab59fe87a7b96a64cfff)  for potential breaking changes.

We commit to keeping the breaking changes minimal so you can upgrade `react-scripts` painlessly.

## Sending Feedback

We are always open to [your feedback](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f547628411ce894772fe71659c82007568d 

## Folder Structure

After creation, your project should look like this:

```
my-app/
  README.md
  node_modules/
  package.json
  public/
    index.html
    favicon.ico
  src/
    App.css
    App.js
    App.test.js
    index.css
    index.js
    logo.svg
```

For the project to build, **these files must exist with exact filenames**:

* `public/index.html` is the page template;
* `src/index.js` is the JavaScript entry point.

You can delete or rename the other files.

You may create subdirectories inside `src`. For faster rebuilds, only files inside `src` are processed by Webpack. 
You need to **put any JS and CSS files inside `src`**, otherwise Webpack won’t see them.

Only files inside `public` can be used from `public/index.html`. 
Read instructions below for using assets from JavaScript and HTML.

You can, however, create more top-level directories. 
They will not be included in the production build so you can use them for things like documentation.

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode. 
Open [http://localhost:3000](http://u.720life.cn/g/e71094f6077cb9592da5b56893f0ad141e926a791c7ed6f0d6bc4e65f5410164)  to view it in the browser.

The page will reload if you make edits. 
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode. 
See the section about [running tests](#running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder. 
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes. 
Your app is ready to be deployed!

See the section about [deployment](#deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (Webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Supported Browsers

By default, the generated project uses the latest version of React.

You can refer [to the React documentation](http://u.720life.cn/g/4c49339db9b897b20ce9fa9b972593be81f69f86ca5098efb6c209f0d721033005fb49bc7ba4e6394008b2833bdef7822f025c1b4e3f3bf4b867433d335b50c8)  for more information about supported browsers.

## Supported Language Features and Polyfills

This project supports a superset of the latest JavaScript standard. 
In addition to [ES6](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304677f62cf744fdb90c3bdec3288547075a13c1854ec3292e6b87cf459a1961b053)  syntax features, it also supports:

* [Exponentiation Operator](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f78e7ce227b1719898bcd68a2f94d87bdc0b13486a45ee1a245fa6f01b1cd41da83557d718ee7c715bea351e28a99477)  (ES2016).
* [Async/await](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046737c2195f2e31d80cb7b44961ce8e865c357d6098d571d1e55935c23dec3d447)  (ES2017).
* [Object Rest/Spread Properties](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460453d94dbc1c37c0b3622c619ffb34e5ca3fa367f931e8917d81ccb8d56eecbb6fed957e4dc61c83f06c7c7802b5f5e3)  (stage 3 proposal).
* [Dynamic import()](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046460af53d8b401b051690f5830d6601d942b7230b0c198d8ca23bbb06704512ea)  (stage 3 proposal)
* [Class Fields and Static Properties](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046460af53d8b401b051690f5830d6601d91a8a2e4b5fe21af98164f805a4fe643829d0c4de100badf149a226adc2ccbd4a)  (part of stage 3 proposal).
* [JSX](http://u.720life.cn/g/2b5f360ced91899e6d7809fb5ee1ea1fbd77b72146743bf5b007101f454a72b8e9559d0888c5f929f694b8f188db720b0502c587d66d4b4fb2808fe981cd31a5)  and [Flow](http://u.720life.cn/g/75e7334396568d32d60ffa9ab235a7724db28711453c538832ddf364f068d373)  syntax.

Learn more about [different proposal stages](http://u.720life.cn/g/c93859e9f1450f4e857784b45a8e110ff5f325c0c9c670f7d935b94a8d1f25c07fb8fdf388fffdf44450ca3b6cc47ba47db38be6beb76ef6cbb6be936352fdb929c015de68ed45119595a0da8e78a278 

While we recommend using experimental proposals with some caution, Facebook heavily uses these features in the product code, so we intend to provide [codemods](http://u.720life.cn/g/ce19288caac4b59057ec565c52ba1b368306bc344c14a44c97fc1c18c6274df2ea2cbc00d50befa5d9931308491e978a63a5b3df4685964f25c96ff911fd63a0d7d49024501d8c13de63ba8c0c6b8947)  if any of these proposals change in the future.

Note that **the project only includes a few ES6 [polyfills](http://u.720life.cn/g/dbf1195f8a53209e138d24666db0663673b77d6b385c8adfe0b84109bafe3e205a910849e8a4936016beb1dde61fe500 

* [`Object.assign()`](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd1266a2b10fc8d38fe1ae13f32e9cdc858c366c991d6af2f740c0eac8574759f3bad7056b4de9d441a59535beb1d016977a4ea25da20bf0821c72c8e39af581d4023)  via [`object-assign`](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462a65f16275212ca6b7b7326d099e66676f4dcb344dd31893320f35749aae9d6e 
* [`Promise`](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd126fdd1ea40180be86366b781aeb1d69201f77ec2e972b12461f043e3970497679d84a04b97180d73ddb7e07bf239102e6fdef3ef4a51b6cf03f3e5e97d4116cb7f)  via [`promise`](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304656b5cda3cae0b5437b55f7fbacb0ed076a7c8ec2bf4721085f8ba19ed3a234a3 
* [`fetch()`](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd1264084d97418d3ad0ff1747f0fabe5e67a53a197ec22ad3d31affd7a1de0017255)  via [`whatwg-fetch`](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469958e67c61f398c3b2acafded57349e417ad05609f127efca222c5377b1cd03e 

If you use any other ES6+ features that need **runtime support** (such as `Array.from()` or `Symbol`), make sure you are including the appropriate polyfills manually, or that the browsers you are targeting already support them.

Also note that using some newer syntax features like `for...of` or `[...nonArrayValue]` causes Babel to emit code that depends on ES6 runtime features and might not work without a polyfill. When in doubt, use [Babel REPL](http://u.720life.cn/g/c93859e9f1450f4e857784b45a8e110fa6892ff2a6d7df6bc639117607353759)  to see what any specific syntax compiles down to.

## Syntax Highlighting in the Editor

To configure the syntax highlighting in your favorite text editor, head to the [relevant Babel documentation page](http://u.720life.cn/g/c93859e9f1450f4e857784b45a8e110f37139ab96c4b906685cec45713109357)  and follow the instructions. Some of the most popular editors are covered.

## Displaying Lint Output in the Editor

>Note: this feature is available with `react-scripts@0.2.0` and higher. 
>It also only works with npm 3 or higher.

Some editors, including Sublime Text, Atom, and Visual Studio Code, provide plugins for ESLint.

They are not required for linting. You should see the linter output right in your terminal as well as the browser console. However, if you prefer the lint results to appear right in your editor, there are some extra steps you can do.

You would need to install an ESLint plugin for your editor first. Then, add a file called `.eslintrc` to the project root:

```js
{
  "extends": "react-app"
}
```

Now your editor should report the linting warnings.

Note that even if you edit your `.eslintrc` file further, these changes will **only affect the editor integration**. They won’t affect the terminal and in-browser lint output. This is because Create React App intentionally provides a minimal set of rules that find common mistakes.

If you want to enforce a coding style for your project, consider using [Prettier](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cc0b828bcdc1bcc709ca815afe026ff2c42e5bda4cd6c7109618d29d21587b23)  instead of ESLint style rules.

## Debugging in the Editor

**This feature is currently only supported by [Visual Studio Code](http://u.720life.cn/g/e2968b3acbb2cf55f957e5cee84b34f742faadec624378d40fc4cbc4df87c378)  and [WebStorm](http://u.720life.cn/g/a27ddb2b79548d3a829f3f0224b2480db88b64147f5f9db5ba451d598d2139563391138e7ceae416c74515b4b8a53c32 

Visual Studio Code and WebStorm support debugging out of the box with Create React App. This enables you as a developer to write and debug your React code without leaving the editor, and most importantly it enables you to have a continuous development workflow, where context switching is minimal, as you don’t have to switch between tools.

### Visual Studio Code

You would need to have the latest version of [VS Code](http://u.720life.cn/g/e2968b3acbb2cf55f957e5cee84b34f742faadec624378d40fc4cbc4df87c378)  and VS Code [Chrome Debugger Extension](http://u.720life.cn/g/61df49c8dfe6497e1d755535043d5993f084ad4bb2562a93ce813aeeb8e143e31ce529a8f29bba55ad86d25d14134388bb1aa37e2667d36afd0385e472df9a0236bd850e2070e6118242bbf92e5e6c26)  installed.

Then add the block below to your `launch.json` file and put it inside the `.vscode` folder in your app’s root directory.

```json
{
  "version": "0.2.0",
  "configurations": [{
    "name": "Chrome",
    "type": "chrome",
    "request": "launch",
    "url": "http://localhost:3000",
    "webRoot": "${workspaceRoot}/src",
    "sourceMapPathOverrides": {
      "webpack:///src/*": "${webRoot}/*"
    }
  }]
}
```
>Note: the URL may be different if you've made adjustments via the [HOST or PORT environment variables](#advanced-configuration).

Start your app by running `npm start`, and start debugging in VS Code by pressing `F5` or by clicking the green debug icon. You can now write code, set breakpoints, make changes to the code, and debug your newly modified code—all from your editor.

Having problems with VS Code Debugging? Please see their [troubleshooting guide](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466da0a62e928567e22efc9994c2bad2b5bea5e9619b77bdb6c548c7f8d5047197afa924f399229642a408e5f8cfacf1625286523eb48856c4e4db4c58f3770288f5e3b6642bf9aa886358142c7b36023e 

### WebStorm

You would need to have [WebStorm](http://u.720life.cn/g/a27ddb2b79548d3a829f3f0224b2480db88b64147f5f9db5ba451d598d21395600dd08e22563d42c5cb0103d8cdbd0bd)  and [JetBrains IDE Support](http://u.720life.cn/g/011bcbff60d4bdcdf5b89348f1b4fec4ea1629e5a5711d79823204fb51bba15ee0f3f740c33a82f68b541897eb1e5474bf6109527e6a5403f68f6a0656678642d6260e2b52a80a4e3afe11bfacec8bc57190236aa6838134eb5dd1c54c3aad05)  Chrome extension installed.

In the WebStorm menu `Run` select `Edit Configurations...`. Then click `+` and select `JavaScript Debug`. Paste `http://localhost:3000` into the URL field and save the configuration.

>Note: the URL may be different if you've made adjustments via the [HOST or PORT environment variables](#advanced-configuration).

Start your app by running `npm start`, then press `^D` on macOS or `F9` on Windows and Linux or click the green debug icon to start debugging in WebStorm.

The same way you can debug your application in IntelliJ IDEA Ultimate, PhpStorm, PyCharm Pro, and RubyMine. 

## Formatting Code Automatically

Prettier is an opinionated code formatter with support for JavaScript, CSS and JSON. With Prettier you can format the code you write automatically to ensure a code style within your project. See the [Prettier's GitHub page](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a16a0976a7d07c0c70c6f11740c8b08e6232a17113f291d58526f49172690672)  for more information, and look at this [page to see it in action](http://u.720life.cn/g/a41cbf80ae88871b67881ae5061997f083926f4b9b4c2d72b436bf19bd63a2fed3023ebfd209f84266878f3b0092a7a6 

To format our code whenever we make a commit in git, we need to install the following dependencies:

```sh
npm install --save husky lint-staged prettier
```

Alternatively you may use `yarn`:

```sh
yarn add husky lint-staged prettier
```

* `husky` makes it easy to use githooks as if they are npm scripts.
* `lint-staged` allows us to run scripts on staged files in git. See this [blog post about lint-staged to learn more about it](http://u.720life.cn/g/ce19288caac4b59057ec565c52ba1b36b313cdc1a957efa9638933cb0d16b09cf846fc2f7bffc856f0e4b303f166ae3d70d82962463e453bdd7c45c2783691d339c27a90ca2f0120eabcbf00a62fb7ff 
* `prettier` is the JavaScript formatter we will run before commits.

Now we can make sure every file is formatted correctly by adding a few lines to the `package.json` in the project root.

Add the following line to `scripts` section:

```diff
  "scripts": {
+   "precommit": "lint-staged",
    "start": "react-scripts start",
    "build": "react-scripts build",
```

Next we add a 'lint-staged' field to the `package.json`, for example:

```diff
  "dependencies": {
    // ...
  },
+ "lint-staged": {
+   "src/**/*.{js,jsx,json,css}": [
+     "prettier --single-quote --write",
+     "git add"
+   ]
+ },
  "scripts": {
```

Now, whenever you make a commit, Prettier will format the changed files automatically. You can also run `./node_modules/.bin/prettier --single-quote --write "src/**/*.{js,jsx}"` to format your entire project for the first time.

Next you might want to integrate Prettier in your favorite editor. Read the section on [Editor Integration](http://u.720life.cn/g/a41cbf80ae88871b67881ae5061997f05ea3252c7fd028d2e2f7686f06654f96139723966af73a7dea377d348a09a4e9)  on the Prettier GitHub page.

## Changing the Page ` `

You can find the source HTML file in the `public` folder of the generated project. You may edit the ` ` tag in it to change the title from “React App” to anything else.

Note that normally you wouldn’t edit files in the `public` folder very often. For example, [adding a stylesheet](#adding-a-stylesheet) is done without touching the HTML.

If you need to dynamically update the page title based on the content, you can use the browser [`document.title`](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd1267fb2856419993d6af548deecc896cdd1c209306492bbef65c165787d6f463737)  API. For more complex scenarios when you want to change the title from React components, you can use [React Helmet](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465378bd9eae7b0f30d68da4b6ab7f821219b3aad4d920429b00e3f3f1e876970e  a third party library.

If you use a custom server for your app in production and want to modify the title before it gets sent to the browser, you can follow advice in [this section](#generating-dynamic-meta-tags-on-the-server). Alternatively, you can pre-build each page as a static HTML file which then loads the JavaScript bundle, which is covered [here](#pre-rendering-into-static-html-files).

## Installing a Dependency

The generated project includes React and ReactDOM as dependencies. It also includes a set of scripts used by Create React App as a development dependency. You may install other dependencies (for example, React Router) with `npm`:

```sh
npm install --save react-router
```

Alternatively you may use `yarn`:

```sh
yarn add react-router
```

This works for any library, not just `react-router`.

## Importing a Component

This project setup supports ES6 modules thanks to Babel. 
While you can still use `require()` and `module.exports`, we encourage you to use [`import` and `export`](http://u.720life.cn/g/c15fc1e24c44fbbd23e530f9de63325dee1ad1144801303ed10f9b235c76c5baaa9e63cb82d33ed5c9f946d0925288b9)  instead.

For example:

### `Button.js`

```js
import React, { Component } from 'react';

class Button extends Component {
  render() {
    // ...
  }
}

export default Button; // Don’t forget to use export default!
```

### `DangerButton.js`


```js
import React, { Component } from 'react';
import Button from './Button'; // Import a component from another file

class DangerButton extends Component {
  render() {
    return  ;
  }
}

export default DangerButton;
```

Be aware of the [difference between default and named exports](http://u.720life.cn/g/ddb1c8aa997182cb1a4af16f7df394520a2863231ad8d7352308cd295ccf0ae9f282ad68adc0d67ad995c0843f51012c034711abae436b283b635ac8ac874f9ba08ac445284a7a0df2af27e694d292235da0ec04065b215541e4e85664afd94036a64dba115df45d8f7f36fd9f2a03498ca544af8ad0f2b8d7e407789c94e43e  It is a common source of mistakes.

We suggest that you stick to using default imports and exports when a module only exports a single thing (for example, a component). That’s what you get when you use `export default Button` and `import Button from './Button'`.

Named exports are useful for utility modules that export several functions. A module may have at most one default export and as many named exports as you like.

Learn more about ES6 modules:

* [When to use the curly braces?](http://u.720life.cn/g/ddb1c8aa997182cb1a4af16f7df394520a2863231ad8d7352308cd295ccf0ae9f282ad68adc0d67ad995c0843f51012c034711abae436b283b635ac8ac874f9ba08ac445284a7a0df2af27e694d292235da0ec04065b215541e4e85664afd94036a64dba115df45d8f7f36fd9f2a0349c774f5a44379f98924dfc21f7ebb734d) 
* [Exploring ES6: Modules](http://u.720life.cn/g/c15fc1e24c44fbbd23e530f9de63325dee1ad1144801303ed10f9b235c76c5baaa9e63cb82d33ed5c9f946d0925288b9) 
* [Understanding ES6: Modules](http://u.720life.cn/g/5f3e77fb5858e4ed025aaf129bb0cb3021dcab9dec091bab8b444b4feb1146e237bb6f7921ca2e258d7a62a87f3e782ad810ca8c9d221cc09765d2e636726d342c79a85e7fde6ca197caf29e8a69ebd700d73313fa71024098a9ec65a99ded27) 

## Code Splitting

Instead of downloading the entire app before users can use it, code splitting allows you to split your code into small chunks which you can then load on demand.

This project setup supports code splitting via [dynamic `import()`](http://u.720life.cn/g/53f102e716dc09a2e91d40c344e73a2fc83a8cb44fff219a753441fc83d07262296009627eba1403e991a3eef737bbb394bf6e303dba973f45143a7494f5dcab00ed324b292034a1d412400278761d3d  Its [proposal](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046460af53d8b401b051690f5830d6601d942b7230b0c198d8ca23bbb06704512ea)  is in stage 3. The `import()` function-like form takes the module name as an argument and returns a [`Promise`](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd126fdd1ea40180be86366b781aeb1d69201f77ec2e972b12461f043e3970497679d84a04b97180d73ddb7e07bf239102e6fdef3ef4a51b6cf03f3e5e97d4116cb7f)  which always resolves to the namespace object of the module.

Here is an example:

### `moduleA.js`

```js
const moduleA = 'Hello';

export { moduleA };
```
### `App.js`

```js
import React, { Component } from 'react';

class App extends Component {
  handleClick = () => {
    import('./moduleA')
      .then(({ moduleA }) => {
        // Use moduleA
      })
      .catch(err => {
        // Handle failure
      });
  };

  render() {
    return (
       
         Load 
       
    );
  }
}

export default App;
```

This will make `moduleA.js` and all its unique dependencies as a separate chunk that only loads after the user clicks the 'Load' button.

You can also use it with `async` / `await` syntax if you prefer it.

### With React Router

If you are using React Router check out [this tutorial](http://u.720life.cn/g/b4d94596ad5f503d0dfad7a9ca07f75378d579beda4db2ea5ec0814141b3c342eab62ab64989770359aa3fdfaa3ac38ee71ce360ea5175f30fedbd7ec7801b0e3c71594662a9af1c96d0c50aa5969e16)  on how to use code splitting with it. You can find the companion GitHub repository [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cf61b338a9e98a7325fea90e9db84390de0af4098f22bd9a097fe7bb926d4daf4ca9968abe1046abc6eb9108312dd3fc08c621cef1bcd561bb11d21132d1a61889626845de057b5a3fc805e2d549d67f23935e7e2f224b49c84788679f76dbd6 

Also check out the [Code Splitting](http://u.720life.cn/g/4c49339db9b897b20ce9fa9b972593befab3ad973d54f51e0eb68b51a42152a527df61a660c5667c7ea82dee8b06f997)  section in React documentation.

## Adding a Stylesheet

This project setup uses [Webpack](http://u.720life.cn/g/f87b2d3c2d36bc68c43d51982df87eb3eefbc0947b046267d355a23800c2aec4)  for handling all assets. Webpack offers a custom way of “extending” the concept of `import` beyond JavaScript. To express that a JavaScript file depends on a CSS file, you need to **import the CSS from the JavaScript file**:

### `Button.css`

```css
.Button {
  padding: 20px;
}
```

### `Button.js`

```js
import React, { Component } from 'react';
import './Button.css'; // Tell Webpack that Button.js uses these styles

class Button extends Component {
  render() {
    // You can use them as regular CSS styles
    return  ;
  }
}
```

**This is not required for React** but many people find this feature convenient. You can read about the benefits of this approach [here](http://u.720life.cn/g/ce19288caac4b59057ec565c52ba1b361d4f5add88b79fb9a4c746909d0b8732160be7329c05bb2cb977ff50a6256940d7c552274a281d87994b7b044c371a6726a2b9af4e52e08631f7f37ef0df260cae752b2cfa371f7e29fceffe17d7ab1681ff5d51bbb1f3437af23442a12a3d24  However you should be aware that this makes your code less portable to other build tools and environments than Webpack.

In development, expressing dependencies this way allows your styles to be reloaded on the fly as you edit them. In production, all CSS files will be concatenated into a single minified `.css` file in the build output.

If you are concerned about using Webpack-specific semantics, you can put all your CSS right into `src/index.css`. It would still be imported from `src/index.js`, but you could always remove that import if you later migrate to a different build tool.

## Post-Processing CSS

This project setup minifies your CSS and adds vendor prefixes to it automatically through [Autoprefixer](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046910ff48c659df9a84d5f371e94953602c1807535c0cd251ece364f54ac2fd9fb)  so you don’t need to worry about it.

For example, this:

```css
.App {
  display: flex;
  flex-direction: row;
  align-items: center;
}
```

becomes this:

```css
.App {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: horizontal;
  -webkit-box-direction: normal;
      -ms-flex-direction: row;
          flex-direction: row;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
}
```

If you need to disable autoprefixing for some reason, [follow this section](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046910ff48c659df9a84d5f371e9495360274588f59810f0fd4695a3b97e0d3c0c8b8a91aaacdbce35ee0d2421730a6f2c4 

## Adding a CSS Preprocessor (Sass, Less etc.)

Generally, we recommend that you don’t reuse the same CSS classes across different components. For example, instead of using a `.Button` CSS class in ` ` and ` ` components, we recommend creating a ` ` component with its own `.Button` styles, that both ` ` and ` ` can render (but [not inherit](http://u.720life.cn/g/2b5f360ced91899e6d7809fb5ee1ea1fbd77b72146743bf5b007101f454a72b8cc0cec60c0df275c19e883a6bb9c13871437271d6601b9f1dfa711d39fa4503ed48565715b6915447d319c899d7e8689 

Following this rule often makes CSS preprocessors less useful, as features like mixins and nesting are replaced by component composition. You can, however, integrate a CSS preprocessor if you find it valuable. In this walkthrough, we will be using Sass, but you can also use Less, or another alternative.

First, let’s install the command-line interface for Sass:

```sh
npm install --save node-sass-chokidar
```

Alternatively you may use `yarn`:

```sh
yarn add node-sass-chokidar
```

Then in `package.json`, add the following lines to `scripts`:

```diff
   "scripts": {
+    "build-css": "node-sass-chokidar src/ -o src/",
+    "watch-css": "npm run build-css && node-sass-chokidar src/ -o src/ --watch --recursive",
     "start": "react-scripts start",
     "build": "react-scripts build",
     "test": "react-scripts test --env=jsdom",
```

>Note: To use a different preprocessor, replace `build-css` and `watch-css` commands according to your preprocessor’s documentation.

Now you can rename `src/App.css` to `src/App.scss` and run `npm run watch-css`. The watcher will find every Sass file in `src` subdirectories, and create a corresponding CSS file next to it, in our case overwriting `src/App.css`. Since `src/App.js` still imports `src/App.css`, the styles become a part of your application. You can now edit `src/App.scss`, and `src/App.css` will be regenerated.

To share variables between Sass files, you can use Sass imports. For example, `src/App.scss` and other component style files could include `@import "./shared.scss";` with variable definitions.

To enable importing files without using relative paths, you can add the  `--include-path` option to the command in `package.json`.

```
"build-css": "node-sass-chokidar --include-path ./src --include-path ./node_modules src/ -o src/",
"watch-css": "npm run build-css && node-sass-chokidar --include-path ./src --include-path ./node_modules src/ -o src/ --watch --recursive",
```

This will allow you to do imports like

```scss
@import 'styles/_colors.scss'; // assuming a styles directory under src/
@import 'nprogress/nprogress'; // importing a css file from the nprogress node module
```

At this point you might want to remove all CSS files from the source control, and add `src/**/*.css` to your `.gitignore` file. It is generally a good practice to keep the build products outside of the source control.

As a final step, you may find it convenient to run `watch-css` automatically with `npm start`, and run `build-css` as a part of `npm run build`. You can use the `&&` operator to execute two scripts sequentially. However, there is no cross-platform way to run two scripts in parallel, so we will install a package for this:

```sh
npm install --save npm-run-all
```

Alternatively you may use `yarn`:

```sh
yarn add npm-run-all
```

Then we can change `start` and `build` scripts to include the CSS preprocessor commands:

```diff
   "scripts": {
     "build-css": "node-sass-chokidar src/ -o src/",
     "watch-css": "npm run build-css && node-sass-chokidar src/ -o src/ --watch --recursive",
-    "start": "react-scripts start",
-    "build": "react-scripts build",
+    "start-js": "react-scripts start",
+    "start": "npm-run-all -p watch-css start-js",
+    "build-js": "react-scripts build",
+    "build": "npm-run-all build-css build-js",
     "test": "react-scripts test --env=jsdom",
     "eject": "react-scripts eject"
   }
```

Now running `npm start` and `npm run build` also builds Sass files.

**Why `node-sass-chokidar`?**

`node-sass` has been reported as having the following issues:

- `node-sass --watch` has been reported to have *performance issues* in certain conditions when used in a virtual machine or with docker.

- Infinite styles compiling [#1939](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f54f1e1f51d507e6edf19563a6c14b603efd843c6b9c5136572eaa87139fbc38efd) 

- `node-sass` has been reported as having issues with detecting new files in a directory [#1891](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cfdf2e2cdb5285f168245453ee3e47a2d39a118610ab37766a3a7a875561b2f7) 

 `node-sass-chokidar` is used here as it addresses these issues.

## Adding Images, Fonts, and Files

With Webpack, using static assets like images and fonts works similarly to CSS.

You can **`import` a file right in a JavaScript module**. This tells Webpack to include that file in the bundle. Unlike CSS imports, importing a file gives you a string value. This value is the final path you can reference in your code, e.g. as the `src` attribute of an image or the `href` of a link to a PDF.

To reduce the number of requests to the server, importing images that are less than 10,000 bytes returns a [data URI](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd126c1eaa1a5d0a33c83ab650c6440d7e6ac7560dc3b4f41e160335bbc0e40dc119cd07a5ba59844d20997d975037c543ddd)  instead of a path. This applies to the following file extensions: bmp, gif, jpg, jpeg, and png. SVG files are excluded due to [#1153](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f5428239c791b1e6f14fad22aa16212c6503a81e1bd4c695f8c7b5ba024b1bc4130 

Here is an example:

```js
import React from 'react';
import logo from './logo.png'; // Tell Webpack this JS file uses this image

console.log(logo); // /logo.84287d09.png

function Header() {
  // Import result is the URL of your image
  return  ;
}

export default Header;
```

This ensures that when the project is built, Webpack will correctly move the images into the build folder, and provide us with correct paths.

This works in CSS too:

```css
.Logo {
  background-image: url(./logo.png);
}
```

Webpack finds all relative module references in CSS (they start with `./`) and replaces them with the final paths from the compiled bundle. If you make a typo or accidentally delete an important file, you will see a compilation error, just like when you import a non-existent JavaScript module. The final filenames in the compiled bundle are generated by Webpack from content hashes. If the file content changes in the future, Webpack will give it a different name in production so you don’t need to worry about long-term caching of assets.

Please be advised that this is also a custom feature of Webpack.

**It is not required for React** but many people enjoy it (and React Native uses a similar mechanism for images). 
An alternative way of handling static assets is described in the next section.

## Using the `public` Folder

>Note: this feature is available with `react-scripts@0.5.0` and higher.

### Changing the HTML

The `public` folder contains the HTML file so you can tweak it, for example, to [set the page title](#changing-the-page-title).
The ` ` tag with the compiled code will be added to it automatically during the build process.

### Adding Assets Outside of the Module System

You can also add other assets to the `public` folder.

Note that we normally encourage you to `import` assets in JavaScript files instead.
For example, see the sections on [adding a stylesheet](#adding-a-stylesheet) and [adding images and fonts](#adding-images-fonts-and-files).
This mechanism provides a number of benefits:

* Scripts and stylesheets get minified and bundled together to avoid extra network requests.
* Missing files cause compilation errors instead of 404 errors for your users.
* Result filenames include content hashes so you don’t need to worry about browsers caching their old versions.

However there is an **escape hatch** that you can use to add an asset outside of the module system.

If you put a file into the `public` folder, it will **not** be processed by Webpack. Instead it will be copied into the build folder untouched.   To reference assets in the `public` folder, you need to use a special variable called `PUBLIC_URL`.

Inside `index.html`, you can use it like this:

```html
 
```

Only files inside the `public` folder will be accessible by `%PUBLIC_URL%` prefix. If you need to use a file from `src` or `node_modules`, you’ll have to copy it there to explicitly specify your intention to make this file a part of the build.

When you run `npm run build`, Create React App will substitute `%PUBLIC_URL%` with a correct absolute path so your project works even if you use client-side routing or host it at a non-root URL.

In JavaScript code, you can use `process.env.PUBLIC_URL` for similar purposes:

```js
render() {
  // Note: this is an escape hatch and should be used sparingly!
  // Normally we recommend using `import` for getting asset URLs
  // as described in “Adding Images and Fonts” above this section.
  return  ;
}
```

Keep in mind the downsides of this approach:

* None of the files in `public` folder get post-processed or minified.
* Missing files will not be called at compilation time, and will cause 404 errors for your users.
* Result filenames won’t include content hashes so you’ll need to add query arguments or rename them every time they change.

### When to Use the `public` Folder

Normally we recommend importing [stylesheets](#adding-a-stylesheet), [images, and fonts](#adding-images-fonts-and-files) from JavaScript.
The `public` folder is useful as a workaround for a number of less common cases:

* You need a file with a specific name in the build output, such as [`manifest.webmanifest`](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd12621b09953e91c72df6d783762b578c2d27e22f4fd3c901bfe0f318fcb1559a6c3 
* You have thousands of images and need to dynamically reference their paths.
* You want to include a small script like [`pace.js`](http://u.720life.cn/g/a3385ad9571368037114eea9fd12b3641d68f8ad6c7d32cade4e4b8e1d25da4310474305c1ee4b1e9da94fcd857716f7)  outside of the bundled code.
* Some library may be incompatible with Webpack and you have no other option but to include it as a ` ` tag.

Note that if you add a ` ` that declares global variables, you also need to read the next section on using them.

## Using Global Variables

When you include a script in the HTML file that defines global variables and try to use one of these variables in the code, the linter will complain because it cannot see the definition of the variable.

You can avoid this by reading the global variable explicitly from the `window` object, for example:

```js
const $ = window.$;
```

This makes it obvious you are using a global variable intentionally rather than because of a typo.

Alternatively, you can force the linter to ignore any line by adding `// eslint-disable-line` after it.

## Adding Bootstrap

You don’t have to use [React Bootstrap](http://u.720life.cn/g/762243656ed2be41100113964e12cabbec7179e10b0770e44c832fb6f4440b2fc4ae8de3d6f3a7ebdb1003b869111dd2)  together with React but it is a popular library for integrating Bootstrap with React apps. If you need it, you can integrate it with Create React App by following these steps:

Install React Bootstrap and Bootstrap from npm. React Bootstrap does not include Bootstrap CSS so this needs to be installed as well:

```sh
npm install --save react-bootstrap bootstrap@3
```

Alternatively you may use `yarn`:

```sh
yarn add react-bootstrap bootstrap@3
```

Import Bootstrap CSS and optionally Bootstrap theme CSS in the beginning of your ```src/index.js``` file:

```js
import 'bootstrap/dist/css/bootstrap.css';
import 'bootstrap/dist/css/bootstrap-theme.css';
// Put any other imports below so that CSS from your
// components takes precedence over default styles.
```

Import required React Bootstrap components within ```src/App.js``` file or your custom component files:

```js
import { Navbar, Jumbotron, Button } from 'react-bootstrap';
```

Now you are ready to use the imported React Bootstrap components within your component hierarchy defined in the render method. Here is an example [`App.js`](http://u.720life.cn/g/4e20e720fe373c1a62f69fb6778bcfe3db05f1ba8cc354e98edc61e8bf3a72374caf67fc12b99e4bb876c474666009f54cabdfd66b81432638d35699cf240942729d996cf526ffb7f9d4f0c05dec0a9269a13f6d76f3280822cdd6e2ae15b90529e79132f2c430d08d1f7bc16a2bbbaf4a580e15436adcd56d3e0d29a6648d6c)  redone using React Bootstrap.

### Using a Custom Theme

Sometimes you might need to tweak the visual styles of Bootstrap (or equivalent package). 
We suggest the following approach:

* Create a new package that depends on the package you wish to customize, e.g. Bootstrap.
* Add the necessary build steps to tweak the theme, and publish your package on npm.
* Install your own theme npm package as a dependency of your app.

Here is an example of adding a [customized Bootstrap](http://u.720life.cn/g/ce19288caac4b59057ec565c52ba1b36b656be706aa3d28cad0a222fc143774c4e0bc82cd0b807b45210b124fd034c66d897e6872784ddc1245f95808d796ca309a2c2fc9649c9a4946ef263b457ffd9)  that follows these steps.

## Adding Flow

Flow is a static type checker that helps you write code with fewer bugs. Check out this [introduction to using static types in JavaScript](http://u.720life.cn/g/ce19288caac4b59057ec565c52ba1b365cc1de9b428df0f0c4d960480b7159a7cd898c962b926c01c823476a08f4efa249f122b1f5103282b0fbbd19942b3042f4d196cc89b4bf5cec66363b6c53e784c19494dbb62a854b2c9cc61db405d38f)  if you are new to this concept.

Recent versions of [Flow](http://u.720life.cn/g/a1454bffde940567aebd5064d43d28185285be39f52a4ac5daad1f16b001f908)  work with Create React App projects out of the box.

To add Flow to a Create React App project, follow these steps:

1. Run `npm install --save flow-bin` (or `yarn add flow-bin`).
2. Add `"flow": "flow"` to the `scripts` section of your `package.json`.
3. Run `npm run flow init` (or `yarn flow init`) to create a [`.flowconfig` file](http://u.720life.cn/g/75e7334396568d32d60ffa9ab235a77279645b82d3e70df0de9f87bc7ae418ba4dfb3422b7acb850b7f52d65a1f04718c9c2235dd5a9d5a9ab744bfbcd8dcf4e)  in the root directory.
4. Add `// @flow` to any files you want to type check (for example, to `src/App.js`).

Now you can run `npm run flow` (or `yarn flow`) to check the files for type errors.
You can optionally use an IDE like [Nuclide](http://u.720life.cn/g/b0e925a0c085a89b5daa4ac3d53ffbfdf18633ddc7ca496bf086495fb2f9c8d3e91c8cc7252837fe548a0783e1467f43)  for a better integrated experience.
In the future we plan to integrate it into Create React App even more closely.

To learn more about Flow, check out [its documentation](http://u.720life.cn/g/75e7334396568d32d60ffa9ab235a77283c2fb2b4b9edd2dec613c0f691db6de 

## Adding a Router

Create React App doesn't prescribe a specific routing solution, but [React Router](http://u.720life.cn/g/6dd236bd335a4bc6f1204a779143a888f8e3ba99d16ba137dc7748b06c322ad5674b6b331bd3c7dc893fd746e5846038)  is the most popular one.

To add it, run:

```sh
npm install --save react-router-dom
```

Alternatively you may use `yarn`:

```sh
yarn add react-router-dom
```

To try it, delete all the code in `src/App.js` and replace it with any of the examples on its website. The [Basic Example](http://u.720life.cn/g/6dd236bd335a4bc6f1204a779143a888f8e3ba99d16ba137dc7748b06c322ad5266b7767f596dc624e6d8bfc1dbb56923a01ab2037791b0dca04a245d4b1af76)  is a good place to get started.

Note that [you may need to configure your production server to support client-side routing](#serving-apps-with-client-side-routing) before deploying your app.

## Adding Custom Environment Variables

>Note: this feature is available with `react-scripts@0.2.3` and higher.

Your project can consume variables declared in your environment as if they were declared locally in your JS files. By
default you will have `NODE_ENV` defined for you, and any other environment variables starting with
`REACT_APP_`.

**The environment variables are embedded during the build time**. Since Create React App produces a static HTML/CSS/JS bundle, it can’t possibly read them at runtime. To read them at runtime, you would need to load HTML into memory on the server and replace placeholders in runtime, just like [described here](#injecting-data-from-the-server-into-the-page). Alternatively you can rebuild the app on the server anytime you change them.

>Note: You must create custom environment variables beginning with `REACT_APP_`. Any other variables except `NODE_ENV` will be ignored to avoid accidentally [exposing a private key on the machine that could have the same name](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f5431ee3a2451ba81cac4348a0781be5deaa84ab09d28318ba2cf239b4f728bff1b4beb55d9b440abda0169e4366db3024a  Changing any environment variables will require you to restart the development server if it is running.

These environment variables will be defined for you on `process.env`. For example, having an environment
variable named `REACT_APP_SECRET_CODE` will be exposed in your JS as `process.env.REACT_APP_SECRET_CODE`.

There is also a special built-in environment variable called `NODE_ENV`. You can read it from `process.env.NODE_ENV`. When you run `npm start`, it is always equal to `'development'`, when you run `npm test` it is always equal to `'test'`, and when you run `npm run build` to make a production bundle, it is always equal to `'production'`. **You cannot override `NODE_ENV` manually.** This prevents developers from accidentally deploying a slow development build to production.

These environment variables can be useful for displaying information conditionally based on where the project is
deployed or consuming sensitive data that lives outside of version control.

First, you need to have environment variables defined. For example, let’s say you wanted to consume a secret defined
in the environment inside a ` `:

```jsx
render() {
  return (
     
       You are running this application in  {process.env.NODE_ENV}  mode. 
       
         
       
     
  );
}
```

During the build, `process.env.REACT_APP_SECRET_CODE` will be replaced with the current value of the `REACT_APP_SECRET_CODE` environment variable. Remember that the `NODE_ENV` variable will be set for you automatically.

When you load the app in the browser and inspect the ` `, you will see its value set to `abcdef`, and the bold text will show the environment provided when using `npm start`:

```html
 
   You are running this application in  development  mode. 
   
     
   
 
```

The above form is looking for a variable called `REACT_APP_SECRET_CODE` from the environment. In order to consume this
value, we need to have it defined in the environment. This can be done using two ways: either in your shell or in
a `.env` file. Both of these ways are described in the next few sections.

Having access to the `NODE_ENV` is also useful for performing actions conditionally:

```js
if (process.env.NODE_ENV !== 'production') {
  analytics.disable();
}
```

When you compile the app with `npm run build`, the minification step will strip out this condition, and the resulting bundle will be smaller.

### Referencing Environment Variables in the HTML

>Note: this feature is available with `react-scripts@0.9.0` and higher.

You can also access the environment variables starting with `REACT_APP_` in the `public/index.html`. For example:

```html
 %REACT_APP_WEBSITE_NAME% 
```

Note that the caveats from the above section apply:

* Apart from a few built-in variables (`NODE_ENV` and `PUBLIC_URL`), variable names must start with `REACT_APP_` to work.
* The environment variables are injected at build time. If you need to inject them at runtime, [follow this approach instead](#generating-dynamic-meta-tags-on-the-server).

### Adding Temporary Environment Variables In Your Shell

Defining environment variables can vary between OSes. It’s also important to know that this manner is temporary for the
life of the shell session.

#### Windows (cmd.exe)

```cmd
set "REACT_APP_SECRET_CODE=abcdef" && npm start
```

(Note: Quotes around the variable assignment are required to avoid a trailing whitespace.)

#### Windows (Powershell)

```Powershell
($env:REACT_APP_SECRET_CODE = "abcdef") -and (npm start)
```

#### Linux, macOS (Bash)

```bash
REACT_APP_SECRET_CODE=abcdef npm start
```

### Adding Development Environment Variables In `.env`

>Note: this feature is available with `react-scripts@0.5.0` and higher.

To define permanent environment variables, create a file called `.env` in the root of your project:

```
REACT_APP_SECRET_CODE=abcdef
```
>Note: You must create custom environment variables beginning with `REACT_APP_`. Any other variables except `NODE_ENV` will be ignored to avoid [accidentally exposing a private key on the machine that could have the same name](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f5431ee3a2451ba81cac4348a0781be5deaa84ab09d28318ba2cf239b4f728bff1b4beb55d9b440abda0169e4366db3024a  Changing any environment variables will require you to restart the development server if it is running.

`.env` files **should be** checked into source control (with the exclusion of `.env*.local`).

#### What other `.env` files can be used?

>Note: this feature is **available with `react-scripts@1.0.0` and higher**.

* `.env`: Default.
* `.env.local`: Local overrides. **This file is loaded for all environments except test.**
* `.env.development`, `.env.test`, `.env.production`: Environment-specific settings.
* `.env.development.local`, `.env.test.local`, `.env.production.local`: Local overrides of environment-specific settings.

Files on the left have more priority than files on the right:

* `npm start`: `.env.development.local`, `.env.development`, `.env.local`, `.env`
* `npm run build`: `.env.production.local`, `.env.production`, `.env.local`, `.env`
* `npm test`: `.env.test.local`, `.env.test`, `.env` (note `.env.local` is missing)

These variables will act as the defaults if the machine does not explicitly set them. 
Please refer to the [dotenv documentation](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a1514843cb86fa4001c6b4e9bb3ccef580e465e395c7cf5baae75e5d60c72a42)  for more details.

>Note: If you are defining environment variables for development, your CI and/or hosting platform will most likely need
these defined as well. Consult their documentation how to do this. For example, see the documentation for [Travis CI](http://u.720life.cn/g/0fc7ca3c50320a29ffcd2692f695ea1d6466f31907c554c35a46493b7c0506615c57950e1311ec7c3888c8400ef0089a54fb44c64dd0075d038326f5ea25151d)  or [Heroku](http://u.720life.cn/g/4833f779fe04ff96a8fa2ae7bc743062c45e810e309b46de88967f27e0727d1d39cf06853bdce4351c7f35f89400249547893db799e1880b576f2c85bbbbfe37 

#### Expanding Environment Variables In `.env`

>Note: this feature is available with `react-scripts@1.1.0` and higher.

Expand variables already on your machine for use in your `.env` file (using [dotenv-expand](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a1514843cb86fa4001c6b4e9bb3ccef575ff81ab067a23c9c0e02fe1009014c2 

For example, to get the environment variable `npm_package_version`:

```
REACT_APP_VERSION=$npm_package_version
# also works:
# REACT_APP_VERSION=${npm_package_version}
```

Or expand variables local to the current `.env` file:

```
DOMAIN=www.example.com
REACT_APP_FOO=$DOMAIN/foo
REACT_APP_BAR=$DOMAIN/bar
```

## Can I Use Decorators?

Many popular libraries use [decorators](http://u.720life.cn/g/ce19288caac4b59057ec565c52ba1b36bd4606d67a81b94865a92773367a7a792ad9023766cd3956c85f0b33072d431de3cbf0eab49aadd08913e085bfe3ece966fb072a1750102ca4da62e92c70501d)  in their documentation. 
Create React App doesn’t support decorator syntax at the moment because:

* It is an experimental proposal and is subject to change.
* The current specification version is not officially supported by Babel.
* If the specification changes, we won’t be able to write a codemod because we don’t use them internally at Facebook.

However in many cases you can rewrite decorator-based code without decorators just as fine. 
Please refer to these two threads for reference:

* [#214](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f545843f2ee7d920d08f432674a9628a2ff) 
* [#411](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f54d6a08cd34c9f26e72ae5e30d2a0fed4f) 

Create React App will add decorator support when the specification advances to a stable stage.

## Fetching Data with AJAX Requests

React doesn't prescribe a specific approach to data fetching, but people commonly use either a library like [axios](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304638015ac6a54b1cadf0934b8a0d5637d0)  or the [`fetch()` API](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd1267fb2856419993d6af548deecc896cdd105617831f075950c93698c68a0ec19b4)  provided by the browser. Conveniently, Create React App includes a polyfill for `fetch()` so you can use it without worrying about the browser support.

The global `fetch` function allows to easily makes AJAX requests. It takes in a URL as an input and returns a `Promise` that resolves to a `Response` object. You can find more information about `fetch` [here](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd1267fb2856419993d6af548deecc896cdd1e4c27dbeb4b9ae117afafe60751ac0cba62d6ffb381880b9f280bf7c0128c994 

This project also includes a [Promise polyfill](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c6f5ec5e5d277fcf06b674e8bee1f9e9)  which provides a full implementation of Promises/A+. A Promise represents the eventual result of an asynchronous operation, you can find more information about Promises [here](http://u.720life.cn/g/b987cef77882ec082b3e6d0fe87b7c3797a0111c69f2835570e0515e964d77ce)  and [here](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd126fdd1ea40180be86366b781aeb1d69201f77ec2e972b12461f043e3970497679d84a04b97180d73ddb7e07bf239102e6f1f26064f4f5ec2bbfc0c75687e29de9d  Both axios and `fetch()` use Promises under the hood. You can also use the [`async / await`](http://u.720life.cn/g/4aacc706ab9903aa417d2c4c0b96932424948adb51a79f878740f2f5621e48335e6389d44c687b7e49fe40309bd3d261)  syntax to reduce the callback nesting.

You can learn more about making AJAX requests from React components in [the FAQ entry on the React website](http://u.720life.cn/g/4c49339db9b897b20ce9fa9b972593beff8d34be50f891796e5d1d7ab01e272056beb055faf30d1ac71277a37418b710 

## Integrating with an API Backend

These tutorials will help you to integrate your app with an API backend running on another port,
using `fetch()` to access it.

### Node
Check out [this tutorial](http://u.720life.cn/g/e183a4c1c4fe9e2036f2e9a53e25f68c130b081f84223b5c68f5767a796aa9e214ec69cd20cd9f0a6fa9cf59beb16c8a1fcd38bc13483184739e5e7ff29812d552c826a434aa44ce7c31ed6565770ec2 
You can find the companion GitHub repository [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304635d3dfdcd7540d524679def687102e993b3668978662d14ae312c481c1cfb515c98f25d6c3eec2decf0c3cb05fe0a43d 

### Ruby on Rails

Check out [this tutorial](http://u.720life.cn/g/e183a4c1c4fe9e2036f2e9a53e25f68c130b081f84223b5c68f5767a796aa9e22030fa614536ea7d083a5f90f22c94a57dcc6c292a4d6c4fd076cb1ffde9e1833d363250eaa20998736274edcf4acfe0ba7d07e2ca04866e66eafb6b9b26c1618c8d83aebed82e6bd2d34b008cf01be1 
You can find the companion GitHub repository [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304635d3dfdcd7540d524679def687102e993b3668978662d14ae312c481c1cfb515248481c7396066ed76867b090d3b7e7f 

## Proxying API Requests in Development

>Note: this feature is available with `react-scripts@0.2.3` and higher.

People often serve the front-end React app from the same host and port as their backend implementation. 
For example, a production setup might look like this after the app is deployed:

```
/             - static server returns index.html with React app
/todos        - static server returns index.html with React app
/api/todos    - server handles any /api/* requests using the backend implementation
```

Such setup is **not** required. However, if you **do** have a setup like this, it is convenient to write requests like `fetch('/api/todos')` without worrying about redirecting them to another host or port during development.

To tell the development server to proxy any unknown requests to your API server in development, add a `proxy` field to your `package.json`, for example:

```js
  "proxy": "http://localhost:4000",
```

This way, when you `fetch('/api/todos')` in development, the development server will recognize that it’s not a static asset, and will proxy your request to `http://localhost:4000/api/todos` as a fallback. The development server will **only** attempt to send requests without `text/html` in its `Accept` header to the proxy.

Conveniently, this avoids [CORS issues](http://u.720life.cn/g/ddb1c8aa997182cb1a4af16f7df394520a2863231ad8d7352308cd295ccf0ae9c01f03275056be1cced0dfc915a492dc98130b5d392a84f10782c4cfccd525fb6a89b7464e4e9376df7bb572b8458a19e221eccd023b4bbe0482643c1783dee8)  and error messages like this in development:

```
Fetch API cannot load http://localhost:4000/api/todos. No 'Access-Control-Allow-Origin' header is present on the requested resource. Origin 'http://localhost:3000' is therefore not allowed access. If an opaque response serves your needs, set the request's mode to 'no-cors' to fetch the resource with CORS disabled.
```

Keep in mind that `proxy` only has effect in development (with `npm start`), and it is up to you to ensure that URLs like `/api/todos` point to the right thing in production. You don’t have to use the `/api` prefix. Any unrecognized request without a `text/html` accept header will be redirected to the specified `proxy`.

The `proxy` option supports HTTP, HTTPS and WebSocket connections. 
If the `proxy` option is **not** flexible enough for you, alternatively you can:

* [Configure the proxy yourself](#configuring-the-proxy-manually)
* Enable CORS on your server ([here’s how to do it for Express](http://u.720life.cn/g/ad145526cbd53aa85254ef22fa25151b21f4e4459db985e7f335201e334f582c9fbcce8beb8e3dfcfd2b9dac7bdc02f4 
* Use [environment variables](#adding-custom-environment-variables) to inject the right server host and port into your app.

### "Invalid Host Header" Errors After Configuring Proxy

When you enable the `proxy` option, you opt into a more strict set of host checks. This is necessary because leaving the backend open to remote hosts makes your computer vulnerable to DNS rebinding attacks. The issue is explained in [this article](http://u.720life.cn/g/ce19288caac4b59057ec565c52ba1b363a24786cbd353b0f72f1ddf4ca6cbeb8f56c6df18a81c92b6ede825ca3b9a335f0e8321ce405a8212eff1738076ce2b173b63882342690282dd040ae9ff0f2fb3e29a367842d5dafc785234f303e18b1)  and [this issue](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467fcc54064697beb3b7b3df6e06eef2988cc25e97cccacfbd4f8105a389317b1eb1c5bcb96aff97a154f211af171f7ad7 

This shouldn’t affect you when developing on `localhost`, but if you develop remotely like [described here](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f549ad7b056327ee46e8ba4f714963352653e1963d594ead164e9171929ee3f89b4  you will see this error in the browser after enabling the `proxy` option:

>Invalid Host header

To work around it, you can specify your public development host in a file called `.env.development` in the root of your project:

```
HOST=mypublicdevhost.com
```

If you restart the development server now and load the app from the specified host, it should work.

If you are still having issues or if you’re using a more exotic environment like a cloud editor, you can bypass the host check completely by adding a line to `.env.development.local`. **Note that this is dangerous and exposes your machine to remote code execution from malicious websites:**

```
# NOTE: THIS IS DANGEROUS!
# It exposes your machine to attacks from the websites you visit.
DANGEROUSLY_DISABLE_HOST_CHECK=true
```

We don’t recommend this approach.

### Configuring the Proxy Manually

>Note: this feature is available with `react-scripts@1.0.0` and higher.

If the `proxy` option is **not** flexible enough for you, you can specify an object in the following form (in `package.json`). 
You may also specify any configuration value [`http-proxy-middleware`](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046431ee7bf782f65f52cf9086f4d7338e3ee2ba44f012ee10a483c56846fccfce6763fbe492ce04798cd2cd4197e2c207c)  or [`http-proxy`](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304613e0c6e978490c40c1b0e592eb0fb1753cce2ffb1408c3bb247bb4875f987ef413b579b946af7ac883e76ce4d40bc533)  supports.
```js
{
  // ...
  "proxy": {
    "/api": {
      "target": " ",
      "ws": true
      // ...
    }
  }
  // ...
}
```

All requests matching this path will be proxies, no exceptions. This includes requests for `text/html`, which the standard `proxy` option does not proxy.

If you need to specify multiple proxies, you may do so by specifying additional entries.
Matches are regular expressions, so that you can use a regexp to match multiple paths.
```js
{
  // ...
  "proxy": {
    // Matches any request starting with /api
    "/api": {
      "target": " ",
      "ws": true
      // ...
    },
    // Matches any request starting with /foo
    "/foo": {
      "target": " ",
      "ssl": true,
      "pathRewrite": {
        "^/foo": "/foo/beta"
      }
      // ...
    },
    // Matches /bar/abc.html but not /bar/sub/def.html
    "/bar/[^/]*[.]html": {
      "target": " ",
      // ...
    },
    // Matches /baz/abc.html and /baz/sub/def.html
    "/baz/.*/.*[.]html": {
      "target": " "
      // ...
    }
  }
  // ...
}
```

### Configuring a WebSocket Proxy

When setting up a WebSocket proxy, there are a some extra considerations to be aware of.

If you’re using a WebSocket engine like [Socket.io](http://u.720life.cn/g/d1d2c4e50f3a95a3fbf9a01af462df22cf9e840995034e5153d1e0be7a9b0f87  you must have a Socket.io server running that you can use as the proxy target. Socket.io will not work with a standard WebSocket server. Specifically, don't expect Socket.io to work with [the websocket.org echo test](http://u.720life.cn/g/e3dcb30212dbc72547937d3bb811e33532efcc65d03b6f59cf1f1a9a642b4c6b 

There’s some good documentation available for [setting up a Socket.io server](http://u.720life.cn/g/d1d2c4e50f3a95a3fbf9a01af462df223a6c3e99e7b7342566ae31a81f0c0b1e 

Standard WebSockets **will** work with a standard WebSocket server as well as the websocket.org echo test. You can use libraries like [ws](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466a3f8f14957707c4875e77888f41374a)  for the server, with [native WebSockets in the browser](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd1267fb2856419993d6af548deecc896cdd1e8556a36b5499511a9f030a5ab890fa0 

Either way, you can proxy WebSocket requests manually in `package.json`:

```js
{
  // ...
  "proxy": {
    "/socket": {
      // Your compatible WebSocket server
      "target": "ws:// ",
      // Tell http-proxy-middleware that this is a WebSocket proxy.
      // Also allows you to proxy WebSocket requests without an additional HTTP request
      // https://github.com/chimurai/http-proxy-middleware#external-websocket-upgrade
      "ws": true
      // ...
    }
  }
  // ...
}
```

## Using HTTPS in Development

>Note: this feature is available with `react-scripts@0.4.0` and higher.

You may require the dev server to serve pages over HTTPS. One particular case where this could be useful is when using [the "proxy" feature](#proxying-api-requests-in-development) to proxy requests to an API server when that API server is itself serving HTTPS.

To do this, set the `HTTPS` environment variable to `true`, then start the dev server as usual with `npm start`:

#### Windows (cmd.exe)

```cmd
set HTTPS=true&&npm start
```

#### Windows (Powershell)

```Powershell
($env:HTTPS = $true) -and (npm start)
```

(Note: the lack of whitespace is intentional.)

#### Linux, macOS (Bash)

```bash
HTTPS=true npm start
```

Note that the server will use a self-signed certificate, so your web browser will almost definitely display a warning upon accessing the page.

## Generating Dynamic ` ` Tags on the Server

Since Create React App doesn’t support server rendering, you might be wondering how to make ` ` tags dynamic and reflect the current URL. To solve this, we recommend to add placeholders into the HTML, like this:

```html
 
 
   
     
     
```

Then, on the server, regardless of the backend you use, you can read `index.html` into memory and replace `__OG_TITLE__`, `__OG_DESCRIPTION__`, and any other placeholders with values depending on the current URL. Just make sure to sanitize and escape the interpolated values so that they are safe to embed into HTML!

If you use a Node server, you can even share the route matching logic between the client and the server. However duplicating it also works fine in simple cases.

## Pre-Rendering into Static HTML Files

If you’re hosting your `build` with a static hosting provider you can use [react-snapshot](http://u.720life.cn/g/920c024f0b8c5aa5e32c4f88af4e6c96f04f91916c4c3865e50e1e5585efbc49fbb980046a034a780e54e9a07af1ff34)  or [react-snap](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d0ac17306eee6120b0294bd9d1a82113703bf8834976fbfcadda780ca7da9a36)  to generate HTML pages for each route, or relative link, in your application. These pages will then seamlessly become active, or “hydrated”, when the JavaScript bundle has loaded.

There are also opportunities to use this outside of static hosting, to take the pressure off the server when generating and caching routes.

The primary benefit of pre-rendering is that you get the core content of each page _with_ the HTML payload—regardless of whether or not your JavaScript bundle successfully downloads. It also increases the likelihood that each route of your application will be picked up by search engines.

You can read more about [zero-configuration pre-rendering (also called snapshotting) here](http://u.720life.cn/g/ce19288caac4b59057ec565c52ba1b36fc88aa0996c4a4adf3fe6102096a9eca2adc85bc741dea08e368ff3f2d431c7400d1b69b962658cec24dc48ab5e6cb3c8b645757afc42135c4949ec6b210af7c 

## Injecting Data from the Server into the Page

Similarly to the previous section, you can leave some placeholders in the HTML that inject global variables, for example:

```js
 
 
   
     
      window.SERVER_DATA = __SERVER_DATA__;
     
```

Then, on the server, you can replace `__SERVER_DATA__` with a JSON of real data right before sending the response. The client code can then read `window.SERVER_DATA` to use it. **Make sure to [sanitize the JSON before sending it to the client](http://u.720life.cn/g/ce19288caac4b59057ec565c52ba1b36a65f6f5243f96415833a73c6e90f278adc7faa39b28a068019e1a3e3fcb6ab0e6f731453cdc60ed80e5be34df42adf8c36eadf08585cd85cf39fd1de78206a68677a8a904f16787bce751984dedb0f54387da38847ac9398be50d66e86b1a747)  as it makes your app vulnerable to XSS attacks.**

## Running Tests

>Note: this feature is available with `react-scripts@0.3.0` and higher. 
>[Read the migration guide to learn how to enable it in older projects!](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f54175dcf4022272d46432bc52032c162a3489b199c44690ef67d80a4ec0475f99b5e9c1914b444c2b3959bac192a4a0376b5cb9c00aa2146000668736c8da527a6) 

Create React App uses [Jest](http://u.720life.cn/g/2b5f360ced91899e6d7809fb5ee1ea1ff6c3ccdeb5963434cea8a08853b4c45a)  as its test runner. To prepare for this integration, we did a [major revamp](http://u.720life.cn/g/2b5f360ced91899e6d7809fb5ee1ea1ff6c3ccdeb5963434cea8a08853b4c45aa0047cba70ee4281ab5be53b59788d8991f5f54162e36d868e3436ce686928fb)  of Jest so if you heard bad things about it years ago, give it another try.

Jest is a Node-based runner. This means that the tests always run in a Node environment and not in a real browser. This lets us enable fast iteration speed and prevent flakiness.

While Jest provides browser globals such as `window` thanks to [jsdom](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e9359ca281f91f1d2241b064f92938e9f04f83089a233bde86ca5996e4a18b60  they are only approximations of the real browser behavior. Jest is intended to be used for unit tests of your logic and your components rather than the DOM quirks.

We recommend that you use a separate tool for browser end-to-end tests if you need them. They are beyond the scope of Create React App.

### Filename Conventions

Jest will look for test files with any of the following popular naming conventions:

* Files with `.js` suffix in `__tests__` folders.
* Files with `.test.js` suffix.
* Files with `.spec.js` suffix.

The `.test.js` / `.spec.js` files (or the `__tests__` folders) can be located at any depth under the `src` top level folder.

We recommend to put the test files (or `__tests__` folders) next to the code they are testing so that relative imports appear shorter. For example, if `App.test.js` and `App.js` are in the same folder, the test just needs to `import App from './App'` instead of a long relative path. Colocation also helps find tests more quickly in larger projects.

### Command Line Interface

When you run `npm test`, Jest will launch in the watch mode. Every time you save a file, it will re-run the tests, just like `npm start` recompiles the code.

The watcher includes an interactive command-line interface with the ability to run all tests, or focus on a search pattern. It is designed this way so that you can keep it open and enjoy fast re-runs. You can learn the commands from the “Watch Usage” note that the watcher prints after every run:

![Jest watch mode](http://facebook.github.io/jest/img/blog/15-watch.gif)

### Version Control Integration

By default, when you run `npm test`, Jest will only run the tests related to files changed since the last commit. This is an optimization designed to make your tests run fast regardless of how many tests you have. However it assumes that you don’t often commit the code that doesn’t pass the tests.

Jest will always explicitly mention that it only ran tests related to the files changed since the last commit. You can also press `a` in the watch mode to force Jest to run all tests.

Jest will always run all tests on a [continuous integration](#continuous-integration) server or if the project is not inside a Git or Mercurial repository.

### Writing Tests

To create tests, add `it()` (or `test()`) blocks with the name of the test and its code. You may optionally wrap them in `describe()` blocks for logical grouping but this is neither required nor recommended.

Jest provides a built-in `expect()` global function for making assertions. A basic test could look like this:

```js
import sum from './sum';

it('sums numbers', () => {
  expect(sum(1, 2)).toEqual(3);
  expect(sum(2, 2)).toEqual(4);
});
```

All `expect()` matchers supported by Jest are [extensively documented here](http://u.720life.cn/g/2b5f360ced91899e6d7809fb5ee1ea1ff6c3ccdeb5963434cea8a08853b4c45ab54603e03f1bd0a50f2fb11c72bb2ef7870f408718c324c80d62addb547ebbc9  
You can also use [`jest.fn()` and `expect(fn).toBeCalled()`](http://u.720life.cn/g/2b5f360ced91899e6d7809fb5ee1ea1ff6c3ccdeb5963434cea8a08853b4c45ab54603e03f1bd0a50f2fb11c72bb2ef7a12b46a35a9241f1af74a67851c1b96fe9ea7134b5763bf767503bf2332c0878)  to create “spies” or mock functions.

### Testing Components

There is a broad spectrum of component testing techniques. They range from a “smoke test” verifying that a component renders without throwing, to shallow rendering and testing some of the output, to full rendering and testing component lifecycle and state changes.

Different projects choose different testing tradeoffs based on how often components change, and how much logic they contain. If you haven’t decided on a testing strategy yet, we recommend that you start with creating simple smoke tests for your components:

```js
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';

it('renders without crashing', () => {
  const div = document.createElement('div');
  ReactDOM.render( , div);
});
```

This test mounts a component and makes sure that it didn’t throw during rendering. Tests like this provide a lot of value with very little effort so they are great as a starting point, and this is the test you will find in `src/App.test.js`.

When you encounter bugs caused by changing components, you will gain a deeper insight into which parts of them are worth testing in your application. This might be a good time to introduce more specific tests asserting specific expected output or behavior.

If you’d like to test components in isolation from the child components they render, we recommend using [`shallow()` rendering API](http://u.720life.cn/g/6d563d09ad0079e975b69586273f66bf6646d7d253b01e87e507815f714f2a69aec05a3768394d59b3010d0a17d5f109)  from [Enzyme](http://u.720life.cn/g/6d563d09ad0079e975b69586273f66bfbe7b12bee788c9ceba7f687ffb659124  To install it, run:

```sh
npm install --save enzyme enzyme-adapter-react-16 react-test-renderer
```

Alternatively you may use `yarn`:

```sh
yarn add enzyme enzyme-adapter-react-16 react-test-renderer
```

As of Enzyme 3, you will need to install Enzyme along with an Adapter corresponding to the version of React you are using. (The examples above use the adapter for React 16.)

The adapter will also need to be configured in your [global setup file](#initializing-test-environment):

#### `src/setupTests.js`
```js
import { configure } from 'enzyme';
import Adapter from 'enzyme-adapter-react-16';

configure({ adapter: new Adapter() });
```

>Note: Keep in mind that if you decide to "eject" before creating `src/setupTests.js`, the resulting `package.json` file won't contain any reference to it. [Read here](#initializing-test-environment) to learn how to add this after ejecting.

Now you can write a smoke test with it:

```js
import React from 'react';
import { shallow } from 'enzyme';
import App from './App';

it('renders without crashing', () => {
  shallow( );
});
```

Unlike the previous smoke test using `ReactDOM.render()`, this test only renders ` ` and doesn’t go deeper. For example, even if ` ` itself renders a ` ` that throws, this test will pass. Shallow rendering is great for isolated unit tests, but you may still want to create some full rendering tests to ensure the components integrate correctly. Enzyme supports [full rendering with `mount()`](http://u.720life.cn/g/6d563d09ad0079e975b69586273f66bf6646d7d253b01e87e507815f714f2a6925a5c5c2b5b1219a09d18482eb9be145  and you can also use it for testing state changes and component lifecycle.

You can read the [Enzyme documentation](http://u.720life.cn/g/6d563d09ad0079e975b69586273f66bfc6a2ef87df33ab8ba5b51fa650348d89)  for more testing techniques. Enzyme documentation uses Chai and Sinon for assertions but you don’t have to use them because Jest provides built-in `expect()` and `jest.fn()` for spies.

Here is an example from Enzyme documentation that asserts specific output, rewritten to use Jest matchers:

```js
import React from 'react';
import { shallow } from 'enzyme';
import App from './App';

it('renders welcome message', () => {
  const wrapper = shallow( );
  const welcome =  Welcome to React ;
  // expect(wrapper.contains(welcome)).to.equal(true);
  expect(wrapper.contains(welcome)).toEqual(true);
});
```

All Jest matchers are [extensively documented here](http://u.720life.cn/g/cb6f6f5a71ffc3893ed7794d465226c956e686a239c6a60c0f91f9b684b9251cbeede6a5094220f3a53e08757f03974203ad0820d76056707d7b6dc5ac4bbef6  
Nevertheless you can use a third-party assertion library like [Chai](http://u.720life.cn/g/4feff95aaa9f7a179f6cb0f59ecae5d0e3538a6ab9cd6e9c906a84c55b8b45f9)  if you want to, as described below.

Additionally, you might find [jest-enzyme](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463d6b6082cd0729b121ec8ba3fd4703d55b96cb86b117c32945bb54751ce289c3)  helpful to simplify your tests with readable matchers. The above `contains` code can be written more simply with jest-enzyme.

```js
expect(wrapper).toContainReact(welcome)
```

To enable this, install `jest-enzyme`:

```sh
npm install --save jest-enzyme
```

Alternatively you may use `yarn`:

```sh
yarn add jest-enzyme
```

Import it in [`src/setupTests.js`](#initializing-test-environment) to make its matchers available in every test:

```js
import 'jest-enzyme';
```

### Using Third Party Assertion Libraries

We recommend that you use `expect()` for assertions and `jest.fn()` for spies. If you are having issues with them please [file those against Jest](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304632291197544a7ea7d219229703505bcf798b21b3f568eead585d8ceff31e52d2  and we’ll fix them. We intend to keep making them better for React, supporting, for example, [pretty-printing React elements as JSX](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304632291197544a7ea7d219229703505bcf48d930b978e37d95d0db66c18932e63c 

However, if you are used to other libraries, such as [Chai](http://u.720life.cn/g/4feff95aaa9f7a179f6cb0f59ecae5d0e3538a6ab9cd6e9c906a84c55b8b45f9)  and [Sinon](http://u.720life.cn/g/c977555e3cf2c35d048b9297ec0831ea6c5f5e314d0f6d01b05ca00982444f70  or if you have existing code using them that you’d like to port over, you can import them normally like this:

```js
import sinon from 'sinon';
import { expect } from 'chai';
```

and then use them in your tests like you normally do.

### Initializing Test Environment

>Note: this feature is available with `react-scripts@0.4.0` and higher.

If your app uses a browser API that you need to mock in your tests or if you just need a global setup before running your tests, add a `src/setupTests.js` to your project. It will be automatically executed before running your tests.

For example:

#### `src/setupTests.js`
```js
const localStorageMock = {
  getItem: jest.fn(),
  setItem: jest.fn(),
  clear: jest.fn()
};
global.localStorage = localStorageMock
```

>Note: Keep in mind that if you decide to "eject" before creating `src/setupTests.js`, the resulting `package.json` file won't contain any reference to it, so you should manually create the property `setupTestFrameworkScriptFile` in the configuration for Jest, something like the following:

>```js
>"jest": {
>   // ...
>   "setupTestFrameworkScriptFile": " /src/setupTests.js"
>  }
>  ```

### Focusing and Excluding Tests

You can replace `it()` with `xit()` to temporarily exclude a test from being executed. 
Similarly, `fit()` lets you focus on a specific test without running any other tests.

### Coverage Reporting

Jest has an integrated coverage reporter that works well with ES6 and requires no configuration. 
Run `npm test -- --coverage` (note extra `--` in the middle) to include a coverage report like this:

![coverage report](http://i.imgur.com/5bFhnTS.png)

Note that tests run much slower with coverage so it is recommended to run it separately from your normal workflow.

#### Configuration

The default Jest coverage configuration can be overriden by adding any of the following supported keys to a Jest config in your package.json.

Supported overrides:
 - [`collectCoverageFrom`](http://u.720life.cn/g/2b5f360ced91899e6d7809fb5ee1ea1ff6c3ccdeb5963434cea8a08853b4c45a4e1944e54c39aff459e55b9e650e49f9e1407afe4b9da7a1a546020ab328f85eba2d01ef909a908ba454f18645345fecd3f297f5ca15a8fbf4430779d429137b) 
 - [`coverageReporters`](http://u.720life.cn/g/2b5f360ced91899e6d7809fb5ee1ea1ff6c3ccdeb5963434cea8a08853b4c45a4e1944e54c39aff459e55b9e650e49f915afbd3c70d04e3a5723f2cbeaa7d7735090cdd2847fc796087ed4313634af5c1273ee1ce2fe3bb2d08423d282f7235b) 
 - [`coverageThreshold`](http://u.720life.cn/g/2b5f360ced91899e6d7809fb5ee1ea1ff6c3ccdeb5963434cea8a08853b4c45a4e1944e54c39aff459e55b9e650e49f915afbd3c70d04e3a5723f2cbeaa7d7739bc84a629a8edd65e4cddc0d3af4976aebcc15f712ea7bcb541291483a569aeb) 
 - [`snapshotSerializers`](http://u.720life.cn/g/2b5f360ced91899e6d7809fb5ee1ea1ff6c3ccdeb5963434cea8a08853b4c45a4e1944e54c39aff459e55b9e650e49f9a15e6e7eb9e5d9b4a15ac4f879acdb45f9fe0e1d3f2aca9f293b3119d71f71831ecc1c2785d9e3fec3f12ee870acb326) 

Example package.json:

```json
{
  "name": "your-package",
  "jest": {
    "collectCoverageFrom" : [
      "src/**/*.{js,jsx}",
      "! /node_modules/",
      "! /path/to/dir/"
    ],
    "coverageThreshold": {
      "global": {
        "branches": 90,
        "functions": 90,
        "lines": 90,
        "statements": 90
      }
    },
    "coverageReporters": ["text"],
    "snapshotSerializers": ["my-serializer-module"]
  }
}
```

### Continuous Integration

By default `npm test` runs the watcher with interactive CLI. However, you can force it to run tests once and finish the process by setting an environment variable called `CI`.

When creating a build of your application with `npm run build` linter warnings are not checked by default. Like `npm test`, you can force the build to perform a linter warning check by setting the environment variable `CI`. If any warnings are encountered then the build fails.

Popular CI servers already set the environment variable `CI` by default but you can do this yourself too:

### On CI servers
#### Travis CI

1. Following the [Travis Getting started](http://u.720life.cn/g/0fc7ca3c50320a29ffcd2692f695ea1d6466f31907c554c35a46493b7c05066163c8ed142ac30a37721ec5b1e4084444)  guide for syncing your GitHub repository with Travis.  You may need to initialize some settings manually in your [profile](http://u.720life.cn/g/41730a1a7cf811a1831a38c04993d30b3520d965588c6ff92d3eb252396da5b5)  page.
1. Add a `.travis.yml` file to your git repository.
```
language: node_js
node_js:
  - 6
cache:
  directories:
    - node_modules
script:
  - npm run build
  - npm test
```
1. Trigger your first build with a git push.
1. [Customize your Travis CI Build](http://u.720life.cn/g/0fc7ca3c50320a29ffcd2692f695ea1d6466f31907c554c35a46493b7c0506612f8ace33eb59f89356bd6330878e42f14735a1ceda8bb26bc7d9e6ef400b456b)  if needed.

#### CircleCI

Follow [this article](http://u.720life.cn/g/ce19288caac4b59057ec565c52ba1b3617f48ae9fdce0d07420321ee802c8f9089b1b76225487e48d3498463ea769d85753a86af90576e229f8c3192ab38e197d7a1503a8f547333450fcb46444372a3)  to set up CircleCI with a Create React App project.

### On your own environment
##### Windows (cmd.exe)

```cmd
set CI=true&&npm test
```

```cmd
set CI=true&&npm run build
```

(Note: the lack of whitespace is intentional.)

##### Windows (Powershell)

```Powershell
($env:CI = $true) -and (npm test)
```

```Powershell
($env:CI = $true) -and (npm run build)
```

##### Linux, macOS (Bash)

```bash
CI=true npm test
```

```bash
CI=true npm run build
```

The test command will force Jest to run tests once instead of launching the watcher.

>  If you find yourself doing this often in development, please [file an issue](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f5459601c0f0b2f9c81db76311c384f8cf2)  to tell us about your use case because we want to make watcher the best experience and are open to changing how it works to accommodate more workflows.

The build command will check for linter warnings and fail if any are found.

### Disabling jsdom

By default, the `package.json` of the generated project looks like this:

```js
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test --env=jsdom"
```

If you know that none of your tests depend on [jsdom](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e9359ca281f91f1d2241b064f92938e9f04f83089a233bde86ca5996e4a18b60  you can safely remove `--env=jsdom`, and your tests will run faster:

```diff
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
-   "test": "react-scripts test --env=jsdom"
+   "test": "react-scripts test"
```

To help you make up your mind, here is a list of APIs that **need jsdom**:

* Any browser globals like `window` and `document`
* [`ReactDOM.render()`](http://u.720life.cn/g/2b5f360ced91899e6d7809fb5ee1ea1fbd77b72146743bf5b007101f454a72b8c939c99aafefd67e8d2b725a26ceb65bbdf1da4b07ab4014841f4f9ff99f8cb6803e8299f52ca007f46934f344509cfd) 
* [`TestUtils.renderIntoDocument()`](http://u.720life.cn/g/2b5f360ced91899e6d7809fb5ee1ea1fbd77b72146743bf5b007101f454a72b8a0a552eee41aadf22e8140d677ad4bf1f4edde64c8cf2cb139785b2adc670a0516b3b23fb8ca85104312af02cf0f0d2d)  ([a shortcut](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046405e3357754798ba3fdb28fb956ae71f75f3eb80172b06d2d29a1b2a9e35ad2d5cf060b5dc7442f372469b86ceea8f122fa0cacc851bbfb28ed81be54c9bab54a8739d29a84e021ff9f16f864508fcff2faf18033d8aa6d644f6f9e302d927c9be4a963c89485f6e149ab0ffa3272b49)  for the above)
* [`mount()`](http://u.720life.cn/g/6d563d09ad0079e975b69586273f66bf6646d7d253b01e87e507815f714f2a69c1c9aaa5647c1bf2901a75b876da610c)  in [Enzyme](http://u.720life.cn/g/6d563d09ad0079e975b69586273f66bfa901a5437504ac41a26ff89f599645d191761b6788b04255a0822dc066453804) 

In contrast, **jsdom is not needed** for the following APIs:

* [`TestUtils.createRenderer()`](http://u.720life.cn/g/2b5f360ced91899e6d7809fb5ee1ea1fbd77b72146743bf5b007101f454a72b8a0a552eee41aadf22e8140d677ad4bf18df402a255fbbb185871b5fe09ca828c71b6fcd94dc138bf597fe5db0f3e2da2)  (shallow rendering)
* [`shallow()`](http://u.720life.cn/g/6d563d09ad0079e975b69586273f66bf6646d7d253b01e87e507815f714f2a69aec05a3768394d59b3010d0a17d5f109)  in [Enzyme](http://u.720life.cn/g/6d563d09ad0079e975b69586273f66bfa901a5437504ac41a26ff89f599645d191761b6788b04255a0822dc066453804) 

Finally, jsdom is also not needed for [snapshot testing](http://u.720life.cn/g/cb6f6f5a71ffc3893ed7794d465226c9d8b941f27b34e9b0fb5480d8a24dcbd798051ea0799619d162dc6f80efd7fa0198baf7c0405dbad26f1ff6436284f95e 

### Snapshot Testing

Snapshot testing is a feature of Jest that automatically generates text snapshots of your components and saves them on the disk so if the UI output changes, you get notified without manually writing any assertions on the component output. [Read more about snapshot testing.](http://u.720life.cn/g/cb6f6f5a71ffc3893ed7794d465226c9d8b941f27b34e9b0fb5480d8a24dcbd798051ea0799619d162dc6f80efd7fa01f3dd841fc45eb5816e732543f7332fe6) 

### Editor Integration

If you use [Visual Studio Code](http://u.720life.cn/g/e2968b3acbb2cf55f957e5cee84b34f7bb82fcf1cf2ed3082c1f623f7d792c29  there is a [Jest extension](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046252dbcd9314277a97cea0943e4af09c7a461827b47461dca51f0e56ffda3c7b4)  which works with Create React App out of the box. This provides a lot of IDE-like features while using a text editor: showing the status of a test run with potential fail messages inline, starting and stopping the watcher automatically, and offering one-click snapshot updates.

![VS Code Jest Preview](https://cloud.githubusercontent.com/assets/49038/20795349/a032308a-b7c8-11e6-9b34-7eeac781003f.png)

## Debugging Tests

There are various ways to setup a debugger for your Jest tests. We cover debugging in Chrome and [Visual Studio Code](http://u.720life.cn/g/e2968b3acbb2cf55f957e5cee84b34f75da003dca7486006f36cf1298df80bdf 

>Note: debugging tests requires Node 8 or higher.

### Debugging Tests in Chrome

Add the following to the `scripts` section in your project's `package.json`
```json
"scripts": {
    "test:debug": "react-scripts --inspect-brk test --runInBand --env=jsdom"
  }
```
Place `debugger;` statements in any test and run:
```bash
$ npm run test:debug
```

This will start running your Jest tests, but pause before executing to allow a debugger to attach to the process.

Open the following in Chrome
```
about:inspect
```

After opening that link, the Chrome Developer Tools will be displayed. Select `inspect` on your process and a breakpoint will be set at the first line of the react script (this is done simply to give you time to open the developer tools and to prevent Jest from executing before you have time to do so). Click the button that looks like a "play" button in the upper right hand side of the screen to continue execution. When Jest executes the test that contains the debugger statement, execution will pause and you can examine the current scope and call stack.

>Note: the --runInBand cli option makes sure Jest runs test in the same process rather than spawning processes for individual tests. Normally Jest parallelizes test runs across processes but it is hard to debug many processes at the same time.

### Debugging Tests in Visual Studio Code

Debugging Jest tests is supported out of the box for [Visual Studio Code](http://u.720life.cn/g/e2968b3acbb2cf55f957e5cee84b34f7d8c8c2a0103ff0e24e8a4636fd3ef18b 

Use the following [`launch.json`](http://u.720life.cn/g/e2968b3acbb2cf55f957e5cee84b34f70806ab6c48549fa353e958bedf005cde7cfe4e90e6978a5a7d10a144d50836582fe2477a91033ae12750716876d4094fee50693b414a42bc980e072968fd37d5)  configuration file:
```
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug CRA Tests",
      "type": "node",
      "request": "launch",
      "runtimeExecutable": "${workspaceRoot}/node_modules/.bin/react-scripts",      
      "args": [
        "test",
        "--runInBand",
        "--no-cache",
        "--env=jsdom"
      ],
      "cwd": "${workspaceRoot}",
      "protocol": "inspector",
      "console": "integratedTerminal",
      "internalConsoleOptions": "neverOpen"
    }
  ]
}
```

## Developing Components in Isolation

Usually, in an app, you have a lot of UI components, and each of them has many different states.
For an example, a simple button component could have following states:

* In a regular state, with a text label.
* In the disabled mode.
* In a loading state.

Usually, it’s hard to see these states without running a sample app or some examples.

Create React App doesn’t include any tools for this by default, but you can easily add [Storybook for React](http://u.720life.cn/g/acdb25a3587a2079cd647a9f52ccbac018565ff43c9066e92fcf80701f2b85ee)  ([source](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469720cdba50b1fc6fc13d9bcab9709b9cfef3c20d856aa31afb09695e766e9f02)  or [React Styleguidist](http://u.720life.cn/g/f41393c365010d21085c86e050fbc98ddef44a6412cbd0dec59ff10bc659bdd2e5c5a4ec01b573bc6622d70523751503)  ([source](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046923be716f43b7d05a1a524f4cee9180adce8b642e62bc29489893ea16c60ea96af6ae41bb33718145cc37a758835f895)  to your project. **These are third-party tools that let you develop components and see all their states in isolation from your app**.

![Storybook for React Demo](http://i.imgur.com/7CIAWpB.gif)

You can also deploy your Storybook or style guide as a static app. This way, everyone in your team can view and review different states of UI components without starting a backend server or creating an account in your app.

### Getting Started with Storybook

Storybook is a development environment for React UI components. It allows you to browse a component library, view the different states of each component, and interactively develop and test components.

First, install the following npm package globally:

```sh
npm install -g @storybook/cli
```

Then, run the following command inside your app’s directory:

```sh
getstorybook
```

After that, follow the instructions on the screen.

Learn more about React Storybook:

* Screencast: [Getting Started with React Storybook](http://u.720life.cn/g/819f03fcd47662bedb6e69f3a50c916868f90a27d88103244dc8f561cdcef90bb7b1ef2db8da47fd8c5ea364086a588b72dccacb80063b44df859309331a3d7083636c195de9040c8b47f0a272ea9c60) 
* [GitHub Repo](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469720cdba50b1fc6fc13d9bcab9709b9cfef3c20d856aa31afb09695e766e9f02) 
* [Documentation](http://u.720life.cn/g/acdb25a3587a2079cd647a9f52ccbac06d348d96f72ce0e0b00a488c581fec67008d46c143fb49b973ea8ec1e9466ecc) 
* [Snapshot Testing UI](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469720cdba50b1fc6fc13d9bcab9709b9c84af89b4df6acdebb694ccb125c27e8a411c85ecd3df921984eb5902a72fa896a07f21ccaac452db57902e69edfdeab0)  with Storybook + addon/storyshot

### Getting Started with Styleguidist

Styleguidist combines a style guide, where all your components are presented on a single page with their props documentation and usage examples, with an environment for developing components in isolation, similar to Storybook. In Styleguidist you write examples in Markdown, where each code snippet is rendered as a live editable playground.

First, install Styleguidist:

```sh
npm install --save react-styleguidist
```

Alternatively you may use `yarn`:

```sh
yarn add react-styleguidist
```

Then, add these scripts to your `package.json`:

```diff
   "scripts": {
+    "styleguide": "styleguidist server",
+    "styleguide:build": "styleguidist build",
     "start": "react-scripts start",
```

Then, run the following command inside your app’s directory:

```sh
npm run styleguide
```

After that, follow the instructions on the screen.

Learn more about React Styleguidist:

* [GitHub Repo](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046923be716f43b7d05a1a524f4cee9180adce8b642e62bc29489893ea16c60ea96af6ae41bb33718145cc37a758835f895) 
* [Documentation](http://u.720life.cn/g/f41393c365010d21085c86e050fbc98ddef44a6412cbd0dec59ff10bc659bdd2091f53b534615573ae72f57d790fd4c0c6b71b01bb20bfa2c03d8e30799bbdb9) 

## Publishing Components to npm

Create React App doesn't provide any built-in functionality to publish a component to npm. If you're ready to extract a component from your project so other people can use it, we recommend moving it to a separate directory outside of your project and then using a tool like [nwb](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467226984f432a1c7f9a15714fabcd876f12955f6dfd35e9eca18182ec5ccc988a99f0477ace46104ed3e3d7f2333d5a21)  to prepare it for publishing.

## Making a Progressive Web App

By default, the production build is a fully functional, offline-first
[Progressive Web App](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b1484e35ecb871f7b46861103f5bd5be688056386b42cd2c5b13075091f410c7459ead15ec5a5cd751de5948d842000a45354 

Progressive Web Apps are faster and more reliable than traditional web pages, and provide an engaging mobile experience:

 * All static site assets are cached so that your page loads fast on subsequent visits, regardless of network connectivity (such as 2G or 3G). Updates are downloaded in the background.
 * Your app will work regardless of network state, even if offline. This means your users will be able to use your app at 10,000 feet and on the subway.
 * On mobile devices, your app can be added directly to the user's home screen, app icon and all. You can also re-engage users using web **push notifications**. This eliminates the need for the app store.

The [`sw-precache-webpack-plugin`](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046766ffbd9d732167fccff02d7ceabbe1952e2add21b92c80639e0df6db02562f9f017e05ebefcd4243313ee9e11d97d86) 
is integrated into production configuration,
and it will take care of generating a service worker file that will automatically
precache all of your local assets and keep them up to date as you deploy updates.
The service worker will use a [cache-first strategy](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b1484e35ecb871f7b46861103f5bd5be688050838441558743a0984cf794f8db2bf7b1101f5c848f8620c8753225ae1e963daa845716b361cc65bec9a897286ac6ae83502e05005d0b785dcf54495aa2ccba4ed32b61b75ae68ceff422c7299907fabbc8374be9d8ea017b13da8837d819bcc) 
for handling all requests for local assets, including the initial HTML, ensuring
that your web app is reliably fast, even on a slow or unreliable network.

### Opting Out of Caching

If you would prefer not to enable service workers prior to your initial
production deployment, then remove the call to `registerServiceWorker()`
from [`src/index.js`](src/index.js).

If you had previously enabled service workers in your production deployment and
have decided that you would like to disable them for all your existing users,
you can swap out the call to `registerServiceWorker()` in
[`src/index.js`](src/index.js) first by modifying the service worker import:
```javascript
import { unregister } from './registerServiceWorker';
```
and then call `unregister()` instead.
After the user visits a page that has `unregister()`,
the service worker will be uninstalled. Note that depending on how `/service-worker.js` is served,
it may take up to 24 hours for the cache to be invalidated.

### Offline-First Considerations

1. Service workers [require HTTPS](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b1484e35ecb871f7b46861103f5bd5be68805263a055ca3721d378078857685444161296b93f37995f144540fda8ba067131f01326cd4b9e3a01e5f2ba73a02c6121e6dfce305cb404aeffcd6df635d26f092ee0a0d0cee349f5697320bd0e97837b6 
although to facilitate local testing, that policy
[does not apply to `localhost`](http://u.720life.cn/g/ddb1c8aa997182cb1a4af16f7df394520a2863231ad8d7352308cd295ccf0ae9df40eb3b5e43d2dd8f4d547e26f927b1b1b17efb43de2f212973b53ff604642b6db6dbb43b6644354e44004de2418a289d84eab3a40d777ef92199a2ff3d2cf474d3a81426eabb0cb44d9a023681e3aa 
If your production web server does not support HTTPS, then the service worker
registration will fail, but the rest of your web app will remain functional.

1. Service workers are [not currently supported](http://u.720life.cn/g/316aec272f7bb8a09a1344623cec4a8b0b587f650d05c7a16a32d9cdecff0befea4709c6237535b3843af578e733d3f9f70bbf5e3f0b5ecbd78614d7a1870914) 
in all web browsers. Service worker registration [won't be attempted](src/registerServiceWorker.js)
on browsers that lack support.

1. The service worker is only enabled in the [production environment](#deployment),
e.g. the output of `npm run build`. It's recommended that you do not enable an
offline-first service worker in a development environment, as it can lead to
frustration when previously cached assets are used and do not include the latest
changes you've made locally.

1. If you *need* to test your offline-first service worker locally, build
the application (using `npm run build`) and run a simple http server from your
build directory. After running the build script, `create-react-app` will give
instructions for one way to test your production build locally and the [deployment instructions](#deployment) have
instructions for using other methods. *Be sure to always use an
incognito window to avoid complications with your browser cache.*

1. If possible, configure your production environment to serve the generated
`service-worker.js` [with HTTP caching disabled](http://u.720life.cn/g/ddb1c8aa997182cb1a4af16f7df394520a2863231ad8d7352308cd295ccf0ae92d27d3568a9c5f5d919b2270d07cd456d644f34ac3e8a654080f37c017a9441a70774961be349985d68fbb03d6b7313f4dd93c717c309f0199627ba6f9fd3f5bf122c4f0bdb4250055055d9bb8c836cd 
If that's not possible—[GitHub Pages](#github-pages), for instance, does not
allow you to change the default 10 minute HTTP cache lifetime—then be aware
that if you visit your production site, and then revisit again before
`service-worker.js` has expired from your HTTP cache, you'll continue to get
the previously cached assets from the service worker. If you have an immediate
need to view your updated production deployment, performing a shift-refresh
will temporarily disable the service worker and retrieve all assets from the
network.

1. Users aren't always familiar with offline-first web apps. It can be useful to
[let the user know](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b1484e35ecb871f7b46861103f5bd5be688050838441558743a0984cf794f8db2bf7b1101f5c848f8620c8753225ae1e963da6b2e13c426f696565c9aac954616af068dd464e229e0a8ac80586429d80b9a4a6b8db3b96c482d705c0b18df2942269e39f23ad38cabddf1340faff0bd42af6ebd82dd316e7ecf874f7973269ab8d741) 
when the service worker has finished populating your caches (showing a "This web
app works offline!" message) and also let them know when the service worker has
fetched the latest updates that will be available the next time they load the
page (showing a "New content is available; please refresh." message). Showing
this messages is currently left as an exercise to the developer, but as a
starting point, you can make use of the logic included in [`src/registerServiceWorker.js`](src/registerServiceWorker.js), which
demonstrates which service worker lifecycle events to listen for to detect each
scenario, and which as a default, just logs appropriate messages to the
JavaScript console.

1. By default, the generated service worker file will not intercept or cache any
cross-origin traffic, like HTTP [API requests](#integrating-with-an-api-backend),
images, or embeds loaded from a different domain. If you would like to use a
runtime caching strategy for those requests, you can [`eject`](#npm-run-eject)
and then configure the
[`runtimeCaching`](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046edf7f95b3e8ae89720551737a5709194f75329001e97ab73533ff15245dd9d9865a7023c4589e334158abea2f590ec5fe0691339ae6eb9707e84b92b7717474f) 
option in the `SWPrecacheWebpackPlugin` section of
[`webpack.config.prod.js`](../config/webpack.config.prod.js).

### Progressive Web App Metadata

The default configuration includes a web app manifest located at
[`public/manifest.json`](public/manifest.json), that you can customize with
details specific to your web application.

When a user adds a web app to their homescreen using Chrome or Firefox on
Android, the metadata in [`manifest.json`](public/manifest.json) determines what
icons, names, and branding colors to use when the web app is displayed.
[The Web App Manifest guide](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b1484e35ecb871f7b46861103f5bd5be68805ca835da44b30a80662a74ddc6fe0bbd5c196c909a7a861f8fd2a3ac4e1343e9e9447f317860ba14f2f914628c878528745d0969944c83a418acb7e9cbe8c383f) 
provides more context about what each field means, and how your customizations
will affect your users' experience.

## Analyzing the Bundle Size

[Source map explorer](http://u.720life.cn/g/920c024f0b8c5aa5e32c4f88af4e6c9610377e854f3c381f10e013c289c5f85c1e5758a7e11064a0765ebb48e71ded8c0fdbebeb26de2dd76bfd94e776ecc7be)  analyzes
JavaScript bundles using the source maps. This helps you understand where code
bloat is coming from.

To add Source map explorer to a Create React App project, follow these steps:

```sh
npm install --save source-map-explorer
```

Alternatively you may use `yarn`:

```sh
yarn add source-map-explorer
```

Then in `package.json`, add the following line to `scripts`:

```diff
   "scripts": {
+    "analyze": "source-map-explorer build/static/js/main.*",
     "start": "react-scripts start",
     "build": "react-scripts build",
     "test": "react-scripts test --env=jsdom",
```

Then to analyze the bundle run the production build then run the analyze
script.

```
npm run build
npm run analyze
```

## Deployment

`npm run build` creates a `build` directory with a production build of your app. Set up your favorite HTTP server so that a visitor to your site is served `index.html`, and requests to static paths like `/static/js/main. .js` are served with the contents of the `/static/js/main. .js` file.

### Static Server

For environments using [Node](http://u.720life.cn/g/6dd25ec2eceebbb6348ad519a7343cbc96da68e3c7ca91fcaf4d0eb7afdbd4be  the easiest way to handle this would be to install [serve](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046048b6601c64cad47e2902d1d36963e87)  and let it handle the rest:

```sh
npm install -g serve
serve -s build
```

The last command shown above will serve your static site on the port **5000**. Like many of [serve]https://github.com/zeit/serve)’s internal settings, the port can be adjusted using the `-p` or `--port` flags.

Run this command to get a full list of the options available:

```sh
serve -h
```

### Other Solutions

You don’t necessarily need a static server in order to run a Create React App project in production. It works just as fine integrated into an existing dynamic one.

Here’s a programmatic example using [Node](http://u.720life.cn/g/6dd25ec2eceebbb6348ad519a7343cbc690041c96fefc0320d9aace915151649)  and [Express](http://u.720life.cn/g/7e435bb7ea8b678eb5a90145f8db35585a9d4b668ee2d3b5780858d809b0b655 

```javascript
const express = require('express');
const path = require('path');
const app = express();

app.use(express.static(path.join(__dirname, 'build')));

app.get('/', function (req, res) {
  res.sendFile(path.join(__dirname, 'build', 'index.html'));
});

app.listen(9000);
```

The choice of your server software isn’t important either. Since Create React App is completely platform-agnostic, there’s no need to explicitly use Node.

The `build` folder with static assets is the only output produced by Create React App.

However this is not quite enough if you use client-side routing. Read the next section if you want to support URLs like `/todos/42` in your single-page app.

### Serving Apps with Client-Side Routing

If you use routers that use the HTML5 [`pushState` history API](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd1267fb2856419993d6af548deecc896cdd154d4aed08a81df814cbe98570cc96105f88daa00d07e97d57d874c1a60dfb02d33be22507c0d686abbc18a08fcbb8f1df0ed557b5c0d2de2204f4e5cb88f33b7)  under the hood (for example, [React Router](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046abfc9e2c5a0770adc9eacd501c47f8d0eddd3057a9e388b9694560c7e23738d5)  with `browserHistory`), many static file servers will fail. For example, if you used React Router with a route for `/todos/42`, the development server will respond to `localhost:3000/todos/42` properly, but an Express serving a production build as above will not.

This is because when there is a fresh page load for a `/todos/42`, the server looks for the file `build/todos/42` and does not find it. The server needs to be configured to respond to a request to `/todos/42` by serving `index.html`. For example, we can amend our Express example above to serve `index.html` for any unknown paths:

```diff
 app.use(express.static(path.join(__dirname, 'build')));

-app.get('/', function (req, res) {
+app.get('/*', function (req, res) {
   res.sendFile(path.join(__dirname, 'build', 'index.html'));
 });
```

If you’re using [Apache HTTP Server](http://u.720life.cn/g/a08b1c634b5423942b4cd1ad0fd35292f0d5342ab57b06c47292c60e0e3387bd  you need to create a `.htaccess` file in the `public` folder that looks like this:

```
    Options -MultiViews
    RewriteEngine On
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^ index.html [QSA,L]
```

It will get copied to the `build` folder when you run `npm run build`. 

If you’re using [Apache Tomcat](http://u.720life.cn/g/27381b9b9aecbc3251722641d01ac5ed995aafe8001a7e4be76e1363c22877cc  you need to follow [this Stack Overflow answer](http://u.720life.cn/g/87bbd50441ad714fa4b3a92b06a39057ddb1028a41fb686374235cc7501bbff9e22d484eab5bc410fbf3daf86e80e266 

Now requests to `/todos/42` will be handled correctly both in development and in production.

On a production build, and in a browser that supports [service workers](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b1484e35ecb871f7b46861103f5bd5be68805263a055ca3721d378078857685444161296b93f37995f144540fda8ba067131f01326cd4b9e3a01e5f2ba73a02c6121ea8e573ae53fa828df16cc09f36b2b390 
the service worker will automatically handle all navigation requests, like for
`/todos/42`, by serving the cached copy of your `index.html`. This
service worker navigation routing can be configured or disabled by
[`eject`ing](#npm-run-eject) and then modifying the
[`navigateFallback`](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046edf7f95b3e8ae89720551737a57091941fd8bad691888024ea9a84ccd8936d5c5181dc3ddc806457102bb2ad11dcb72856172e3db570a27e7c244e543a2be625) 
and [`navigateFallbackWhitelist`](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046edf7f95b3e8ae89720551737a57091941fd8bad691888024ea9a84ccd8936d5c3d75dc0aaf6fd3d41ca167b15008cbd25527e308b6f00d7e5bea9dec853737d2a4aa4a44307c5706ab4cd6b9f74aa849) 
options of the `SWPreachePlugin` [configuration](../config/webpack.config.prod.js).

When users install your app to the homescreen of their device the default configuration will make a shortcut to `/index.html`. This may not work for client-side routers which expect the app to be served from `/`. Edit the web app manifest at [`public/manifest.json`](public/manifest.json) and change `start_url` to match the required URL scheme, for example:

```js
  "start_url": ".",
```

### Building for Relative Paths

By default, Create React App produces a build assuming your app is hosted at the server root. 
To override this, specify the `homepage` in your `package.json`, for example:

```js
  "homepage": "http://mywebsite.com/relativepath",
```

This will let Create React App correctly infer the root path to use in the generated HTML file.

**Note**: If you are using `react-router@^4`, you can root ` `s using the `basename` prop on any ` `. 
More information [here](http://u.720life.cn/g/6dd236bd335a4bc6f1204a779143a888f8e3ba99d16ba137dc7748b06c322ad5ffec92a9976b73094bc7956aa7de462bdf44fbdaea5235ea33aa3d096d9a6db2b90857c60bf9b6192ff5a174b62fe01b  
 
For example:
```js
 
  // renders  
```

#### Serving the Same Build from Different Paths

>Note: this feature is available with `react-scripts@0.9.0` and higher.

If you are not using the HTML5 `pushState` history API or not using client-side routing at all, it is unnecessary to specify the URL from which your app will be served. Instead, you can put this in your `package.json`:

```js
  "homepage": ".",
```

This will make sure that all the asset paths are relative to `index.html`. You will then be able to move your app from `http://mywebsite.com` to `http://mywebsite.com/relativepath` or even `http://mywebsite.com/relative/path` without having to rebuild it.

### [Azure](http://u.720life.cn/g/08a23d9c242a0aac3f1ee3afc4f56dc227c8fabfe4ef4695e3f729087ab0e3f3) 

See [this](http://u.720life.cn/g/ce19288caac4b59057ec565c52ba1b3641d68a76ac96d9ec810b7d8cd32c75aec7d00d71aadb0479f1dd1b2e35d5c00c5a3280034f3d4f8b826157d4f74565215709edadbba60c869c51146e01441d938d7c92e99c7331db4ac841260250a42f)  blog post on how to deploy your React app to Microsoft Azure.

See [this](http://u.720life.cn/g/ce19288caac4b59057ec565c52ba1b3607dabdd15714c9155ae1ba72c2c26fd81f510db1dc4fb99f438a5d444203d369d1d5cb427320acc37af2486261a868bf7c02cb7a5ca62015c5ff748a89369459)  blog post or [this](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461977bd3fb8233fcddce922fbdf17fd24cf2f87c80161eedae57d804e59cbbcf65531ef4cd53a65cc0aa48ba5cd40df02)  repo for a way to use automatic deployment to Azure App Service.

### [Firebase](http://u.720life.cn/g/f79d1a8dd5c9917d7d53a1b53780521533c31454a55d2c147ea4a7a2bdd44979) 

Install the Firebase CLI if you haven’t already by running `npm install -g firebase-tools`. Sign up for a [Firebase account](http://u.720life.cn/g/c52c6a161526abefbb795fee00696d8cb1e07590f5cd707dca523a1e978184f867f7094f24c56648bf9198bc5d4b8b0d)  and create a new project. Run `firebase login` and login with your previous created Firebase account.

Then run the `firebase init` command from your project’s root. You need to choose the **Hosting: Configure and deploy Firebase Hosting sites** and choose the Firebase project you created in the previous step. You will need to agree with `database.rules.json` being created, choose `build` as the public directory, and also agree to **Configure as a single-page app** by replying with `y`.

```sh
    === Project Setup

    First, let's associate this project directory with a Firebase project.
    You can create multiple project aliases by running firebase use --add,
    but for now we'll just set up a default project.

    ? What Firebase project do you want to associate as default? Example app (example-app-fd690)

    === Database Setup

    Firebase Realtime Database Rules allow you to define how your data should be
    structured and when your data can be read from and written to.

    ? What file should be used for Database Rules? database.rules.json
    ✔  Database Rules for example-app-fd690 have been downloaded to database.rules.json.
    Future modifications to database.rules.json will update Database Rules when you run
    firebase deploy.

    === Hosting Setup

    Your public directory is the folder (relative to your project directory) that
    will contain Hosting assets to uploaded with firebase deploy. If you
    have a build process for your assets, use your build's output directory.

    ? What do you want to use as your public directory? build
    ? Configure as a single-page app (rewrite all urls to /index.html)? Yes
    ✔  Wrote build/index.html

    i  Writing configuration info to firebase.json...
    i  Writing project information to .firebaserc...

    ✔  Firebase initialization complete!
```

IMPORTANT: you need to set proper HTTP caching headers for `service-worker.js` file in `firebase.json` file or you will not be able to see changes after first deployment ([issue #2440](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f546df0c8608090fb3ef8c713a47f8c4eb3dae8c77664dc044da5dca6f04a6172e0  It should be added inside `"hosting"` key like next:

```
{
  "hosting": {
    ...
    "headers": [
      {"source": "/service-worker.js", "headers": [{"key": "Cache-Control", "value": "no-cache"}]}
    ]
    ...
```

Now, after you create a production build with `npm run build`, you can deploy it by running `firebase deploy`.

```sh
    === Deploying to 'example-app-fd690'...

    i  deploying database, hosting
    ✔  database: rules ready to deploy.
    i  hosting: preparing build directory for upload...
    Uploading: [==============================          ] 75%✔  hosting: build folder uploaded successfully
    ✔  hosting: 8 files uploaded successfully
    i  starting release process (may take several minutes)...

    ✔  Deploy complete!

    Project Console: https://console.firebase.google.com/project/example-app-fd690/overview
    Hosting URL: https://example-app-fd690.firebaseapp.com
```

For more information see [Add Firebase to your JavaScript Project](http://u.720life.cn/g/f79d1a8dd5c9917d7d53a1b5378052152226ef02911366709c63dff34793b2e6340660143d1223e5170ed881d0e10c21 

### [GitHub Pages](http://u.720life.cn/g/e74b692a81996e1b2ed64adb89491db2cd8ac94bc5280d15243938d18757b6f5) 

>Note: this feature is available with `react-scripts@0.2.0` and higher.

#### Step 1: Add `homepage` to `package.json`

**The step below is important!** 
**If you skip it, your app will not deploy correctly.**

Open your `package.json` and add a `homepage` field for your project:

```json
  "homepage": "https://myusername.github.io/my-app",
```

or for a GitHub user page:

```json
  "homepage": "https://myusername.github.io",
```

Create React App uses the `homepage` field to determine the root URL in the built HTML file.

#### Step 2: Install `gh-pages` and add `deploy` to `scripts` in `package.json`

Now, whenever you run `npm run build`, you will see a cheat sheet with instructions on how to deploy to GitHub Pages.

To publish it at [https://myusername.github.io/my-app](http://u.720life.cn/g/5d2114fa5d36427054287fb9aac0147cac4f825670ef77c37465f623a487afb0651fbd105b217b4343d3f81d55743e4d  run:

```sh
npm install --save gh-pages
```

Alternatively you may use `yarn`:

```sh
yarn add gh-pages
```

Add the following scripts in your `package.json`:

```diff
  "scripts": {
+   "predeploy": "npm run build",
+   "deploy": "gh-pages -d build",
    "start": "react-scripts start",
    "build": "react-scripts build",
```

The `predeploy` script will run automatically before `deploy` is run.

If you are deploying to a GitHub user page instead of a project page you'll need to make two
additional modifications:

1. First, change your repository's source branch to be any branch other than **master**.
1. Additionally, tweak your `package.json` scripts to push deployments to **master**:
```diff
  "scripts": {
    "predeploy": "npm run build",
-   "deploy": "gh-pages -d build",
+   "deploy": "gh-pages -b master -d build",
```

#### Step 3: Deploy the site by running `npm run deploy`

Then run:

```sh
npm run deploy
```

#### Step 4: Ensure your project’s settings use `gh-pages`

Finally, make sure **GitHub Pages** option in your GitHub project settings is set to use the `gh-pages` branch:

 

#### Step 5: Optionally, configure the domain

You can configure a custom domain with GitHub Pages by adding a `CNAME` file to the `public/` folder.

#### Notes on client-side routing

GitHub Pages doesn’t support routers that use the HTML5 `pushState` history API under the hood (for example, React Router using `browserHistory`). This is because when there is a fresh page load for a url like `http://user.github.io/todomvc/todos/42`, where `/todos/42` is a frontend route, the GitHub Pages server returns 404 because it knows nothing of `/todos/42`. If you want to add a router to a project hosted on GitHub Pages, here are a couple of solutions:

* You could switch from using HTML5 history API to routing with hashes. If you use React Router, you can switch to `hashHistory` for this effect, but the URL will be longer and more verbose (for example, `http://user.github.io/todomvc/#/todos/42?_k=yknaj`). [Read more](http://u.720life.cn/g/6dd236bd335a4bc6f1204a779143a888f8e3ba99d16ba137dc7748b06c322ad5f078dedacc93fb3844707fdf0f75614bae7a60b777e57fe580d74d18532a66ee)  about different history implementations in React Router.
* Alternatively, you can use a trick to teach GitHub Pages to handle 404 by redirecting to your `index.html` page with a special redirect parameter. You would need to add a `404.html` file with the redirection code to the `build` folder before deploying your project, and you’ll need to add code handling the redirect parameter to `index.html`. You can find a detailed explanation of this technique [in this guide](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304610474cac0b1c9a27eedaf211d967d6c3b36250d0273c9620b231245c52de695c 

### [Heroku](http://u.720life.cn/g/895de86c73bd84e81a31c257a763aaff1016065e57c4eaa331797e84e43170c8) 

Use the [Heroku Buildpack for Create React App](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d817ea0ce25ea78677e640df05b99a95fa9e97f1ca9d5e87d36c887f2a1a21f6a52d898f01fb272ecee8b6b26434068a  
You can find instructions in [Deploying React with Zero Configuration](http://u.720life.cn/g/099af8e2d404671dc75ad72aee7390a3b9393cd8089dd4f2eacaea613e298a9a086054d54a798451a75c5f47d4a02394ee592ac750c44e0719207be9020914df4d44fc2fab242713e8e32087eec7304a 

#### Resolving Heroku Deployment Errors

Sometimes `npm run build` works locally but fails during deploy via Heroku. Following are the most common cases.

##### "Module not found: Error: Cannot resolve 'file' or 'directory'"

If you get something like this:

```
remote: Failed to create a production build. Reason:
remote: Module not found: Error: Cannot resolve 'file' or 'directory'
MyDirectory in /tmp/build_1234/src
```

It means you need to ensure that the lettercase of the file or directory you `import` matches the one you see on your filesystem or on GitHub.

This is important because Linux (the operating system used by Heroku) is case sensitive. So `MyDirectory` and `mydirectory` are two distinct directories and thus, even though the project builds locally, the difference in case breaks the `import` statements on Heroku remotes.

##### "Could not find a required file."

If you exclude or ignore necessary files from the package you will see a error similar this one:

```
remote: Could not find a required file.
remote:   Name: `index.html`
remote:   Searched in: /tmp/build_a2875fc163b209225122d68916f1d4df/public
remote:
remote: npm ERR! Linux 3.13.0-105-generic
remote: npm ERR! argv "/tmp/build_a2875fc163b209225122d68916f1d4df/.heroku/node/bin/node" "/tmp/build_a2875fc163b209225122d68916f1d4df/.heroku/node/bin/npm" "run" "build"
```

In this case, ensure that the file is there with the proper lettercase and that’s not ignored on your local `.gitignore` or `~/.gitignore_global`.

### [Netlify](http://u.720life.cn/g/cc0437eea0449b9442ff80fba6617bf80b142636bcee59448c77c063cbcee05e) 

**To do a manual deploy to Netlify’s CDN:**

```sh
npm install netlify-cli -g
netlify deploy
```

Choose `build` as the path to deploy.

**To setup continuous delivery:**

With this setup Netlify will build and deploy when you push to git or open a pull request:

1. [Start a new netlify project](http://u.720life.cn/g/d73729f90a0b8627b2639f02a742cb2c11b22142ad06bad813ceacb138912297) 
2. Pick your Git hosting service and select your repository
3. Click `Build your site`

**Support for client-side routing:**

To support `pushState`, make sure to create a `public/_redirects` file with the following rewrite rules:

```
/*  /index.html  200
```

When you build the project, Create React App will place the `public` folder contents into the build output.

### [Now](http://u.720life.cn/g/efb73dc5227f5cfdbb7b960172088db5d9df371d206fd23166787f68c9e3d1e3) 

Now offers a zero-configuration single-command deployment. You can use `now` to deploy your app for free.

1. Install the `now` command-line tool either via the recommended [desktop tool](http://u.720life.cn/g/efb73dc5227f5cfdbb7b960172088db5f357e1f2e6796a2adabc2d7c4825be77)  or via node with `npm install -g now`.

2. Build your app by running `npm run build`.

3. Move into the build directory by running `cd build`.

4. Run `now --name your-project-name` from within the build directory. You will see a **now.sh** URL in your output like this:

    ```
    > Ready! https://your-project-name-tpspyhtdtk.now.sh (copied to clipboard)
    ```

    Paste that URL into your browser when the build is complete, and you will see your deployed app.

Details are available in [this article.](http://u.720life.cn/g/efb73dc5227f5cfdbb7b960172088db52510ecf9167477f420d0716ec1eba6316b6d06779ead4456025c1647e9ec1981) 

### [S3](http://u.720life.cn/g/27820330f4d197042ec05c336c0aab24200fab63ef77f4abd71523de5000f528)  and [CloudFront](http://u.720life.cn/g/27820330f4d197042ec05c336c0aab248e156f1f655519fa5a0c632a4c1c413c01104aa57789619630eb9b6148bbd2ed) 

See this [blog post](http://u.720life.cn/g/ce19288caac4b59057ec565c52ba1b36f93db33944dfed2170cd3d8e5f1f363940221fb4e76b43ae65754aee3434ce4e3d980ec338b772a0286dae6e2c031308b6f7dc00732672d3ec66de425005dc8d9895eccf074edd8900068ea9cca31d4a)  on how to deploy your React app to Amazon Web Services S3 and CloudFront.

### [Surge](http://u.720life.cn/g/8af7da1a982b1717ac9698329e8ab4b85cbc52d73fed8fc450ec6bc33c725ce9) 

Install the Surge CLI if you haven’t already by running `npm install -g surge`. Run the `surge` command and log in you or create a new account.

When asked about the project path, make sure to specify the `build` folder, for example:

```sh
       project path: /path/to/project/build
```

Note that in order to support routers that use HTML5 `pushState` API, you may want to rename the `index.html` in your build folder to `200.html` before deploying to Surge. This [ensures that every URL falls back to that file](http://u.720life.cn/g/8af7da1a982b1717ac9698329e8ab4b8e0f23f28d40270a8ad2d45b19a8c7cc5413a5e7dce21b804de1bf9866081dc219cd93b0278ba9b9466d29e24005fb218c3eaf67b8b015a4e68b280a13464423d 

## Advanced Configuration

You can adjust various development and production settings by setting environment variables in your shell or with [.env](#adding-development-environment-variables-in-env).

Variable | Development | Production | Usage
:--- | :---: | :---: | :---
BROWSER | :white_check_mark: | :x: | By default, Create React App will open the default system browser, favoring Chrome on macOS. Specify a [browser](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462a65f16275212ca6b7b7326d099e6667c7f6cb0edbaf612b61f84422b9a41e8c)  to override this behavior, or set it to `none` to disable it completely. If you need to customize the way the browser is launched, you can specify a node script instead. Any arguments passed to `npm start` will also be passed to this script, and the url where your app is served will be the last argument. Your script's file name must have the `.js` extension.
HOST | :white_check_mark: | :x: | By default, the development web server binds to `localhost`. You may use this variable to specify a different host.
PORT | :white_check_mark: | :x: | By default, the development web server will attempt to listen on port 3000 or prompt you to attempt the next available port. You may use this variable to specify a different port.
HTTPS | :white_check_mark: | :x: | When set to `true`, Create React App will run the development server in `https` mode.
PUBLIC_URL | :x: | :white_check_mark: | Create React App assumes your application is hosted at the serving web server's root or a subpath as specified in [`package.json` (`homepage`)](#building-for-relative-paths). Normally, Create React App ignores the hostname. You may use this variable to force assets to be referenced verbatim to the url you provide (hostname included). This may be particularly useful when using a CDN to host your application.
CI | :large_orange_diamond: | :white_check_mark: | When set to `true`, Create React App treats warnings as failures in the build. It also makes the test runner non-watching. Most CIs set this flag by default.
REACT_EDITOR | :white_check_mark: | :x: | When an app crashes in development, you will see an error overlay with clickable stack trace. When you click on it, Create React App will try to determine the editor you are using based on currently running processes, and open the relevant source file. You can [send a pull request to detect your editor of choice](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f54968a0bd443e5d8a7e8140a9613110dde3d970bb76674b4ad10915728bfed27d9  Setting this environment variable overrides the automatic detection. If you do it, make sure your systems [PATH](http://u.720life.cn/g/dbf1195f8a53209e138d24666db066366898267ffd7af6089b89681004c989b00a3551a42f8636641a1206e17746de40)  environment variable points to your editor’s bin folder. You can also set it to `none` to disable it completely.
CHOKIDAR_USEPOLLING | :white_check_mark: | :x: | When set to `true`, the watcher runs in polling mode, as necessary inside a VM. Use this option if `npm start` isn't detecting changes.
GENERATE_SOURCEMAP | :x: | :white_check_mark: | When set to `false`, source maps are not generated for a production build. This solves OOM issues on some smaller machines.
NODE_PATH | :white_check_mark: |  :white_check_mark: | Same as [`NODE_PATH` in Node.js](http://u.720life.cn/g/6dd25ec2eceebbb6348ad519a7343cbcf515d1b669a4f94f0ed2ec2a7868d80313b963f0a5459aed4a983b7b8cf937daf313f8553b623d0c25230d5a2eb3d56e4c2ee50909c273b9227f4ee065c6e3c4  but only relative folders are allowed. Can be handy for emulating a monorepo setup by setting `NODE_PATH=src`.

## Troubleshooting

### `npm start` doesn’t detect changes

When you save a file while `npm start` is running, the browser should refresh with the updated code. 
If this doesn’t happen, try one of the following workarounds:

* If your project is in a Dropbox folder, try moving it out.
* If the watcher doesn’t see a file called `index.js` and you’re referencing it by the folder name, you [need to restart the watcher](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f545dc7a8cb52aa4a2c1a3c39e2e3b650dc2f5d760db20a0a65b37525879e292b8b)  due to a Webpack bug.
* Some editors like Vim and IntelliJ have a “safe write” feature that currently breaks the watcher. You will need to disable it. Follow the instructions in [“Adjusting Your Text Editor”](http://u.720life.cn/g/f87b2d3c2d36bc68c43d51982df87eb3b4a1cb6bc27098c2a5b7f286be30ef9a3922a9d473bf958689548ab9db4050e761e5fb7b8063f11406d20fc7ab2c8b813c28e195112a1954a1762571bef05625 
* If your project path contains parentheses, try moving the project to a path without them. This is caused by a [Webpack watcher bug](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a20442f4ba6d4d9f2ebf4c2d6ccf2001429f364a9c49c9d253f13b10075b0441 
* On Linux and macOS, you might need to [tweak system settings](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ae1a35a67a9dd18bd62b3a41ece2ee78a91ec9844a62f722e8e8e0b14525762c4f8f165bccc039841c1586c859acba50a38e1b6855387d3603fa18cf8d02da16)  to allow more watchers.
* If the project runs inside a virtual machine such as (a Vagrant provisioned) VirtualBox, create an `.env` file in your project directory if it doesn’t exist, and add `CHOKIDAR_USEPOLLING=true` to it. This ensures that the next time you run `npm start`, the watcher uses the polling mode, as necessary inside a VM.

If none of these solutions help please leave a comment [in this thread](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f54cdd549125174a0725c2cfb26bf76b76967fc5fe0b031367fcbda0e2186e33eaf 

### `npm test` hangs on macOS Sierra

If you run `npm test` and the console gets stuck after printing `react-scripts test --env=jsdom` to the console there might be a problem with your [Watchman](http://u.720life.cn/g/2b5f360ced91899e6d7809fb5ee1ea1f9fc1412d9ca634fe66e2ff265d5984bd813d89210c9c3b1372d8da4c79bb269f)  installation as described in [facebookincubator/create-react-app#713](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f5446d57c489fb8e08b82dd08f5b533c905030ac273fe309cd85f4d3c3936244fa3 

We recommend deleting `node_modules` in your project and running `npm install` (or `yarn` if you use it) first. If it doesn't help, you can try one of the numerous workarounds mentioned in these issues:

* [facebook/jest#1767](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304632291197544a7ea7d219229703505bcf14cc41e0257e232008dd0f43847e4fcb) 
* [facebook/watchman#358](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f3507340c9cfc50545d87e9edaf026dde139fcbde97e5db6e2cc77a90e494141) 
* [ember-cli/ember-cli#6259](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463cbf6793f5edf84905e0a8bc25ed1f99c1b290e92a1e5914d09eb0a8e698f12b617c6c7c680bbbaa957efc9314c9809d) 

It is reported that installing Watchman 4.7.0 or newer fixes the issue. If you use [Homebrew](http://u.720life.cn/g/af2cb7974ba29ffbfd8647e25db79703fe8f782a472f679c5bc0eae46d1d2236  you can run these commands to update it:

```
watchman shutdown-server
brew update
brew reinstall watchman
```

You can find [other installation methods](http://u.720life.cn/g/2b5f360ced91899e6d7809fb5ee1ea1f9fc1412d9ca634fe66e2ff265d5984bdf88037ce1b430b14197c373d23f78952cfc9553f2a0c72453b1dee87825a57b2eed466553d08ce9e4e2650c34515a4fc)  on the Watchman documentation page.

If this still doesn’t help, try running `launchctl unload -F ~/Library/LaunchAgents/com.github.facebook.watchman.plist`.

There are also reports that *uninstalling* Watchman fixes the issue. So if nothing else helps, remove it from your system and try again.

### `npm run build` exits too early

It is reported that `npm run build` can fail on machines with limited memory and no swap space, which is common in cloud environments. Even with small projects this command can increase RAM usage in your system by hundreds of megabytes, so if you have less than 1 GB of available memory your build is likely to fail with the following message:

>  The build failed because the process exited too early. This probably means the system ran out of memory or someone called `kill -9` on the process.

If you are completely sure that you didn't terminate the process, consider [adding some swap space](http://u.720life.cn/g/93e30238e47de776c7e058ce98b95c6bebe0821448beb652bb83e5950d792d81cfedcf296a456463f78ed82c71a42aba68e3b04afd0c582682e5ef4cb24b0874e333b3eb87a5e64992ca18b981c42439)  to the machine you’re building on, or build the project locally.

### `npm run build` fails on Heroku

This may be a problem with case sensitive filenames.
Please refer to [this section](#resolving-heroku-deployment-errors).

### Moment.js locales are missing

If you use a [Moment.js](http://u.720life.cn/g/b53e731144faead411887fabafe8ed313aca4a51abc95e13522f20662d4f2c0b  you might notice that only the English locale is available by default. This is because the locale files are large, and you probably only need a subset of [all the locales provided by Moment.js](http://u.720life.cn/g/b53e731144faead411887fabafe8ed31d83320d890b469248d80bbde6276c6f2bd547b3ff2ffd8c670487d4bca28e08c 

To add a specific Moment.js locale to your bundle, you need to import it explicitly. 
For example:

```js
import moment from 'moment';
import 'moment/locale/fr';
```

If import multiple locales this way, you can later switch between them by calling `moment.locale()` with the locale name:

```js
import moment from 'moment';
import 'moment/locale/fr';
import 'moment/locale/es';

// ...

moment.locale('fr');
```

This will only work for locales that have been explicitly imported before.

### `npm run build` fails to minify

Some third-party packages don't compile their code to ES5 before publishing to npm. This often causes problems in the ecosystem because neither browsers (except for most modern versions) nor some tools currently support all ES6 features. We recommend to publish code on npm as ES5 at least for a few more years.

 
To resolve this:

1. Open an issue on the dependency's issue tracker and ask that the package be published pre-compiled.
  * Note: Create React App can consume both CommonJS and ES modules. For Node.js compatibility, it is recommended that the main entry point is CommonJS. However, they can optionally provide an ES module entry point with the `module` field in `package.json`. Note that **even if a library provides an ES Modules version, it should still precompile other ES6 features to ES5 if it intends to support older browsers**.

2. Fork the package and publish a corrected version yourself. 

3. If the dependency is small enough, copy it to your `src/` folder and treat it as application code.

In the future, we might start automatically compiling incompatible third-party modules, but it is not currently supported. This approach would also slow down the production builds.

## Alternatives to Ejecting

[Ejecting](#npm-run-eject) lets you customize anything, but from that point on you have to maintain the configuration and scripts yourself. This can be daunting if you have many similar projects. In such cases instead of ejecting we recommend to *fork* `react-scripts` and any other packages you need. [This article](http://u.720life.cn/g/09a13dac90e09367cfb9878ebb1b09f4d2cd1ebabe9238a5e34396cfa9682a1ac3b4d45d6ceea1ab32756cc3f730752c5b0085b90fc6ed20df722db719657e2a)  dives into how to do it in depth. You can find more discussion in [this issue](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f549d2956e680e70f069a299dec6f3c89596d8ff802e62110eff9b46c801b7be2a5 

## Something Missing?

If you have ideas for more “How To” recipes that should be on this page, [let us know](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f54a75c2cbd7bdec6bb20a3c911e95dfb70)  or [contribute some!](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046df8717a2e271b356693e11afc1c572c3e11a6ef44081b23fe8982a9906244f54c8bdbccd7a468c3a4379157ca880681e2a0b6b8eb2122f7ab38c5ba87ad3c3a762a5c8aa3cb8d02d63ed093f3beb091526211c3afea6cf3565f42816569285c4) 



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)