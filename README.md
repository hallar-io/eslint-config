<div align="center">
<h1>eslint-config</h1>

<p>These are my settings for ESLint and Prettier</p>
<p>You might like them - or you might not. Don't worry you can always change them.</p>
</div>

---

## Table of Contents

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Table of Contents](#table-of-contents)
- [Installation](#installation)
- [Usage](#usage)
  - [Other configs](#other-configs)
    - [React example](#react-example)
- [VS Code](#vs-code)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Installation

This module should be installed as one of your project's `devDependencies`:

```
npx install-peerdeps --dev eslint-config
```

## Usage

Then add the extends to your .eslintrc.js:

```js
module.exports = {
  extends: "hallar",
  rules: {
    // your overrides
  },
};
```

### Other configs

You can use other configs in combination with the main eslint.

```js
module.exports = {
  extends: ['hallar', 'hallar/<config-name>'],
}
```

#### React example

```js
module.exports = {
  extends: [
    'hallar',
    'hallar/react',
    'hallar/jsx-a11y',
  ],
  rules: {
    // your overrides
  },
};
```


## VS Code

Using the eslint-plugin you can use these settings for autoformatting:

```js
"editor.formatOnSave": true,
"eslint.format.enable": true,
  "[javascript]": {
"editor.formatOnSave": false,
  "editor.defaultFormatter": "dbaeumer.vscode-eslint"
},
"[javascriptreact]": {
  "editor.formatOnSave": false,
  "editor.defaultFormatter": "dbaeumer.vscode-eslint"
},
"[typescript]": {
  "editor.formatOnSave": false,
  "editor.defaultFormatter": "dbaeumer.vscode-eslint"
},
"[typescriptreact]": {
  "editor.formatOnSave": false,
  "editor.defaultFormatter": "dbaeumer.vscode-eslint"
},
"editor.codeActionsOnSave": {
  "source.fixAll": true,
}
```

## With JetBrains Products (IntelliJ IDEA, WebStorm, RubyMine, PyCharm, PhpStorm, etc)

If you have previously configured ESLint to run via a File Watcher, [turn that off.](https://www.jetbrains.com/help/idea/using-file-watchers.html#enableFileWatcher)

### If you choose Local / Per Project Install Above
1. Open ESLint configuration by going to File > Settings (Edit > Preferences on Mac) > Languages & Frameworks > Code Quality Tools > ESLint (optionally just search settings for "eslint")
1. Select **Automatic ESLint Configuration**
1. Check **Run eslint --fix on save**

### If you choose Global Install

The following steps are for a typical Node / ESLint global installtion.  If you have a customized setup, refer to JetBrains docs for more [ESLint Configuration Options](https://www.jetbrains.com/help/webstorm/eslint.html#ws_js_eslint_manual_configuration).

1. Open ESLint configuration by going to File > Settings (Edit > Preferences on Mac) > Languages & Frameworks > Code Quality Tools > ESLint (optionally just search settings for "eslint")
1. Select **Manual ESLint configuration**
1. Choose your **Node interpreter** from the detected installations
1. Select the global **ESLint package** from the dropdown
1. Leave Configuration File as **Automatic Search**
1. Check **Run eslint --fix on save**

### Ensure the Prettier plugin is disabled if installed.

1. Open Prettier configuration by going to File > Settings (Edit > Preferences on Mac) > Languages & Frameworks > Code Quality Tools > Prettier (optionally just search settings for "prettier")
1. Uncheck both **On code reformat** and **On save**
1. *Optional BUT IMPORTANT:* If you have the Prettier extension enabled for other languages like CSS and HTML, turn it off for JS since we are doing it through Eslint already.
    1. Make sure the **Run for files** glob does not include `js,ts,jsx,tsx`.
    2. An example glob for styles, config, and markdown. `{**/*,*}.{yml,css,sass,md}`
