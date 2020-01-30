---
title: "Development Notes: Notification"
description: "Usage instructions for @tournant/notification."
date: 2020-01-30
tags: dev-notes
layout: layouts/post.njk
---

Our latest component gives you the ability to communicate timely information with your users. You can notify them about stuff and other stuff. It’s [@tournant/notification](https://www.npmjs.com/package/@tournant/notification).

Let’s write some words about the process of building it and where it is or isn’t useful.

## A notification is a notification is a notification?

I am glad you asked, headline. The answer is: Nah.

Let’s imagine the real world for a second. You are sitting on the edge of silver future, wondering how it might be. Suddenly you washing machine yells: «I’m done!», interrupting your thoughts completely. A bit overzealous.

Now, on the other hand a self-driving car that does not warn you, loud and clear, that it is about to make a break, breaks and slams your face into your breakfast is tiny bit too shy.

I guess the point I’m trying to make is: It depends. Some notifications need to communicated immediately and with urgency. While some can wait.

Our notification component knows this and can fit into any situation. In technical terms, the component is a _live region_ that can have a role of either `status` or `alert`.

## What ARIA has to say

You might know that we haven’t invented the term [live region](https://www.w3.org/TR/wai-aria-1.1/#dfn-live-region) ourself, but that it is part of the ARIA guidelines. In their terms these regions are «perceivable regions of a web page that are typically updated as a result of an external event when user focus may be elsewhere».

Now, to expand a bit on the roles I have mentioned before. They basically mirror the not-so-important announcement ([status](https://www.w3.org/TR/wai-aria-1.1/#status)) or the very-much-so important announcement ([alert](https://www.w3.org/TR/wai-aria-1.1/#alert)).

Going back to the almost realistic examples from the beginning: Our washing machine being done would be a case of implementing a status message. While the car should be an alert.

## Usage Guidelines

As always, you can find exhaustive documentation in the Readme on NPM or GitHub.

But, let’s quickly cover the basics here, as you are reading this.

We decided to make `status` the default role of the component. Why? Because, as [Marcus](https://marcus.io/) nicely put it, developers tend to have an economical behaviour when it comes to reading documentation. We didn’t want to put a component out there and bombard users of assistive technology with alert messages.

To use it as a status message you need to pass in only a message:

```html
<!-- Input !-->
<tournant-notification message="Page 4 has been loaded" />

<!-- Output -->
<div role="status" class="t-ui-alert is-info">Page 4 has been loaded</div>
```

If you _need_ to announce an alert, e.g. when submitting a form, you can use the `type` prop:

```html
<!-- Input !-->
<tournant-notification
  type="assertive"
  message="Your e-mail address is invalid"
/>

<!-- Output -->
<div role="alert" class="t-ui-alert is-info">
  The server could not be reached
</div>
```

### Message handling

To be clear: This component is only the message. To comply with the ARIA guidelines it will set a timeout once it is mounted, and hide itself via `aria-hidden` and setting `display: none`.

Let’s suppose you are showing a notification for every item in an array.

```js
export default {
  data: () => ({
    messages: [   { text: 'Page 1 loaded' }   { text: 'Page 2 loaded' },   { text: 'Page 3 loaded' } ]
  })
}
```

The component will _not_ delete the underlying, it will only become invisible. It will, though, emit a [custom event](https://vuejs.org/v2/guide/components-custom-events.html) once the timer has elapsed. You will have to clean-up your messages once they have become obsolete.

### Props

The following props can be used to control the component:

- `message`: _Required_. A string that should be added to page and read out by screen readers.
- `state`: Default: `info`. A state level, with which you can control visual representation.
- `type`: Default: `polite`. Controls the announcement by a screen reader. Must be either `assertive` or `polite`.
- `hideAfterSeconds`: Default: `5`. The time which should pass before the message is hidden.

And so we end our notification (sorry). You can find the component on NPM or view the source code on GitHub.

Happy notifying,
Team Tournant
