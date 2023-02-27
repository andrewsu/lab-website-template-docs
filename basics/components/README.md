---
description: How to write fancier content for your site with components
---

# Components

Markdown is meant for [basic content](../write-basic-content.md), but sometimes you need something more. **Components** are building blocks for more complex visual and interactive elements on your site. You can also think of them as "widgets".

The template comes with many pre-made components so you can assemble your website however you want with ease.

Simply place the code for a component in one of your markdown files, and it will appear in your site. The basic syntax for including a component is:

```liquid
{% raw %}
{% include some-component.html parameter="value" %}
{% endraw %}
```

{% hint style="info" %}
Unless noted otherwise, all component parameters are optional and have graceful fallbacks if not specified.
{% endhint %}

Example of including an image with a caption:

```liquid
Some regular Markdown content. Lorem ipsum dolor sit amet.

{%
  include figure.html
  image="images/group-photo.jpg"
  caption="The team at our annual Christmas party, 2025"
  link="team-page"
  width="400px"
%}
```