###### Concept

# GitHub README Pages switch

Markdown snippet that links to GitHub Pages view for improved UI

Markdown rendering is restricted in GitHub repo view and accordingly on npmjs.com / npmx.dev. the code snippet here gives a short information and a link to the GitHub Pages view richer UI. 

*[hh lohmann &lt;hh.lohmann@gmail.com&gt;](mailto:hh.lohmann@gmail.com?subject=github-readme-pages-switch)*

<!-- see https://hh-lohmann.github.io/github-readme-pages-switch -->
<p align="center" id="github_readme_pages_switch" style="display:none;">
  <b><i>This page may be displayed more optimal in its
  <a href="https://hh-lohmann.github.io/github-readme-pages-switch/">GitHub Pages view</a>
  </i></b>
</p>


## Synopsis

For GitHub (serving both for repo view and GitHub Pages, therefore real switch):

```html
<!-- see https://hh-lohmann.github.io/github-readme-pages-switch -->
<p align="center" id="github_readme_pages_switch" style="display:none;">
  <b><i>This page may be displayed more optimal in its
  <a href="https://OWNER.github.io/REPO/">GitHub Pages view</a>
  </i></b>
</p>
```

For npm publish version (npmjs.com / npmx.dev = always repo view only = no switch)

```html
<!-- see https://hh-lohmann.github.io/github-readme-pages-switch -->
<b><i>This page may be displayed more optimal in its
<a href="https://OWNER.github.io/REPO/">GitHub Pages view</a>
</i></b>
```


## Examples

```html
<!-- see https://hh-lohmann.github.io/github-readme-pages-switch -->
<p align="center" id="github_readme_pages_switch" style="display:none;">
  <b><i>This page may be displayed more optimal in its
  <a href="https://hh-lohmann.github.io/github-readme-pages-switch/">GitHub Pages view</a>
  </i></b>
</p>
```



## Demo

Cf. actual usage here [at top](https://hh-lohmann.github.io/github-readme-pages-switch/README.md)


## Installation

Copy appropriate example from [Synopsis](#synopsis) to the beginning of target README and replace OWNER with the owner of the repo and REPO with the name of the repo (cf. [Examples](#examples)).

Best used in templates for repos.


## Details

  * While GitHub Pages support full HTML including scripting, GitHub repo view renders only basic text formatting by additional HTML in README.md. Since this applies also to "style" attributes, the HTML paragraph containing the link to GitHub Pages is not displayed on GitHub Pages due to `display:none`, but displayed as with no "style" attribute in GitHub repo view.

