---
title: "Introducing: Tournant"
description: "Well, hello there. We are Tournant. We build building blocks for an Inclusive Web."
date: 2019-12-04
tags: meta
layout: layouts/post.njk
---

With this post, we are going to answer some questions you might have. Or maybe give you answers to questions that you didn’t have. To be a bit pathetic: This post is our mission statement.

It will explain what we do, why we do it and – to begin with – what our name means.

## Tournant – The dictionary part

To explain our name we have to make a short detour into the world of food. Into the kitchen, to be exact.

Georges Auguste Escoffier developed the concept of the _Brigade de Cuisine_, a detailed list of positions that make up the staff of a professional kitchen. Even though most of the described posts are non-existing in most of the kitchens.

Hidden among better-known positions such as the mighty _Chef de cuisine_, the _Chef de partie_ or the _Pâtissier_ is a humble one: named _Tournant_.

While all other positions are rather specific, the Tournant has a different obligation: They need to help out where help is needed. They will have to know how to work together with all the different chefs. Knowing how to be useful in ever-changing circumstances.

## Tournant – The organisational part

Now, you might be asking – and rightfully so – what all this has to do with development.
This group was born out of the realisation that the Vue development landscape is missing something very fundamental: An accessible component library.

While there is a group named [Vue A11y](https://github.com/vue-a11y/), the Vue landscape is missing a project such as [Reach UI](https://reacttraining.com/reach-ui/). Reach UI is maintained by the team behind React Training and «seeks to become the accessible foundation of your React-based design system».

Reach UI will not provide you with styled components or everything you need, but it gives you things you need over and over again and abstract away some of the difficulties in building accessible interfaces.

Despite – or maybe because of – the fact that accessibility in digital projects is in a dire state. In February 2019 WebAIM conducted [a study of the top million homepages](https://webaim.org/projects/million/). They found, on average, almost 60 detectable accessibility errors per page; [pages on which Vue was detected](https://webaim.org/projects/million/#frameworks) were even worse off, with 73.7 errors per page.

It does not have to be this way.

[Tournant](https://github.com/tournantdev), and our main project, [Tournant UI](https://ui.tournant.dev/), is our effort to shrink that number.

We are not trying to steal other projects in the Vue realm – such as Vue A11y, [Vuetify](https://vuetifyjs.com/) or [Buefy](https://buefy.github.io/#/) – a piece of their cake, but try to add a new cake to the bakery.

And such as our namesake in the kitchen, we develop components that are there when you need them. But which also let you do, what you do best: Developing and designing your projects and making them awesome.

## Tournant UI – Inclusive Vue Components

Tournant UI will include the UI components documented in the [Design Patterns and Widgets](https://www.w3.org/TR/wai-aria-practices-1.1/#aria_ex) section of the [ARIA Authoring Practices](https://www.w3.org/TR/wai-aria-practices-1.1/). We say «will include» because this project is still in early development. If you want to help out, please read our [contributing document](https://github.com/tournantdev/ui/blob/master/CONTRIBUTING.md) on GitHub and get in touch with us.

Our goal is to provide components that are not tied to a specific layout methodology or include any business logic (such as data fetching).

Instead, we are aiming to make accessibility more accessible. Sounds weird, eh? But a common sentiment is that accessibility is hard. And we get that. It certainly isn’t easy—even more so when you are trying to develop complicated components. The [ARIA specification](https://www.w3.org/TR/wai-aria-1.1/) is a specification and as such not easy to understand by a layperson, the [Web Content Accessibility Guidelines](https://www.w3.org/TR/WCAG21/) can be a great resource – or a very dry one.

The interplay of some attributes can be confusing, can get you in a world of disappointment. And—even if you follow all the specs and guidelines—Assistive Technology is technology and technology has bugs.

This leads to effort. We believe this effort that has to be done, because «access by everyone regardless of disability is an essential aspect» ([Tim Berners-Lee](https://www.w3.org/Press/IPO-announce)) of the World Wide Web.

What we also believe that the WWW is broken as is. It is broken beyond repair by any single individual. Putting it back together, making it more usable for everyone will require a community effort. Tournant UI is our part in this effort.

## It’s not all the help you’ll need

But, alas. A component library will only get you so far. Providing inclusive and accessible user experiences is an effort that has to be undertaken by whole organisations. Your editors will have to provide a text alternative to images and videos, and your translators will have to hand over translations for multilingual sites. Your fellow developers have to care about not breaking what works.

In the grand scheme of things building better interfaces is more of a social and educational enterprise than a technical one.

Fortunately, there are humans currently undertaking this effort. To get a quick overview take a look at Scott O’Hara’s list of [Accessibility Resources](https://www.scottohara.me/note/2019/05/07/resources.html) or the list of resources for the talk [Accessibility, Inputs & Vue](https://talks.ovl.design/OY4mvA/accessibility-inputs-vue) by our team member Oscar.

## Building blocks for an inclusive web

This was us introducing ourselves. We hope you will join us along our journey. If you find bugs or quirks in the components we publish, please [open issues](https://github.com/tournantdev/ui/issues). If you want to contribute, get in touch; and last but not least: Please share the word, use the components and keep being awesome and invested in the fight for a better, inclusive Web.

Yours,
[Marcus](https://marcus.io/) & [Oscar ](https://www.ovl.design/)
