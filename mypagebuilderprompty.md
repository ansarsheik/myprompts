You are a senior full-stack engineer and product architect.

I am building a multi-tenant website builder. I already have:

* A working CMS (Payload CMS) handling tenants, pages, media, auth
* A frontend renderer that can render pages from structured JSON

I now need to build a **separate Builder App (React / Next.js)** that allows customers to visually create and edit websites.

Your task is to design and scaffold this Builder App with production-level thinking.

## Core Requirements

The builder must include:

1. Visual Canvas

* Section-based page builder (not freeform like Webflow)
* Drag-and-drop reordering of sections
* Add / delete / duplicate sections
* Click to select a block
* Highlight selected and hovered elements

2. Block System

* Use a block registry pattern
* Each block has:

  * type
  * defaultProps
  * editComponent
  * renderComponent
  * configurable fields
* Example blocks: Hero, Text, Image, Features, CTA, Testimonials

3. State Management

* Maintain a single page JSON document
* Do NOT manipulate DOM directly
* All edits update state → state renders UI
* Include undo/redo support

4. Inspector Panel (Right Sidebar)

* Contextual editing when a block is selected
* Controls:

  * text content
  * images
  * alignment
  * spacing
  * colors (from theme only)
  * typography presets
* No raw CSS editing

5. Drag and Drop

* Use a modern library (dnd-kit preferred)
* Support reordering sections
* Optional: nested blocks (only if cleanly designed)

6. Styling System

* Use theme tokens (colors, fonts, spacing)
* Prevent arbitrary values
* Example:

  * "primary", "secondary" instead of hex codes
  * "lg", "xl" instead of px

7. Responsive Editing

* Support desktop / tablet / mobile preview
* Allow limited overrides per breakpoint

8. Autosave

* Debounced save to CMS API
* Track unsaved changes

9. Live Preview

* Either:

  * render using same components inside builder
  * OR iframe preview using frontend renderer

10. Integration

* Fetch and save data via API (assume REST)
* Page structure is JSON like:
  {
  sections: [
  { type: "hero", props: {...} }
  ]
  }

## Output Requirements

Provide:

1. High-level architecture

* Folder structure
* Key components and responsibilities

2. Data model (TypeScript interfaces)

3. Block registry example

4. Core components with code:

* Builder layout (3-panel UI)
* Canvas renderer
* Block renderer
* Inspector panel
* Drag-and-drop setup

5. State management setup (Zustand or Redux)

6. Example block (Hero) with:

* render component
* edit component

7. Autosave logic (debounced)

8. Suggestions for scaling (performance, large pages, multi-tenant)

## Constraints

* Use React + Next.js (App Router)
* Use TypeScript
* Keep UX simple and scalable (like Shopify / Squarespace)
* Avoid overengineering
* Focus on clean patterns and maintainability

## Important

Do NOT give generic explanations.

Give concrete architecture, code examples, and real implementation patterns I can use immediately.
