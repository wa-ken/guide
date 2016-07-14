# INTERFIRM Coding Guide

> あくまでガイドラインです。これに則ることを強制するものではありません。

<https://github.com/thoughtbot/guides>

High level guidelines:

* Be consistent.
* Avoid rewrite existing code to follow this guide.
* Don't violate a guideline without a good reason.
* A reason is good when you can convince a teammate.

A note on the language:

* "Avoid" means don't do it unless you have good reason.
* "Don't" means there's never a good reason.
* "Prefer" indicates a better option and its alternative to watch out for.
* "Use" is a positive instruction.

# Table of Contents

* [Code Review](#code-review)
* [CSS](#css)
    * [scss-lint](#scss-lint)
    * [SMACSS](#smacss)
    * [Module](#module)
* [JavaScript](#javascript)
    * [ESLint](#eslint)
    * [React](#react)
* [Rails](#rails)
    * [rails-style-guide](#rails-style-guide)
* [Ruby](#ruby)
    * [ruby-style-guide](#ruby-style-guide)

# Code Review

<https://github.com/thoughtbot/guides/tree/master/code-review>

* レビュー後のコメントを最初にする人は、リアクションではなくコメントを使いましょう（通知が送られないため）
* CSSやテキストのみの改修の場合、CIをスキップする判断もOK
* 顔を合わせてのディスカッションが必要な場合は、週ごとの振り返り会（現在は木曜日開催）で行いましょう。

# CSS

BEMは将来性が乏しそうなので非採用。

## scss-lint

<https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md>

* BemDepth: disabled

BEMは非採用なので、無視します。

* HexLength: short

```scss
// short
color: #f2e;

// long
color: #ff22ee;
```

* HexNotation: lowercase

Checks if hexadecimal colors are written in lowercase. You can specify which case with the style option.
hexの指定は小文字で記述してください。

* LeadingZero: include_zero

```scss
// unnecessary leading zero
margin: 0.5em;

// no leading zero
margin: .5em;
```

* NestingDepth: max_depth: 4
* SelectorDepth: max_depth: 2
* StringQuotes: double_quotes

```scss
// double quotes
content: "hello";
```

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

## Module

<http://demo.patternlab.io/>

各プロジェクトで、デザインパーツを集めたページを作れるといいのではないでしょうか。

# JavaScript

## ESLint

<http://eslint.org/docs/rules>

* disallow semicolons (行末のセミコロンは使用しない)

See <http://eslint.org/docs/rules/semi>.

* enforce double quotes (ダブルクォートを用いる)

See <http://eslint.org/docs/rules/quotes>.

* indent: 2 (インデントはスペース2つ)

See <http://eslint.org/docs/rules/indent>.

* require let or const instead of var (`var` の代わりに `let` または `const` を用いる)

See <http://eslint.org/docs/rules/no-var>.

## coffeescript-style-guide(今後削除予定）

<https://github.com/polarmobile/coffeescript-style-guide>

## React

* 拡張子は `*.js`

    :no_good: `comment.jsx`

    :ok_woman: `comment.js`

* 複数形は曖昧なので使わない

    :no_good: `class Comments` (`comments.js`)

    :ok_woman: `class CommentList` (`comment_list.js`)

* コンテナは `*Box` (`*_box.js`)

    :no_good: `class CommentContainer` (`comment_container.js`)

    :ok_woman: `class CommentBox` (`comment_box.js`)

* テストライブラリ
    * Mocha (TDDスタイル): <https://mochajs.org/#tdd>
    * Chai (assertスタイル): <http://chaijs.com/api/assert/>
    * Sinon: <http://sinonjs.org/docs/>
    * Enzyme: <http://airbnb.io/enzyme/docs/api>

* テストガイド

**なぜテストをするのか (Why)**

> 期待通りにコンポーネントが動いているという確信が得られますし、後で自信を持ってリファクタリングを行えます。

**どのようにテストを行うのか (How)**

> 私たちが多用するテクニックは、シャローレンダリングです。

> シャローレンダリングを使うと、どのように子コンポーネントが実装されているかを気にする必要がなくなるため、シャローレンダリングはとても有効な方法です。

**何をテストするのか (What)**

> 必ずレンダリングされること

> アウトプットをテストする

> 状態をテストする

> イベントをテストする

> エッジケースをテストする

from <http://postd.cc/getting-started-with-tdd-in-react>.

* 参考
    * <https://facebook.github.io/react/docs/tutorial.html>
    * <https://github.com/interfirm/hapieco/pull/490>

# Rails

## rails-style-guide

* <https://github.com/bbatsov/rails-style-guide>
* <https://github.com/satour/rails-style-guide/blob/master/README-jaJA.md> (日本語版)

# Ruby

## ruby-style-guide

* <https://github.com/bbatsov/ruby-style-guide>
* <https://github.com/fortissimo1997/ruby-style-guide/blob/japanese/README.ja.md> (日本語版)

* <a name="english-comments"></a>
  Write comments in English **or Japanese**. Please use english basically, and use Japanese when it's clear that the explanation will be easier to understand.
<sup>[[link](#english-comments)]</sup>

### 複数のスタイル提案

* <a name="consistent-multi-line-chains"></a>
    Adopt a consistent multi-line method chaining style. There are two
    popular styles in the Ruby community, both of which are considered
    good - leading `.` (Option A) and trailing `.` (Option B).
<sup>[[link](#consistent-multi-line-chains)]</sup>

    * **(Option A)** When continuing a chained method invocation on another line keep the `.` on the second line.

    * **(Option B)** When continuing a chained method invocation on another line,
      include the `.` on the first line to indicate that the expression continues.**(使用中)**

    ```rb
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
      string interpolation or special symbols such as `\t`, `\n`, `'`, etc.**(使用中)**

    ```rb
    # bad
    name = "Bozhidar"

    # good
    name = 'Bozhidar'
    ```

    * **(Option B)** Prefer double-quotes unless your string literal
      contains `"` or escape characters you want to suppress.

    The string literals in this guide are aligned with the first style.
