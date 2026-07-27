# Internationalized Layouts with Logical Properties & Flexbox Gutters

A responsive and translation-ready interface containing:

- English left-to-right profile settings card
- Arabic right-to-left profile settings card
- Matching left-to-right and right-to-left notification cards
- One shared stylesheet for both writing directions

The project demonstrates internationalized logical CSS properties, Flexbox gutters, automatic direction mirroring, accessible controls, and a human audit of AI-generated CSS.

## Live Website

After GitHub Pages is enabled:

`https://blen-hadgu-web.github.io/logical-properties-rtl-flexbox/`

## Public Repository

`https://github.com/blen-hadgu-web/logical-properties-rtl-flexbox`

## Project Structure

```text
logical-properties-rtl-flexbox/
├── .nojekyll
├── favicon.svg
├── index.html
├── profile-avatar.svg
├── README.md
├── SUBMISSION.txt
├── TESTING-CHECKLIST.md
├── VIDEO-SCRIPT.md
└── styles.css
```

## Run Locally

No package manager, framework, JavaScript, or build command is required.

1. Download or clone the repository.
2. Open `index.html` in a modern browser.

VS Code Live Server may also be used.

## AI Tool and Prompt

**AI tool:** ChatGPT

### Drafting prompt

> I have an HTML structure with two identical settings cards: one is Left-to-Right (LTR) and the other is Right-to-Left (RTL) [paste the supplied HTML]. Write a clean CSS file using Flexbox layouts.
>
> Use internationalized logical properties for all spacing, sizing, borders, and positioning. Use properties such as `margin-inline`, `margin-block`, `padding-inline`, `padding-block`, `border-block-start`, `border-block-end`, `inline-size`, `block-size`, `min-inline-size`, `min-block-size`, `inset-inline-start`, and `inset-block-start`.
>
> The physical direction words prohibited by this lab must not appear anywhere in the stylesheet, including comments and selector names. Do not use physical margin, padding, border, inset, or text-alignment properties.
>
> Align text with `text-align: start`.
>
> Use `display: flex` and parent `gap` values for all element-to-element gutters. Do not add margins to individual items merely to push siblings apart.
>
> Use the exact same component classes for the LTR and RTL settings cards. The `dir` attribute alone must mirror the avatar, profile information, Change Photo button, and action buttons.
>
> Include a responsive layout, global `border-box` sizing, visible keyboard focus, and accessible light and dark colors.

## Technical Audit

### Direction symmetry

The same classes are used by both cards. The browser changes Flexbox's inline direction through each section's `dir` attribute:

```html
<section class="settings-card" dir="ltr">
<section class="settings-card" dir="rtl">
```

No direction-specific CSS override is needed.

### Logical properties

The stylesheet uses properties such as:

- `margin-inline`
- `padding-inline`
- `padding-block`
- `border-block-start`
- `border-block-end`
- `inline-size`
- `block-size`
- `min-inline-size`
- `min-block-size`
- `inset-inline-start`
- `inset-block-start`
- `text-align: start`

### Banned-word audit

The completed `styles.css` contains zero occurrences of the four prohibited physical direction words. This includes comments, property names, selectors, and values.

### Flexbox gutters

Cards, profile rows, action rows, and notification rows use parent `gap` values. Individual children do not receive margins to simulate gutters.

### Button order

The HTML action order remains:

```html
<button>Cancel</button>
<button>Save Changes</button>
```

Because the footer is a Flexbox container inside sections with different writing directions, the visual order mirrors naturally. No duplicated RTL rule is required.

### Avatar and photo-button position

The profile row is also a shared Flexbox layout. In English, the avatar begins at the inline start. In Arabic, the inline start changes automatically, placing the avatar on the opposite visual side.

## Accessibility Improvements

The supplied structure was retained and enhanced with:

- Language attributes on English and Arabic components
- A skip link
- Meaningful local avatar alternatives
- Explicit button types
- Visible keyboard focus
- Semantic labels for notification dismissal
- Responsive reflow
- Dark-mode color support

## Testing

See [`TESTING-CHECKLIST.md`](TESTING-CHECKLIST.md).

The separate “Web Project Testing & Quality Assurance Guide” was not supplied with the assignment text. The included checklist covers all visible requirements and common RTL, keyboard, responsive, and deployment checks.

## Deployment

1. Create a public repository named `logical-properties-rtl-flexbox`.
2. Upload or push every project file.
3. Open **Settings → Pages**.
4. Select **Deploy from a branch**.
5. Choose `main` and `/(root)`.
6. Save and wait for deployment.

## Author

**Blen Hadgu**
