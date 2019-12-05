---
title: "Development Notes: Breadcrumb"
description: "Usage instructions for @tournant/breadcrumb."
date: 2019-12-05
tags: dev-notes
layout: layouts/post.njk
---

Say hello to our latest component: [@tournant/breadcrumb](https://www.npmjs.com/package/@tournant/breadcrumb).

## What is a breadcrumb?

A breadcrumb is, [the ARIA guidelines](https://www.w3.org/TR/wai-aria-practices-1.1/#breadcrumb) say it quite nicely, «a trail of links to let users find their place within a website».

It is placed atop of the main content as a navigational guide. In recent times it also found its use case for Search Engine Optimisation (SEO), since it provides a handy mechanism to increase the number of internal links.

## What ARIA has to say

The component is pretty straight forward. There are no special keyboard interactions to follow. The list has to be rendered in a `nav` element, which contains an ordered list (`ol`).

The `nav` element needs to have a label to distinguish it from other navigation landmarks.

The last item in the breadcrumb is marked with `aria-current="page"`. Most screen readers will use this to announce that it is, well, the current page. However, linking the last item is not mandatory. If it misses the `to` property, it will be rendered as plain text and not marked.

At the time of writing `aria-current` is not supported by TalkBack on Android.

## Usage Guidelines

`@tournant/breadcrumb` takes these properties:

### labelText

A string that is used as the `aria-label` for the `nav` element. It defaults to “Breadcrumb”.

### labelledBy

You can provide the ID of an element on the page to label the navigation.

If this element should be contained in the `nav`, you can use the `label` slot.

```html
<tournant-breadcrumb :links="links" :labelledBy="test-id">
  <template v-slot:label>
    <h2 id="test-id">Breadcrumb</h2>
  </template>
</tournant-breadcrumb>
```

If you use `labelledBy`, `aria-label` will _not_ be added.

### links

An array of links that construct the breadcrumb. Items in the array are objects which _must_ contain the properties `to` and `text`. A simple example might look like:

```js
[
  { to: "/", text: "Homepage" },
  { to: "/archive", text: "Archive" },
  { to: "/archive/post", text: "Post" }
];
```

### Framework Compatibility

Links in Vue don’t have to be represented as `a` elements. If you are using [Vue Router](https://router.vuejs.org/) you most likely want to use the [Router Link](https://router.vuejs.org/api/#router-link-props) component. And if you are using [Nuxt](https://nuxtjs.org/), they should probably be [Nuxt Links](https://nuxtjs.org/api/components-nuxt-link/).

This is why we detect if Nuxt or Vue Router are defined on the running Vue instance. If they are, we use the matching component and forward all attributes and props.

If some links are not part of your router config, you can add `useNativeLinkElement: true` to them and the link will always be rendered as a standard `a` element.

If your homepage is not yet part of your Vue implementation, you can modify the example from above like this:

```js
[
  { to: "/", text: "Homepage", useNativeLinkElement: true },
  { to: "/archive", text: "Archive" },
  { to: "/archive/post", text: "Post" }
];
```

This functionality is provided by the [@tournant/dynamic-anchor](https://www.npmjs.com/package/@tournant/dynamic-anchor) component. The complications of building this are worthy a post on its own, I will update this post as soon as it is written.

### Microdata

Schema.org compatible [BreadcrumbList microdata](https://schema.org/BreadcrumbList) is embedded into the markup. Hence this breadcrumb is discoverable by third parties and they are able to use this data, e.g. in displaying it in a search results page.

For complete usage instructions, please read the [component package page](https://www.npmjs.com/package/@tournant/breadcrumb).

That’s it. Happy crumbling.
Team Tournant
