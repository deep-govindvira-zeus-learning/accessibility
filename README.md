# accessibility (Text Info + Audio Info)

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
