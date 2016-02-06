# cz-customizable


The customizable Commitizen plugin to help to have consistent commit messages like the [AngularJS team](https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#-git-commit-guidelines).

![screenshot](screenshot.png)

Suitable for large teams working with multiple projects with their own commit scopes. When you specify the scopes in your `.cz-config.js`, `cz-customizable` will allow you to **select** the pre-defined scopes. So no more scope spelling mistakes embarrassing you in your changelog file.

You can specify the commit types, scopes and override scopes for specific types. Please refer to Options secion bellow.



[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/) [![Build Status](https://travis-ci.org/leonardoanalista/cz-customizable.svg)](https://travis-ci.org/leonardoanalista/cz-customizable) [![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release) [![codecov.io](https://codecov.io/github/leonardoanalista/cz-customizable/coverage.svg?branch=master)](https://codecov.io/github/leonardoanalista/cz-customizable?branch=master) [![npm monthly downloads](https://img.shields.io/npm/dm/cz-customizable.svg?style=flat-square)](https://www.npmjs.com/package/cz-customizable)


## Steps:
* install commitizen in case you don't have it: `npm install -g commitizen`
* install the cz-customizable: `npm install cz-customizable --save-dev`
* configure `commitizen` to use `cz-customizable` as plugin. Add those lines to your `package.json`:
  ```
  ...
  "config": {
    "commitizen": {
      "path": "node_modules/cz-customizable"
    }
  }
  ```

* you should commit your `.cz-config.js` file to your git. 

* Run `cp ./node_modules/cz-customizable/cz-config-EXAMPLE.js ./.cz-config.js` in a project root directory to get a template.

** if you don't provide a config file, this adapter will use the contents of the default file `node_modules/cz-customizable/cz-config-EXAMPLE.js`


From now on, instead of `git commit` you type `git cz` and let the tool do the work for you.

Hopefully this will help you to have consistent commit messages and have a fully automated deployemnt without any human intervention.

## Options

Here are the options you can set in your `cz-config.js`

* scopes: {Array of Strings}: Specify the scopes for your particular project. Eg.: for some banking system: ["acccounts", "payments"]. For another travelling application: ["bookings", "search", "profile"]
* scopeOverrides: {}: 
```
  scopeOverrides: {
    fix: [
      {name: 'merge'},
      {name: 'style'},
      {name: 'e2eTest'},
      {name: 'unitTest'}
    ]
  }
  ```
  * allowCustomScopes: {boolean, default false}: adds the option `custom` to scope selection so you can still typea scope if you need.
  * allowBreakingChanges: {Array of Strings: default none}. List of commit types you would like to the question `breaking change` prompted. Eg.: ['feat', 'fix']


## Related tools:
- (https://github.com/commitizen/cz-cli)
- (https://github.com/stevemao/conventional-recommended-bump)
- (https://github.com/semantic-release/semantic-release)



## GOTCHAS

* backticks
If you wish to have backticks in your content, for example "feat: \`string\`", the commit preview will be "feat: \\\\`string\\\\`".
Don't worry because on your `git log` will be "feat: \`string\`" as desired.

* multiline contents on the body of the message
Body is the only place where you can use a `pipe` to break lines.
E.g.: you type this: `my items are:| - item01| - item 02`, which will become:


`my items are:`
 `- item01`
 `- item 02`



## CONTRIBUTING

Please refer to the [Contributor Guidelines](https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md) and [Conduct of Code](https://github.com/angular/code-of-conduct/blob/master/CODE_OF_CONDUCT.md) from [AngularJs](https://github.com/angular/angular.js) project.




Leonardo Correa
