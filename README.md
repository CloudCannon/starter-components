# Starter Components

`npx @bookshop/browser`

Working project for building out the new starter components & surrounding themes project.  
Everything should currently be viewed in a state of flux — treat this as an R&D repo.

Initial cut will include components built for Hugo.

General plan is that a page will have an array of `sections`, where each section contains one or more arrays of `content_blocks`. This prevents users from nesting sections (i.e. putting `two-columns` inside another `two-columns` etc).

Figma reference for components and sections: https://www.figma.com/file/7sd7vSt6KxeAMce9x0m3xU/Starter-template?node-id=137%3A531

## Sections

Sections are components like `one-column`, `two-columns`, `hero`, ... etc.

It is expected that these are the components a user will select from when adding a new section to the page.

These will have settings such as:

**Section width**
```
│┌───────────────┐│
││               ││
│└───────────────┘│
│┌─────┐          │
││     │          │
│└─────┘          │
│┌──────────┐     │
││          │     │
│└──────────┘     │
```

**Section alignment**
```
│┌─────┐          │
││     │          │
│└─────┘          │
│     ┌─────┐     │
│     │     │     │
│     └─────┘     │
│          ┌─────┐│
│          │     ││
│          └─────┘│
```

**Inner content width**
```
│┌───────────────┐│
││┌─────┐        ││
│││     │        ││
││└─────┘        ││
│└───────────────┘│
│┌───────────────┐│
││┌─────────────┐││
│││             │││
││└─────────────┘││
│└───────────────┘│
```

**Inner content alignment**
```
│┌───────────────┐│
││┌─────┐        ││
│││     │        ││
││└─────┘        ││
│└───────────────┘│
│┌───────────────┐│
││        ┌─────┐││
││        │     │││
││        └─────┘││
│└───────────────┘│
```

## Content Blocks

Content blocks are components like `button`, `headline`, `paragraph`, ... etc.

They're probably too specific to add to the page directly, but are useful to add/remove from, say, a hero section.

These may also have some of the same width / alignment settings as the sections, or they may inherit the width / alignment settings from their parent section.

## Styling

Currently, styles are implemented using flex. Where possible, use css variables and define these in `components/shared/styles/global.scss`, which will allow users to retheme the component library easily.
