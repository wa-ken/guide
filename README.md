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

# JS
## eslint
* https://github.com/eslint/eslint/tree/master/docs/rules

## coffeescript-style-guide(今後削除予定）
* https://github.com/polarmobile/coffeescript-style-guide

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

    ```Ruby
    # bad - need to consult first line to understand second line
    one.two.three.
      four

    # good - it's immediately clear what's going on the second line
    one.two.three
      .four
    ```

  * **(Option B)** When continuing a chained method invocation on another line,
    include the `.` on the first line to indicate that the
    expression continues.

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
    etc.

    ```Ruby
    # bad
    name = "Bozhidar"

    # good
    name = 'Bozhidar'
    ```

  * **(Option B)** Prefer double-quotes unless your string literal
    contains `"` or escape characters you want to suppress.

    ```Ruby
    # bad
    name = 'Bozhidar'

    # good
    name = "Bozhidar"
    ```

  The string literals in this guide are aligned with the first style.

