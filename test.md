# Test Document

This is a **test file** for _mdview_ v2.1.

## Inline Formatting

- Bold text: **hello world**
- Italic text: *hello world*
- Bold+italic: ***combined***
- Inline code: `console.log("hi")`
- ~~Strikethrough~~

## Code Block

```python
def greet(name):
    return f"Hello, {name}!"

print(greet("World"))
```

## Links & Images

Check out [Anthropic](https://anthropic.com) for more.

## Blockquote

> The best way to predict the future is to invent it.
> — Alan Kay

## Nested Lists

- Top level item
  - Second level
    - Third level
    - Another third
  - Back to second
- Another top level
  1. Nested ordered
  2. Second ordered
     - Mixed nesting
     - Goes deep

## Ordered List

1. First item
2. Second item
3. Third item

## Task List

- [x] Build markdown parser
- [x] Add dark mode
- [x] Add tables
- [x] Add nested lists
- [x] Add footnotes
- [ ] Add editor (V2) ✓
- [ ] World domination

## Table

| Feature | Status | Priority |
|---------|:------:|-------:|
| Viewer | Done | High |
| Tables | Done | Medium |
| Editor | Done | High |
| Nested lists | Done | Medium |
| Footnotes | Done | Low |

## Footnotes

This is a sentence with a footnote[^1]. Here's another one[^note].

[^1]: This is the first footnote content.
[^note]: And this is a named footnote.

## HTML Passthrough

<details>
<summary>Click to expand</summary>

This content is hidden by default. It uses the HTML `details` and `summary` tags.

</details>

Text with <mark>highlighted</mark> words and <kbd>Ctrl</kbd>+<kbd>S</kbd> keyboard shortcuts.

---

*End of test document.*
