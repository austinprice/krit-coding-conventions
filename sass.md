# Sass Guidelines
A set of conventions for writing clean, organized and scalable Sass.

## Architecture
A clean and organized folder structure is key. To keep our Sass folder structure organized, we make use of partials and a modified version of the [7-1](https://github.com/HugoGiraudel/sass-boilerplate) Pattern of structuring folders, with 6 folders and 1 index file. The folders are:

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
- /config
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


## Syntax & Formatting
In general, we follow the [Sass Guidelines](https://sass-guidelin.es/#syntax--formatting) for syntax and formatting. When in doubt, refer to those for syntax and formatting questions.

Some basic rules:
- 2-space indents, no tabs
- Use whitespace only in a meaningful way
- Use single quotes on all strings
- Use zeros before decimal values

### Naming Conventions
We follow basic [BEM](https://en.bem.info/methodology/naming-convention/) naming conventions, meaning Block-Element-Modifier.

```
.block {
}

.block-element {
}

.block-element_modifier {
}
```
You can use Sass' nested properties to make these classes more organized.
```
.block {
  &-element {
    &_modifier {
    }
  }
}
```
Which would print out as:
```
.block-element_modifier {
}
```

### Nesting
Nesting is cool, but don't go more than 3 levels deep.

### Declaration Sorting
To keep styles consistent, we follow the [Concentric CSS](https://github.com/brandon-rhodes/Concentric-CSS/blob/master/style.css) model of type ordering. Essentially, Concentric CSS follows the box-model to define order. Start outside and work inward. Refer to Concentric CSS for specific order, but these are the general guidelines:

1. Layout (display, position, etc.)
2. View (visibility, opacity, z-index, etc.)
3. Margins
4. Borders
5. Background
6. Padding
7. Dimensions (width, height)
8. Overflow
9. Text styles (text-align, text-transform, etc.)
10. Text Formatting (line-height, letter-spacing, etc.)
11. Font styles (color, font-size, etc.)


## Commenting
A well-commented codebase makes collaboration easy as pie. Follow this basic commenting rules

#### File Headers
All files should contain a header explaining what the file is used for. For example, the base/_type.scss file should contain this header:
```
// Type
// All base font and typography styles (font-family, color, size, etc.)
// --------------------------------------------------------------------
```

#### Section Headers
Sections help make files more easily searchable. Not all files need sections, but if you add sections to a file, use the following format for section headers. For example, in the base/_type.scss file, you may have the following header:

```
// --------------------------------------------------------------------
// Headers
// All base header styles (h1-h6)
// --------------------------------------------------------------------
```

Sections should be wrapped with a closing comment as well.
```
// Headers ------------------------------------------------------------
```

#### Element Headers
For elements that don't warrant their own sections, attach an Element Header above it. For example, declaring the global link styles in base/_type.scss might look like this:
```
// Global styles for all links
a {
  color: $active-color;
  text-decoration: none;
  
  &:hover {
    text-decoration: underline;
  }
}
```


## Variables
In order to maintain a consistent style throughout the app, rely heavily on the use of variables.

### Declaration
All variables should be declared 
