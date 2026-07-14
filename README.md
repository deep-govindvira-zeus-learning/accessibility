# accessibility (Text Info + Audio Info)


# Shortcuts

`tab` : next

`shift` + `tab` : go back

# docs

https://www.w3.org/WAI/ARIA/apg/patterns/

# Code

```html

<section
  aria-labelledby="news-heading"
><h2 id="news-heading">Latest News</h2>
</section>

This will read "Latest News, region"

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
