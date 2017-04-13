# GoAbout Javascript Styleguide + ESLint config

This package provides GoAbout's base JS .eslintrc as an extensible shared config. It uses [AirBnB's config](https://github.com/airbnb/javascript) as a base with a few differences.

The main differences are

* semicolons are not necessary;
* Most errors changed to warnings. Because "errors" prevent webpack-compiled code from running and hence provide unnecessary point of distraction while writing the code. Warnings are still visible and can be fixed later;

## Usage

Our default export contains all of our ESLint rules, including ECMAScript 6+. It requires `eslint` and `eslint-plugin-import`.

1. Install the correct versions of each package using `npm` by adding in packages.json:

  ```
    "goabout-eslint-config": "...path to github repo..."
  ```


2. Add `"extends": "node_modules/goabout-eslint-config/index.js"` to your `.eslintrc`


## Extending rules

Feel free to rewrite rules or extend them using your own `.eslintrc`. Like that:

```
// add your custom rules here
'rules': {
  // allow paren-less arrow functions
  'arrow-parens': 0,
  // allow async-await
  'generator-star-spacing': 0
}
```

## Improving this config

Consider adding test cases if you're making complicated rules changes, like anything involving regexes. Perhaps in a distant future, we could use literate programming to structure our README as test cases for our .eslintrc?

You can run tests with `npm test`.

You can make sure this module lints with itself using `npm run lint`.
