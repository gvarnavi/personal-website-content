---

date: 2023-07-23T14:00:00+06:00
lastmod: 2023-07-23T14:00:00+06:00
title: Interactive Presentations Workflow
authors: ["georgiosvarnavides"]
categories:
  - presentations
slug: interactive-presentations-workflow
comments: true
thumbnail: /images/presentations-00.svg

---

#### Observable Notebooks

First things first: if you want an interactive presentation you need to create (or re-use!) interactive components or widgets.
These need to run client-side and would ideally be packaged as react components.
I like using [observablehq](https://observablehq.com/explore) to do this, a reactive notebook environment for javascript code.

Admittedly, coding in javascript is a bit of a learning curve but I have found the [scijs family of packages](https://scijs.net/packages/) as-well as [numjs](https://www.npmjs.com/package/numjs) to be a fairly good numpy replacement for N-dimensional array scientific computing.

Observablehq ships with lightweight [interface components](https://observablehq.com/@observablehq/inputs) such as buttons, sliders, dropdowns, etc., to facilitate interactive widgets, a concise [plotting API](https://observablehq.com/plot/), and the ability to fork/import other public notebooks.

When building exploratory observable notebooks, I like to interweave markdown text and interactive displays leaving all the utility functions at the bottom, see e.g. [this 4dstem multislice simulation notebook](https://observablehq.com/@gvarnavi/4dstem-multislice-simulation).
I then create a separate (untitled) notebook which simply imports the necessary visualizations/widgets to export as I'd like to appear in the presentation, see e.g. [this 4dstem multislice simulation component](https://observablehq.com/@gvarnavi/multislice-4dstem-component).


#### React Components

Once you're satisfied with your interactive component, you need to export it as a React component to embed in our presentation.
Observablehq provides many ways to [embed notebook cells](https://observablehq.com/@observablehq/embeds) onto websites, but we're interested in embedding the "Entire notebook" using "Runtime with React" in the pop-up window.

Each interactive component must then be yarn-installed in your docusaurus website (see below) and the minimal code the pop-up windown prompts you to copy should be placed in the `src` directory, see e.g. [here](https://github.com/gvarnavi/2023mm-presentation/blob/main/src/components/TwoConvexSetsComponent.js).

At this point, if you created the component yourself, you can remove the `<p>` tag with the attribution banner.
Finally, if you've modified the notebook a few times, make sure to install the correct [pinned version](https://observablehq.com/@mootari/notebook-data) of the notebook.

#### Docusaurus Website

The actual website is made using [Docusaurus](https://docusaurus.io/), a wonderful documentation-site builder using React and MDX.
This will give us site-navigation as-well as a sidebar "for-free" where each documentation markdown page is written in MDX, allowing you to embed React components directly into markdown text, see e.g. [here](https://github.com/gvarnavi/2023mm-presentation/blob/main/slides/em-bg/em-bg_4dstem.mdx).

A number of configuration options can be used to make the website look more "presentation-like":
- [Hideable sidebar](https://docusaurus.io/docs/sidebar#hideable-sidebar)
- [Hideable table-of-contents](https://docusaurus.io/docs/api/plugins/@docusaurus/plugin-content-docs#hide_table_of_contents) on each doc page
- [CSS-styling](https://github.com/gvarnavi/2023mm-presentation/blob/main/src/css/custom.css) to hide observable "inspector" cells
- [Tabs](https://docusaurus.io/docs/markdown-features/tabs) and [details](https://docusaurus.io/docs/markdown-features#details) elements were used to mimic slide animations 

Finally, you can [deploy your website](https://docusaurus.io/docs/deployment) using a Jamstack provider.
I like using Github pages, and you can see the full source-code for an example presentation [here](https://github.com/gvarnavi/2023mm-presentation).
