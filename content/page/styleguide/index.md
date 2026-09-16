+++
title = "Style Guide"
description = "Every markdown construct this blog can render, on one page, for eyeballing typography in both themes."
template = "page.html"
slug = "styleguide"

[extra]
noindex = true
+++

# Style Guide

Every markdown construct Zola supports, on one page, so the typography can be checked in a single
pass in both themes.

## Headings

# Heading level 1

## Heading level 2

### Heading level 3

#### Heading level 4

##### Heading level 5

###### Heading level 6

## Paragraphs and measure

A normal paragraph, to check leading, colour and the space between paragraphs.

A deliberately long paragraph for measuring line length, because line length is the single setting
that most affects whether long-form prose is comfortable to read. The usual target is somewhere
between sixty and eighty characters per line; count the characters on a full line of this paragraph
on a wide screen and see where it lands.

Short one.

## Inline formatting

Plain text, **bold text**, *italic text*, ***bold italic text***, ~~strikethrough~~, `inline code`,
and mixes such as **bold with `code` inside** or *italic with `code` inside*.

Smart punctuation is on, so: "curly double quotes", 'curly single quotes', an em dash --- like
this, an en dash for ranges 1999--2026, and an ellipsis... trailing off.

Emoji rendering is on too: :rocket: :coffee: :sparkles: :warning: :white_check_mark:

Escaped characters: \*not italic\*, \_not italic\_, \`not code\`, and a literal backslash \\ plus
an ampersand & and angle brackets &lt;like this&gt;.

Line breaks: this line ends with two trailing spaces  so this should be a hard break inside the
same paragraph.

## Links

An [external link](https://www.getzola.org/documentation/content/linking/), an
[internal link to the about page](@/page/about/index.md), an
[internal link to a post](@/2026-01-31-programmers-arent-going-anywhere.md), an
email autolink <sergey@example.com>, and a [reference-style link][zola-ref].

[zola-ref]: https://www.getzola.org/documentation/

## Lists

### Unordered, tight

- First item
- Second item with a noticeably longer line so that wrapping inside a list item can be checked against the hanging indent
- Third item

### Unordered, loose

- First item, in a loose list, so each item is wrapped in its own paragraph.

- Second item, which should therefore have paragraph-sized spacing above it.

- Third item.

### Ordered

1. First step
2. Second step
3. Third step
10. Tenth step, to check that wider numbers still align

### Ordered, custom start

7. Seventh
8. Eighth
9. Ninth

### Nested

- Top level item
  - Second level item
    - Third level item
      - Fourth level item
  - Back to second level
- Top level again
  1. Ordered inside unordered
  2. Second ordered item
     - Unordered inside ordered

### Task list

- [x] Completed task
- [ ] Incomplete task
- [ ] Another task with a longer description to check wrapping and checkbox alignment

### Definition list (not supported)

Zola's markdown parser does not implement definition lists, so the blocks below collapse into
ordinary paragraphs. Use raw `<dl>` HTML if you ever need one.

Term
: The definition of the term.

Another term
: Its definition, which would wrap onto a second line if it were rendered as a list.

### List containing block content

- An item that contains a paragraph.

  And a second paragraph inside the same list item.

  ```sh
  echo "a fenced block inside a list item"
  ```

  > And a blockquote inside a list item.

- A plain item after all that.

## Blockquotes

> A single-paragraph blockquote. Short and to the point.

> A multi-paragraph blockquote, long enough to wrap so the left padding and the
> decorative quote mark can be judged against real text.
>
> This is the second paragraph of the same blockquote.

> A blockquote with a nested one inside it.
>
> > The nested quote. Check whether the decoration and indent stack sensibly or
> > double up awkwardly.

> A quote followed by an attribution, which needs raw HTML because markdown has no
> syntax for it.
> <cite>Sergey Silaev</cite>

## Code

Inline `code` inside a sentence, inline code in a **`bold context`**, and inline code
inside a heading is tested below.

### Fenced, no language

```
No language tag, so no highlighting should be applied.
Just monospace text in a box.
```

### Fenced, with language

```rust
use std::collections::HashMap;

#[derive(Debug, Clone)]
pub struct Config {
    pub name: String,
    pub tags: HashMap<String, String>,
}

impl Default for Config {
    fn default() -> Self {
        Self {
            name: "default".to_string(),
            tags: HashMap::new(),
        }
    }
}
```

### Other languages

```python
def fib(n: int) -> int:
    """Classic, with a docstring and a comment."""
    a, b = 0, 1
    for _ in range(n):  # trailing comment
        a, b = b, a + b
    return a
```

```bash
#!/usr/bin/env bash
set -euo pipefail
for f in "$@"; do
  printf '%s\n' "${f##*/}"
done
```

```toml
[markdown.highlighting]
light_theme = "github-light"
dark_theme = "github-dark"
style = "class"
```

```json
{ "name": "8am.dev", "tags": ["zola", "blog"], "count": 42, "ok": true }
```

```diff
- removed line
+ added line
  unchanged line
```

### With line numbers

```rust,linenos
fn main() {
    let greeting = "hello";
    println!("{greeting}, world!");
}
```

### With highlighted lines

```rust,linenos,hl_lines=2-3
fn main() {
    let greeting = "hello";
    println!("{greeting}, world!");
    // lines two and three should be marked
}
```

### With a filename label

```rust,name=src/main.rs
fn main() {
    println!("named block");
}
```

### Long line, to check horizontal overflow

```python
result = some_function(first_argument, second_argument, third_argument, fourth_argument, fifth_argument, sixth_argument, seventh_argument)
```

## Tables

### Basic

| Language | Typing   | First release |
| -------- | -------- | ------------- |
| Rust     | Static   | 2015          |
| Python   | Dynamic  | 1991          |
| Go       | Static   | 2012          |

### With alignment

| Left | Centre | Right |
| :--- | :----: | ----: |
| a    |   b    |     c |
| longer cell | longer cell | longer cell |
| 1    |   22   |   333 |

### With inline formatting and a wide body

| Setting | Default | Notes |
| --- | --- | --- |
| `highlight_code` | `false` | Set in `[markdown.highlighting]` |
| `style` | `"inline"` | Use `"class"` for **dual themes** |
| `light_theme` | *none* | See the Zola docs for the full list of supported themes |

## Horizontal rule

Text above the rule.

---

Text below the rule.

## Images

A standalone image with a title attribute:

![A sample placeholder image](/styleguide-sample.svg "The title attribute")

## Shortcodes

{{<youtube id="dQw4w9WgXcQ" />}}

## Raw HTML

### Details / summary

Leave a blank line after `<summary>` and the body is parsed as normal markdown.

<details>
  <summary>A collapsed details element</summary>

Content inside the details element, including a paragraph and a list:

- one
- two

</details>

<details open>
  <summary>One that starts expanded</summary>

Add the `open` attribute to have it unfolded on page load.

</details>

<details open>
  <summary>One wrapping a code block</summary>

```rust
fn main() {
    println!("collapsed code");
}
```

</details>

<details>
  <summary>A summary long enough to wrap onto a second line, so the chevron
  alignment can be checked against multi-line text</summary>

Body text.

</details>

Keyboard keys: press <kbd>Ctrl</kbd> + <kbd>C</kbd> to copy.

Highlighted text: <mark>this should be marked</mark>.

Subscript and superscript: H<sub>2</sub>O and E = mc<sup>2</sup>.

An abbreviation: <abbr title="Static Site Generator">SSG</abbr>.

A figure with a caption:

<figure>
  <img src="/styleguide-sample.svg" alt="Sample inside a figure">
  <figcaption>A caption underneath the figure.</figcaption>
</figure>

## Heading edge cases

### A heading with `inline code` in it

### A heading with a [link](@/page/about/index.md) in it

### A heading that is deliberately long enough to wrap onto a second line on most screen widths

Trailing paragraph so the final heading has something underneath it.
