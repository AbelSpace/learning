# Eslint

## Local Installation and Usage

If you want to include ESLint as part of your project’s build system, we recommend installing it locally. You can do so using npm:

`$ npm install eslint --save-dev`

You should then setup a configuration file:

`$ ./node_modules/.bin/eslint --init`

After that, you can run ESLint in your project’s root directory like this:

`$ ./node_modules/.bin/eslint yourfile.js`

`> npm install -g eslint-cli` can help you using local eslint directly.

## Global Installation and Usage

If you want to make ESLint available to tools that run across all of your projects, we recommend installing ESLint globally. You can do so using npm:

`$ npm install -g eslint`

You should then setup a configuration file:

`$ eslint --init`

After that, you can run ESLint on any file or directory like this:

`$ eslint yourfile.js`

## Command Line Interface

`npm i -g eslint`

This installs the ESLint CLI from the npm repository. To run ESLint, use the following format:

`eslint [options] [file|dir|glob]*`

such as:

`eslint file1.js file2.js`

or:

`eslint lib/**`

*Please note that when passing a glob as a parameter, it will be expanded by your shell. The results of the expansion can vary depending on your shell, and its configuration. If you want to use [node glob syntax](https://github.com/isaacs/node-glob), you have to quote your parameter (using double quotes if you need it to run in Windows), as follows:*

`eslint "lib/**"`

Unfortunately, our `--ext` CLI option is only really used when you specify a directory and ESLint needs to figure out what files to lint in that directory. By specifying a glob pattern, that logic is bypassed: Either because your shell is expanding the glob and sending a list of files to ESLint, or because ESLint sees the glob.

You have two options: use a directory (`eslint src --ext js ...`), or use a more specific glob (`eslint "src/**/*.js" ...`).

I highly recommend quoting a glob pattern to avoid your shell expanding the glob, especially if you want to put this command in an npm script or otherwise distribute it in a project.

- `eslint --ext js webapp`
- `eslint webapp`
- `eslint webapp --ext js`
  
  Above three are same.

  Below is wrong usage, will include other type files, event you set `--ext js` like `eslint --ext js webapp/**`

  ```shell
  eslint webapp/**
  eslint webapp/**/*
  ```

- `eslint webapp/**/*.js`
- `eslint "webapp/**/*.js"`

## Configuration Cascading and Hierarchy
When using `.eslintrc.*` and `package.json` files for configuration, you can take advantage of configuration cascading. For instance, suppose you have the following structure:

```tree
your-project
├── .eslintrc
├── lib
│ └── source.js
└─┬ tests
  ├── .eslintrc
  └── test.js
```

The configuration cascade works by using the closest `.eslintrc` file to the file being linted as the highest priority, then any configuration files in the parent directory, and so on. When you run ESLint on this project, all files in lib/ will use the `.eslintrc` file at the root of the project as their configuration. When ESLint traverses into the tests/ directory, it will then use your-project/tests/.eslintrc in addition to your-project/.eslintrc. So your-project/tests/test.js is linted based on the **combination** of the two `.eslintrc` files in its directory hierarchy, with the closest one taking priority. In this way, you can have project-level ESLint settings and also have directory-specific overrides.