# `prism-console`

> [Prism](https://www.npmjs.com/package/prismjs) but outputs to the browser console.

## Example

The following code, when run in a browser, displays the output in this image in the browser console:

```javascript
import { generateTheme, highlight } from "prism-console";
import Prism from "prismjs";

const theme = generateTheme(...);

console.log(
  ...highlight(
    `import { generateTheme, highlight } from "prism-console"`,
    Prism.languages.javascript,
    theme
  )
);

console.log(
  ...highlight(
    `.token.deleted {
  color: red;
}`,
    Prism.languages.css,
    theme
  )
);
```

![syntax highlighted code](https://raw.githubusercontent.com/tomblcode/prism-console/master/example.png)

## API

### `generateTheme(stylesheet: string): Theme`

`stylesheet` is the CSS source for the Prism theme.

### `highlight(code: string, grammar: Prism.Grammar, theme: Theme): string[]`

`code` is the code to be highlighted.

`grammar` A [Prism](https://prismjs.com) language grammar, typically taken from `Prism.languages`.

`theme` is the theme to highlight the code with, generated by `generateTheme`.

`highlight` returns an array of arguments to be passed to any function in the `console.log` family.
