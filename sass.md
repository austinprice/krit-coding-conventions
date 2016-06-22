# Sass Guidelines
A set of conventions for writing clean, organized and scalable Sass.

## Architecture
A clean and organized folder structure is key. To keep our Sass folder structure organized, we make use of partials and a modified version of the 7-1 Pattern of structuring folders, with 6 folders and 1 index file. The folders are:

- /base
  - Sets base global default styles. Stick with element selectors, child selectors and psuedo classes.
  - Includes basic fonts, typography sizes, link styles, backgrounds.
  - Avoid class and ID selectors in the base
- /components
  - Sets global styles of small, modular components that can be dropped anywhere in the app.
  - Includes nav bars, buttons, cards, modals, sliders, etc.
  - Avoid large, complex components and page-specific styles.
- /layout
  - Sets styles for laying out the app, combining components into larger, more complex elements
  - Includes the grid, containers, forms, galleries, hero sections, etc.
  - Avoid micro styles, singular components, and page-specific styles
- /pages
  - Sets any page-specific styles that will be used only on a given page or section of the app.
  - File names should directly correspond to a template name.
  - Keep styles here to a minimum. Try to make styles modular and repeatable across instances first.
- /abstracts
  - Sets global tools and helpers used across the app.
  - Includes variables, settings, mixins, and functions.
  - Avoid concrete element, class and ID selectors. This should only contain abstract tools that utilize the power of Sass.
- /vendors
  - Contains all external files/libraries.
  - Includes anything that you're not creating yourself and are pulling in from a third party.
  - Avoid editing any files here unless absolutely necessary.

- index.scss
  - Only used for importing all other styles.
  - 1 file per import, 1 import per line.
  - Should not contain anything besides imports and comments
