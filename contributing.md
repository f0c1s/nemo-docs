# Nemo Contribution Guidelines

## Support strategy

## Git branching strategy

All modules will have the following branches:

* `develop` branch for active development
* `master` branch representing most recent release
* `X.X-release` branches, which will be cut from master each time a new `X.X` release is made

## Version tagging

Contributors must NOT modify version numbers. Repository owners will manage versioning and tagging releases.

## Code review policy

* Changes must be submitted as pull requests into `develop` and/or `X.X-release` branches from the contributor's fork of
the module
* Integration build for the PR must pass
* Code must be reviewed by *at least* one repository owner
* All comments must be addressed by the contributor

Once all of these are satisfied, code can be merged.

## Code style

The opinion of the author is style is contextual. If you are working in established code, follow the style you find there. 
Some simple principles to observe:

### Don't be "cute"

This essentially means, don't write terse code for the sake of brevity. Write enough lines of code for the intent of the code to
be clear. Nobody should have to unwind clever usage of bitwise operators, or figure out that you've used the function signature
to shortcut the var declaration (cute people know what I'm talking about).

### Object naming

* camelCase names. Do not title_case
* provide meaningful semantic names. Don't try to save bytes.
* observe verb-noun naming of functions (e.g. `getConfig`, `setValue`, `resolveViewName`)
* only capitalize constructor or factory function names

### Strings

Unless you are coding a JSON file, use single quotes.

### Indentation

Use 2 spaces per tab

### General formatting

All modules should validate against the following `jshintrc` file:

```
{
  // Whether the scan should stop on first error.
  "passfail": false,
  // Maximum errors before stopping.
  "maxerr": 100,


  // Predefined globals

  // Whether the standard browser globals should be predefined.
  "browser": false,
  // Whether the Node.js environment globals should be predefined.
  "node": true,
  // Whether the Rhino environment globals should be predefined.
  "rhino": false,
  // Whether CouchDB globals should be predefined.
  "couch": false,
  // Whether the Windows Scripting Host environment globals should be predefined.
  "wsh": false,

  // Whether jQuery globals should be predefined.
  "jquery": false,
  // Whether Prototype and Scriptaculous globals should be predefined.
  "prototypejs": false,
  // Whether MooTools globals should be predefined.
  "mootools": false,
  // Whether Dojo Toolkit globals should be predefined.
  "dojo": false,

  // Custom predefined globals.
  "predef": [],

  // Development

  // Whether debugger statements should be allowed.
  "debug": false,
  // Whether logging globals should be predefined (console, alert, etc.).
  "devel": false,


  // ECMAScript 5

  // Whether the "use strict"; pragma should be required.
  "strict": true,
  // Whether global "use strict"; should be allowed (also enables strict).
  "globalstrict": true,


  // The Good Parts

  // Whether automatic semicolon insertion should be allowed.
  "asi": false,
  // Whether line breaks should not be checked, e.g. `return [\n] x`.
  "laxbreak": false,
  // Whether bitwise operators (&, |, ^, etc.) should be forbidden.
  "bitwise": false,
  // Whether assignments inside `if`, `for` and `while` should be allowed. Usually
  // conditions and loops are for comparison, not assignments.
  "boss": true,
  // Whether curly braces around all blocks should be required.
  "curly": true,
  // Whether `===` and `!==` should be required (instead of `==` and `!=`).
  "eqeqeq": true,
  // Whether `== null` comparisons should be allowed, even if `eqeqeq` is `true`.
  "eqnull": false,
  // Whether `eval` should be allowed.
  "evil": false,
  // Whether ExpressionStatement should be allowed as Programs.
  "expr": true,
  // Whether `for in` loops must filter with `hasOwnPrototype`.
  "forin": false,
  // Whether immediate invocations must be wrapped in parens, e.g.
  // `( function(){}() );`.
  "immed": true,
  // Whether use before define should be forbidden.
  "latedef": false,
  // Whether functions should be allowed to be defined within loops.
  "loopfunc": false,
  // Whether arguments.caller and arguments.callee should be forbidden.
  "noarg": false,
  // Whether `.` should be forbidden in regexp literals.
  "regexp": false,
  // Whether unescaped first/last dash (-) inside brackets in regexps should be allowed.
  "regexdash": false,
  // Whether script-targeted URLs should be allowed.
  "scripturl": false,
  // Whether variable shadowing should be allowed.
  "shadow": false,
  // Whether `new function () { ... };` and `new Object;` should be allowed.
  "supernew": false,
  // Whether variables must be declared before used.
  "undef": true,
  // Whether `this` inside a non-constructor function should be allowed.
  "validthis": false,
  // Whether smarttabs should be allowed
  // (http://www.emacswiki.org/emacs/SmartTabs).
  "smarttabs": false,
  // Whether the `__proto__` property should be allowed.
  "proto": false,
  // Whether one-case switch statements should be allowed.
  "onecase": false,
  // Whether non-standard (but widely adopted) globals should be predefined.
  "nonstandard": false,
  // Allow multiline strings.
  "multistr": false,
  // Whether line breaks should not be checked around commas.
  "laxcomma": false,
  // Whether semicolons may be ommitted for the trailing statements inside of a
  // one-line blocks.
  "lastsemic": false,
  // Whether the `__iterator__` property should be allowed.
  "iterator": false,
  // Whether only function scope should be used for scope tests.
  "funcscope": false,
  // Whether es.next specific syntax should be allowed.
  "esnext": false,


  // Style preferences

  // Whether constructor names must be capitalized.
  "newcap": false,
  // Whether empty blocks should be forbidden.
  "noempty": false,
  // Whether using `new` for side-effects should be forbidden.
  "nonew": false,
  // Whether names should be checked for leading or trailing underscores
  // (object._attribute would be forbidden).
  "nomen": false,
  // Whether only one var statement per function should be allowed.
  "onevar": false,
  // Whether increment and decrement (`++` and `--`) should be forbidden.
  "plusplus": false,
  // Whether all forms of subscript notation are allowed.
  "sub": false,
  // Whether trailing whitespace rules apply.
  "trailing": false,
  // Specify indentation.
  "indent": 2,
  // Whether strict whitespace rules apply.
  "white": false,
  // Quote formatting
  "quotmark": true,

  // Complexity

  // Maximum number of function parameters.
  "maxparams": 5,
  // Maximum block nesting depth.
  "maxdepth": 4,
  // Maximum number of statements per function.
  "maxstatements": 25,
  // Maximum cyclomatic complexity.
  "maxcomplexity": 6
}

```
