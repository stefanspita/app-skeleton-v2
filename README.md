# app-skeleton-v2
Front-end site skeleton

## Steps I took to create it
1) Install Node
- Go through the standard installation of Node for your operating system: https://nodejs.org/en/download/
- I would always choose the LTS version (long term support). The latest version is less stable, so only use it if you are an advanced user or you are interested in trying out experimental features
- Restart your command line if you had it open
- At the end of the installation you should be able to run `node --version` from your command line and get the version number you had just installed. Please ask me for help if you haven't. This is an important step to get right. Not installing Node with the right permissions or in the right place will greatly affect your development experience

2) Create a git repository
- Add a new repository in your github account, using the github interface
- clone your repository using `git clone git@github.com:[github-username]/[repository-name]`

3) Initialize npm
- in your command line, navigate into your newly cloned repository and run `npm init`. Complete the wizard that follows. If you're not sure what any of the questions mean, just press ENTER to use the default recommended values.

4) Create `.gitignore` file
- The folders and files defined in this file will not be pushed to github. This can be for several reasons:
  - The `node_modules` and the `dist` folders are never pushed to github because they contain the code for all dependencies your project needs to install and the compiled code, respectively. The dependencies are managed through the `package.json` and `package-lock.json` files. Including the whole `node_modules` folder into your github project will take a lot space and considerably increase the time it takes to pull and push changes to/from github.
  - Other files/folders might only be relevant to your local setup (for example the text editor `Webstorm` stores project indexes in a folder called `.idea`). These are not relevant to any other computer/server your code might be running on.

5) Set up Webpack, React and Babel according to this tutorial: https://blog.usejournal.com/setting-up-react-webpack-4-babel-7-from-scratch-2019-b771dca2f637
- Webpack is a bundler. It takes all your code and the dependencies you use and bundles them into files the browser runs efficiently.
- React is a small framework that helps split up the display and logic code. Ultimately, it will help manage a large application.
- Babel is a JavaScript compiler. It lets you use the latest features of the JavaScript language on older browsers by compiling ES6 (latest JavaScript) into ES5 (Vanilla JavaScript). Webpack is configured to run Babel on your code automatically

6) Set up code linting
- This is a more advanced concept and understanding it is optional if you're new to JavaScript
- Code linting helps maintain the code style across your codebase, while also catching most typos and bugs in your code. Normally, the team working on a project decides on the code style they want to use by choosing `eslint` rules from here: https://eslint.org/docs/rules/ and including them in an `.eslintrc` file in the main folder of the repository.
- Alternatively, you can use a set of rules created by other companies. The industry standard is airbnb: https://www.npmjs.com/package/eslint-config-airbnb
- For this project, I've installed a simpler set of rules published by the company I work for: https://github.com/moneyhub/eslint-config-momentumft/blob/master/react.js
- This set of rules depends on a few other dependencies being installed:
  - `eslint` is the package that checks if the code matches the rules defined in the `.eslintrc` file of the project
  - `babel-eslint` lets `eslint` know the codebase is written in Babel syntax
  - `eslint-plugin-react` - set of `eslint` rules for a `React` project. It includes a set of recommended linting rules for a `React` based project
- When using `eslint` I would also recommend installing the `eslint` plugin into your choice of editor and enable the `autofix` option. This option enables your editor to adjust your code to match the linting rules whenever you save a file. These auto adjustments are completely safe and they won't change the way your code works. When issues in your code can't be fixed automatically, they will be left alone for you to fix
