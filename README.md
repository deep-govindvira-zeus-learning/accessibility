# accessibility (Text Info + Audio Info)

- 1.3.3 Sensory Characteristics (A) - No Text - Instructions must not rely solely on shape, color, size, position, orientation, or sound.
- 1.3.4 Orientation (AA) - Content must not lock to a single orientation (portrait or landscape) unless essential
- 1.3.5 Identify Input Purpose (AA) - Autocomplete - Inputs collecting user info must expose their purpose programmatically (HTML autocomplete tokens).
- 1.4.1 Use of Color (A) - No text - Color must not be the only visual means of conveying info, indicating action, or distinguishing elements.
- 1.4.2 Audio Control (A) - 3 Sec - Audio that plays automatically for >3s must have a way to pause, stop, or control volume independently
- 1.4.3 Contrast (Minimum) (AA) - Text contrast ≥4.5:1 (normal) or ≥3:1 (large: ≥18.66px bold / ≥24px)
- 1.4.4 Resize Text (AA) - Text must scale up to 200% without loss of content or function (no horizontal scroll trap, no clipping) ( use rem/em units so text scales with browser zoom)
- 1.4.5 Images of Text (AA) - Use real text instead of images of text when the same presentation is possible.
- 1.4.10 Reflow (AA) - Content reflows to a single column at 320 CSS px wide (400% zoom) with no 2-D scrolling. (media queries)
- 1.4.11 Non-text Contrast (AA) - UI components and meaningful graphics need ≥3:1 contrast against adjacent colors.
- 1.4.12 Text Spacing (AA) - No loss of content when users override/overflow line-height to 1.5×, paragraph 2×, letter 0.12×, word 0.16×.
- 1.4.13 Content on Hover or Focus - Tooltips/popovers on hover/focus must be dismissable, hoverable, and persistent.
- 2.1.1 Keyboard (A) - All functionality must be operable with a keyboard alone.
- 2.1.2 No Keyboard Trap (A) - Keyboard focus must be able to move away from any component using standard keys.
- 2.1.4 Character Key Shortcuts (A) - Single-character shortcuts must be turn-off-able, remappable, or active only on focus
- 2.2.1 Timing Adjustable (A) - Users must be able to turn off, adjust, or extend time limits
- 2.2.2 Pause, Stop, Hide (A) - Moving/blinking/auto-updating content lasting >5s must be pausable, stoppable, or hideable
- 2.3.1 Three Flashes or Below Threshold (A) - Nothing flashes more than three times per second (or stays under the flash thresholds).
- 2.4.1 Bypass Blocks (A) - Provide a way to skip repeated blocks (skip link, landmarks, or headings).
- 2.4.2 Page Titled (A) - Each page has a descriptive, unique <title>
- 2.4.3 Focus Order (A) - Focus moves in an order that preserves meaning and operability.
- 2.4.4 Link Purpose (In Context) (A) - The purpose of each link is clear from its text or its programmatic context.
- 2.4.5 Multiple Ways (AA) - More than one way to locate a page within a set (search, sitemap, nav, index)
- 2.4.6 Headings and Labels (AA) - Headings and labels describe their topic or purpose.
- 2.4.7 Focus Visible (AA) - Keyboard focus must have a visible indicator.
- 2.4.11 Focus Not Obscured (Minimum) (AA) - When an element gets focus, it is not entirely hidden by other content. (New in 2.2)
- 2.5.1 Pointer Gestures (A) - Multipoint or path-based gestures must have a single-pointer alternative.
- 2.5.2 Pointer Cancellation (A) - Down-event alone must not trigger actions; allow abort/undo by moving away before release.
- 2.5.3 Label in Name (A) - A control's accessible name must contain its visible label text.
- 2.5.4 Motion Actuation (A) - Functions triggered by device motion must also work via UI controls and be disableable.
- 2.5.7 Dragging Movements (A) - Any drag operation must have a single-pointer alternative that isn't a drag. (New in 2.2)
- 2.5.8 Target Size (Minimum) (AA) - Pointer targets are at least 24×24 CSS px, or have enough spacing. (New in 2.2)
- 3.1.1 Language of Page (A) - The default human language of each page is set programmatically.
- 3.1.2 Language of Parts (AA) - Passages in a different language are marked with their own lang attribute.
- 3.2.1 On Focus (A) - Moving focus to a component must not trigger an unexpected change of context.
- 3.2.2 On Input (A) - Changing a setting must not auto-trigger a context change unless the user was warned.
- 3.2.3 Consistent Navigation (A) - Repeated navigation appears in the same relative order across pages
- 

# rem vv em

```
Use rem on font size, margins, paddings,
Use em for buttons, components which should grow relative to parent.
```

### Change the font-size of parent and observer child

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>rem vs em</title>

<style>
    .parent {
        font-size: 25px;
    }
    .child {
        font-size: 2em;
    }
</style>
</head>

<body>
    <div class="parent">
        Parent Text
        <div class="child">
            Child Text
        </div>
    </div>
</body>
</html>
```

# Shortcuts

`tab` : next

`shift` + `tab` : go back

# docs

https://www.w3.org/WAI/ARIA/apg/patterns/

# Code

```html

<label>Email: <span aria-hidden="true">*</span>
<input id="email" type="email" required>

This will not read Email asterisk".
This will read "Email"

<input
  autocomplete="name" <!-- Expect Full Name -->
  autocomplete="given-name" <!-- Expect First Name -->
  autocomplete="family-name"
  autocomplete="email"
  autocomplete="tel"
  autocomplete="password"
  autocomplete="current-password"
  autocomplete="new-password"
  autocomplete="street-address"
  autocomplete="postal-code"
  autocomplete="postal-code"
>

<audio controls src="audio.mp3"></audio>
<a href="/refund-transcirpt">Read full transcript</a>

<video src="demo.mp4" controls>
  <track
      kind="subtitles | captions | descriptions | chapters | metadata"
      src="english.vtt"
      srclang="en"
      label="English"
      default>
  <track
      kind="subtitles | captions | descriptions | chapters | metadata"
      src="hindi.vtt"
      srclang="hi"
      label="Hindi">
</video>

<section
  aria-labelledby="news-heading"
><h2 id="news-heading">Latest News</h2>
</section>

This will read "Latest News, region"

<div role="button" tabindex="0"
  aria-disabled="true"
>Save<div>

<button
  aria-label="Close"
><svg><!-- close icon --></svg>
</button>

<span id="title">Delete File</span>
<button
  aria-labelledby="title"
>🗑️</button>

This will read "Delete File, button"

<div
  aria-live="polite | assertive | off"
  aria-relevant="additions | removals | text | all"
  aria-atomic="true | false"
  aria-busy="true | false"
></div>
```

# Accordion 

https://www.w3.org/WAI/ARIA/apg/patterns/accordion/examples/accordion/
