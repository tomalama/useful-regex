# Useful Regex

Regular expressions to make converting from CommonJS to ES6 or ES6 to CommonJS easier.

## Regular Expressions

### Convert CommonJS modules to ES6 modules

Find:

```
const ({?)(([^;}]|\n)*)(}?) = require\((.*)\);
```

Replace:

```
import $1$2$4 from $5;
```

### Convert ES6 modules to CommonJS modules

Find:

```
import ({?)(([^;}]|\n)*)(}?) from (.*);
```

Replace:

```
const $1$2$4 = require($5);
```

## Usage

### VSCode

Using these regular expressions require an extra setting in VSCode. Add the following to `<project_root>/.vscode/settings.json`.

```json
{
  "search.usePCRE2": true
}
```
