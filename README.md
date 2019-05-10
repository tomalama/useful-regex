# Useful Regex

## Convert CommonJS modules to ES6 modules

### Find

```
const ({?)(([^;}]|\n)*)(}?) = require\((.*)\);
```

### Replace

```
import $1$2$4 from $5;
```

## Convert ES6 modules to CommonJS modules

### Find

```
import ({?)(([^;}]|\n)*)(}?) from (.*);
```

### Replace

```
const $1$2$4 = require($5);
```
