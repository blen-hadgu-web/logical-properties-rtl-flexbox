# Web Project Testing and Quality Assurance Checklist

Use this checklist in the video. Add any additional cases from the instructor's separate QA guide if it becomes available.

## 1. Content and structure

- [ ] English profile settings card is visible.
- [ ] Arabic profile settings card is visible.
- [ ] Both cards use the same CSS classes.
- [ ] English content has `dir="ltr"` and `lang="en"`.
- [ ] Arabic content has `dir="rtl"` and `lang="ar"`.
- [ ] Both notification cards are visible.
- [ ] The local avatar image loads in both cards.
- [ ] Every button has `type="button"`.

## 2. Translation symmetry

Compare both settings cards:

- [ ] English avatar appears at the English inline start.
- [ ] Arabic avatar appears at the Arabic inline start.
- [ ] Profile information follows the avatar in both directions.
- [ ] Change Photo appears at the opposite inline side when space allows.
- [ ] English action buttons follow LTR flow.
- [ ] Arabic action buttons mirror through RTL flow.
- [ ] Card spacing is visually equivalent.
- [ ] Notification icon, text, and dismissal button mirror naturally.

## 3. Banned-word source audit

Open `styles.css` and search for each prohibited physical direction word:

- [ ] First prohibited word: zero results
- [ ] Second prohibited word: zero results
- [ ] Third prohibited word: zero results
- [ ] Fourth prohibited word: zero results

The searches must include comments and selector names, not only declarations.

## 4. Logical properties

Verify the stylesheet contains:

- [ ] `margin-inline`
- [ ] `padding-inline`
- [ ] `padding-block`
- [ ] `border-block-start`
- [ ] `border-block-end`
- [ ] `inline-size`
- [ ] `block-size`
- [ ] `min-inline-size`
- [ ] `min-block-size`
- [ ] `inset-inline-start`
- [ ] `inset-block-start`
- [ ] `text-align: start`

## 5. Flexbox gutter audit

- [ ] `.app-layout` uses Flexbox.
- [ ] `.settings-card` uses Flexbox.
- [ ] `.settings-card__profile-section` uses Flexbox.
- [ ] `.settings-card__actions` uses Flexbox.
- [ ] `.notification-card` uses Flexbox.
- [ ] Parent `gap` values control sibling spacing.
- [ ] Individual children do not use margins to push siblings apart.
- [ ] No floats are used.

## 6. Box model

- [ ] Universal `box-sizing: border-box` is present.
- [ ] Pseudo-elements receive `border-box`.
- [ ] Default heading and paragraph margins are reset.
- [ ] Card padding stays inside the declared inline size.

## 7. Responsive testing

Test approximately:

- [ ] 320px
- [ ] 375px
- [ ] 768px
- [ ] 1024px
- [ ] 1440px
- [ ] 2560px

At each width:

- [ ] No page-level horizontal scrollbar appears.
- [ ] Cards wrap without overlap.
- [ ] Profile rows remain readable.
- [ ] Buttons remain inside each card.
- [ ] Narrow layouts stack the profile content.
- [ ] Arabic text remains aligned to its logical start.
- [ ] English text remains aligned to its logical start.

## 8. Keyboard and zoom

- [ ] Skip link appears first when pressing Tab.
- [ ] Buttons receive focus in logical source order.
- [ ] Focus rings are visible in both color schemes.
- [ ] The page remains usable at 200% zoom.
- [ ] Text reflows without clipping.
- [ ] Buttons remain reachable at 200% zoom.

## 9. Color and theme

- [ ] Text contrast is readable in light mode.
- [ ] Text contrast is readable in dark mode.
- [ ] Status text is distinguishable.
- [ ] Focus color contrasts with card surfaces.
- [ ] Cards remain visually separate from the canvas.

## 10. Production deployment

- [ ] Repository is public.
- [ ] `index.html` is at repository root.
- [ ] `styles.css` loads.
- [ ] Local avatar and favicon load.
- [ ] GitHub Pages reports successful deployment.
- [ ] Live page works in Incognito/Private mode.
- [ ] README documents the project, prompt, audit, and local run steps.
