https://github.com/thoughtbot/guides

High level guidelines:

* Be consistent.
* Don't rewrite existing code to follow this guide.
* Don't violate a guideline without a good reason.
* A reason is good when you can convince a teammate.

A note on the language:

* "Avoid" means don't do it unless you have good reason.
* "Don't" means there's never a good reason.
* "Prefer" indicates a better option and its alternative to watch out for.
* "Use" is a positive instruction.

# Code Review
[Code Review](/code_review)

# CSS
BEMは将来性が乏しそうなので非採用。

## scss-lint
https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md
* BemDepth: disabled
* HexLength: short
* HexNotation: lowercase
* LeadingZero: include_zero
* NestingDepth: max_depth: 4
* SelectorDepth: max_depth: 2
* StringQuotes: double_quotes


## SMACSS
* https://smacss.com/
* https://smacss.com/ja (日本語版)

At the very core of SMACSS is categorization. By categorizing CSS rules, we begin to see patterns and can define better practices around each of these patterns.

There are five types of categories:

1. Base
2. Layout
3. Module
4. State
5. Theme

We often find ourselves mixing styles across each of these categories. If we are more aware of what we are trying to style, we can avoid the complexity that comes from intertwining these rules.

Each category has certain guidelines that apply to it. This somewhat succinct separation allows us to ask ourselves questions during the development process. How are we going to code things and why are we going to code them that way?

# JS
## eslint
https://github.com/eslint/eslint/tree/master/docs/rules
* disallow semicolons
```js
var name = "ESLint"
var website = "eslint.org";
```
* enforce double quotes
* indent: 2
* require let or const instead of var

The following patterns are considered problems:
```js
var x = "y";
var CONFIG = {};
```
The following patterns are not considered problems:
```js
let x = "y";
const CONFIG = {};
```

## coffeescript-style-guide(今後削除予定）
https://github.com/polarmobile/coffeescript-style-guide

# Rails
## rails-style-guide
* https://github.com/bbatsov/rails-style-guide
* https://github.com/satour/rails-style-guide/blob/master/README-jaJA.md (日本語版)

# Ruby
## ruby-style-guide 
* https://github.com/bbatsov/ruby-style-guide
* https://github.com/fortissimo1997/ruby-style-guide/blob/japanese/README.ja.md (日本語版)

### 複数のスタイル提案
* <a name="consistent-multi-line-chains"></a>
    Adopt a consistent multi-line method chaining style. There are two
    popular styles in the Ruby community, both of which are considered
    good - leading `.` (Option A) and trailing `.` (Option B).
<sup>[[link](#consistent-multi-line-chains)]</sup>

  * **(Option A)** When continuing a chained method invocation on
    another line keep the `.` on the second line.


  * **(Option B)** When continuing a chained method invocation on another line,
    include the `.` on the first line to indicate that the
    expression continues.**(使用中)**

    ```Ruby
    # bad - need to read ahead to the second line to know that the chain continues
    one.two.three
      .four

    # good - it's immediately clear that the expression continues beyond the first line
    one.two.three.
      four
    ```

  A discussion on the merits of both alternative styles can be found
  [here](https://github.com/bbatsov/ruby-style-guide/pull/176).

* <a name="consistent-string-literals"></a>
  Adopt a consistent string literal quoting style. There are two popular
  styles in the Ruby community, both of which are considered good - single
  quotes by default (Option A) and double quotes by default (Option B).
<sup>[[link](#consistent-string-literals)]</sup>

  * **(Option A)** Prefer single-quoted strings when you don't need
    string interpolation or special symbols such as `\t`, `\n`, `'`,
    etc.**(使用中)**

    ```Ruby
    # bad
    name = "Bozhidar"

    # good
    name = 'Bozhidar'
    ```

  * **(Option B)** Prefer double-quotes unless your string literal
    contains `"` or escape characters you want to suppress.

  The string literals in this guide are aligned with the first style.

