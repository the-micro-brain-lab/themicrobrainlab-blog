# Me

I'm Minh, a quantitative researcher @ [The µ-brain Lab](https://themicrobrainlab.netlify.app).
This site contains somes notes of my journey.

---

## Setting up this webpage

1. Setup hugo site ( https://gohugo.io/getting-started/quick-start ).

2. Install Xie's theme ( https://github.com/yihui/hugo-xmin ) into `themes/hugo-xmin`.

3. Add CMU font into `static/css` folder. The `static/css/font.css` file will be used. The style of the page is from `themes/hugo-xmin/static/css/style.css`.

4. Setup `Katex` for fast math rendering by adding [its css and js files](https://katex.org/docs/browser.html) to `themes/hugo-xmin/layouts/partials/head_custom.html`.
(This can also be done by placing the initial code for loading these files into a custom css file in `static` and add this custom css to `config.toml`. )

5. Setup code highlighting in `config.toml` ( https://gohugo.io/content-management/syntax-highlighting )

```toml {linenos=table, hl_lines=[12]}
[markup]
  [markup.highlight]
    anchorLineNos = false
    codeFences = true
    guessSyntax = false
    hl_Lines = ""
    lineAnchors = ""
    lineNoStart = 1
    lineNos = false
    lineNumbersInTable = true
    noClasses = true
    style = "borland"
    tabWidth = 4
```

## Basic command

+ Create new post:
`
hugo new posts/my-first-post.md
`