# Write basic content

[Markdown](https://commonmark.org/help/) is a way to write basic text content and formatting in a clean and simple way. Markdown `.md` files are plain text files that get converted into pages on your resulting website.

[👁️ Preview](https://lab-website-template.netlify.app/testbed#basic-formatting)

## Links

To an external site:

```markdown
[Link text](https://some-website.org/)
```

To a page within your site:

```markdown
[Meet our team!](team)
```

The example above works in most cases, because your site is likely to only have top-level pages and the URL is relative to the current page. If you have sub-pages or more complex linking needs, see below.

<details>

<summary>Advanced</summary>

You can of course use any [standard path syntax](https://www.w3schools.com/html/html\_filepaths.asp):

```markdown
Page/photo located in same folder as current page (i.e. a sub-page)
[Link text](page)
[Link text](photo.jpg)

Photo located in sub-folder of current page
[Link text](assets/photo.jpg)

Photo located in folder one level up from current page
[Link text](../photo.jpg)

Page/sub-page, starting from root of website
[Link text](/page)
[Link text](/page/sub-page)
```

But note that if you're writing a link relative to root (starting it with a `/`), and [the URL you set up](../getting-started/set-up-your-url.md) is not at root, e.g. `github.io/your-lab-website`, you'll need to prepend a "baseurl":

```markdown
Manually prepend baseurl
[Link text](/your-lab-website/page/sub-page)

Jekyll automatically prepends the right baseurl
[Link text]({{ "/page/sub-page" | relative_url }})
[Link text]({% raw %}
{% link page/sub-page/index.md %}
{% endraw %})
```

</details>

### Data, front-matter, components

Specifying URLs in `/_data` files, front matters, [component](components/) parameters, etc. works differently than it does in Markdown content. The link to the page/image/etc. **must be relative to the root of your repo**. You cannot refer to files relative to the current file, or use the `..` to move up folders.

```yaml
- image: images/photo.jpg
```

```liquid
{% raw %}
{% include some-component.html image="images/photo.jpg" %}
{% endraw %}
```

## **Basic text styles**

```markdown
_italic text_
```

```markdown
**bold text**
```

```markdown
~~strike-through text~~
```

## **Line breaks**

```html
<br>
<br>
Text with extra blank lines above and below
<br>
<br>
```

## **Comments**

```markdown
<!-- a comment in HTML -->

{% raw %}
{% comment %}
A comment in Liquid
{% endcomment %}
{% endraw %}
```

## **Lists**

```markdown
- list item a
- list item b
- list item c
```

```markdown
1. ordered list item 1
2. ordered list item 2
3. ordered list item 3
```

## **Headings**

```markdown
# Top level heading
## Secondary heading
### Very specific heading
#### Even more specific heading
```

## **Horizontal rule**

```markdown
---
```

## **Table**

With left-aligned, centered, and right-aligned columns.

```markdown
| TABLE | Game 1 | Game 2 | Game 3 | Total |
| :---- | :----: | :----: | :----: | ----: |
| Anna  |  144   |  123   |  218   |  485  |
| Bill  |   90   |  175   |  120   |  385  |
| Cara  |  102   |  214   |  233   |  549  |
```

## **Block quote**

```markdown
> It was the best of times it was the worst of times.
> It was the age of wisdom, it was the age of foolishness.
> It was the spring of hope, it was the winter of despair.
```

## **Code block**

With syntax highlighting.

````markdown
```javascript
// a comment
const popup = document.querySelector("#popup");
popup.style.width = "100%";
popup.innerText = "Lorem ipsum dolor sit amet.";
```
````

## **Inline code**

```markdown
This sentence has `inline code`, useful for making references to variables, packages, versions, etc. within a sentence.
```

## **Util classes**

In Markdown, you can attach an arbitrary CSS class to an element with the syntax `{:.class}`. Depending on the type of element, this code may have to go on the same line or on the next line.

The template has a few utility classes for basic things.

```markdown
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
{:.center}
```

Centers an element. Most things in the template are centered by default where appropriate, but sometimes you may want to attach this `center` utility class to an element to center it.