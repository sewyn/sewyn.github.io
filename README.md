# Personal website

There are two pages:

| File | Web URL |
| --- | --- |
| [`simple.html`](./simple.html) | <https://sewyn.github.io/simple.html> |
| [`index.html`](./index.html) | <https://sewyn.github.io> (on the web, "index" is the default page) |

## HTML tags

How to know what tag to use for a thing? I'm afraid this is just learning how HTML works. Lots of guides online are bad. This one is simple.

<http://www.simplehtmlguide.com/cheatsheet.php>

## How to edit site

Since HTML is just a text file, you can use any text editor. You can just use notepad if you want. Simply, you can open the HTML file in your browser, change the text with notepad, then reload the page in the browser to see the changes.

You will also need to commit the changes with Git. You can do this by downloading [GitHub Desktop](https://desktop.github.com/) and getting confused a lot. You can also use many other methods and get confused a bunch more.

### Online

Press `.` when on the GitHub page to open the web editor. This has the editor (first tab on left) for editing, and a Git tab (third tab on left) for committing the changes to the GitHub repository.

### VSCode

Download VSCode and get lost in the many menus. It is very nice though, as it has autocompletion, nice colours, etc etc etc.

## Stuff you could do

### "preview" images

Make so when you click/tap an image it links to the image in full screen (i.e., opens image in browser). i.e., wrapping

```html
<img src="images/cryptidhunt_day2.jpg" alt="Inktober day 2" />
```

in

```html
<a href="images/cryptidhunt_day2.jpg">
    <img src="images/cryptidhunt_day2.jpg" alt="Inktober day 2" />
</a>
```

### add links to headers

Hover over the header above. There's a little link icon. So now you can share the website AND the scroll position with someone. You can already do this yourself by linking to (for example) <https://sewyn.github.io#day2>. This suggestion is just adding the link to the headers. It could look like

```html
<h3 id="day2">DAY 2 - PRIZED POSSESSION <a href="#day2">🔗</a></h3>
```

You could also use <https://www.bryanbraun.com/anchorjs/> (I use this on [my website](https://blog.alifeee.co.uk/sketch-your-society/) - see for example) by including

```html
...
<script src="https://cdn.jsdelivr.net/npm/anchor-js/anchor.min.js"></script>
<script>
  anchors.add();
</script>
...
```

in `<head>`

### Move content to a markdown file

This is how I do my [blog](https://blog.alifeee.co.uk)

Instead of the content in HTML...

```html
...
<main>
    <h2>This is some content!</h2>
    <p>
        It has to be edited in the HTML and is quite hard to write with all the a <a href="http://www.simplehtmlguide.com/cheatsheet.php">tags</a> and <i>cool</i> elements everywhere
    </p>
</main>
...
```

...it can be written in (for example) a [markdown](https://www.markdownguide.org/getting-started/) file...

```md
## This is some content!

It is now editable in [Markdown](https://www.markdownguide.org/getting-started/), which is much more readable by a human, and harder to make mistakes. Pretty *cool*, eh?
```

...and then loaded into the HTML with *code*, for example (the simplest one, which I use), [`<zero-md>`](https://github.com/zerodevx/zero-md)...

```html
...
  <script
    type="module"
    src="https://cdn.jsdelivr.net/gh/zerodevx/zero-md@2/dist/zero-md.min.js"
  ></script>
...
<main>
    <zero-md src="markdown-file.md"></zero-md>
</main>
```
