# Oxlint Configuration File

This configuration is aligned with ESLint v8's configuration schema (`eslintrc.json`).

Usage: `oxlint -c oxlintrc.json --import-plugin`

::: danger NOTE

Only the `.json` format is supported. You can use comments in configuration files.

:::

Example

```json [.oxlintrc.json]
{
  "env": {
    "browser": true
  },
  "globals": {
    "foo": "readonly"
  },
  "settings": {},
  "rules": {
    "eqeqeq": "warn",
    "import/no-cycle": "error"
  }
}
```

## env

type: `object`

Predefine global variables.

Environments specify what global variables are predefined. See [ESLint's list of environments](https://eslint.org/docs/v8.x/use/configure/language-options#specifying-environments) for what environments are available and what each one provides.

## globals

type: `object`

Add or remove global variables.

For each global variable, set the corresponding value equal to `"writable"` to allow the variable to be overwritten or `"readonly"` to disallow overwriting.

Globals can be disabled by setting their value to `"off"`. For example, in an environment where most Es2015 globals are available but `Promise` is unavailable, you might use this config:

```json
{
  "env": {
    "es6": true
  },
  "globals": {
    "Promise": "off"
  }
}
```

You may also use `"readable"` or `false` to represent `"readonly"`, and `"writeable"` or `true` to represent `"writable"`.

## plugins

type: `array`

### plugins[n]

type: `string`

## rules

type: `object`

See [Oxlint Rules](https://oxc.rs/docs/guide/usage/linter/rules.html)

## settings

type: `object`

Shared settings for plugins

### settings.jsdoc

type: `object`

#### settings.jsdoc.augmentsExtendsReplacesDocs

type: `boolean`

Only for `require-(yields|returns|description|example|param|throws)` rule

#### settings.jsdoc.exemptDestructuredRootsFromChecks

type: `boolean`

Only for `require-param-type` and `require-param-description` rule

#### settings.jsdoc.ignoreInternal

type: `boolean`

For all rules but NOT apply to `empty-tags` rule

#### settings.jsdoc.ignorePrivate

type: `boolean`

For all rules but NOT apply to `check-access` and `empty-tags` rule

#### settings.jsdoc.ignoreReplacesDocs

type: `boolean`

Only for `require-(yields|returns|description|example|param|throws)` rule

#### settings.jsdoc.implementsReplacesDocs

type: `boolean`

Only for `require-(yields|returns|description|example|param|throws)` rule

#### settings.jsdoc.overrideReplacesDocs

type: `boolean`

Only for `require-(yields|returns|description|example|param|throws)` rule

#### settings.jsdoc.tagNamePreference

type: `object`

### settings.jsx-a11y

type: `object`

#### settings.jsx-a11y.components

type: `object`

#### settings.jsx-a11y.polymorphicPropName

type: `[
  string,
  null
]`

### settings.next

type: `object`

#### settings.next.rootDir

### settings.react

type: `object`

#### settings.react.formComponents

type: `array`

##### settings.react.formComponents[n]

#### settings.react.linkComponents

type: `array`

##### settings.react.linkComponents[n]
