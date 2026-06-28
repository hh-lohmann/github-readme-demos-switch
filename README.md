###### Concept

# GitHub README demos switch

Markdown snippet to switch demos link to local dev version instead of display on GitHub Pages

A link to demos with really running code is a valuable feature for code projects, and GitHub Pages is a good tool for rendering demo code hosted in a GitHub repo, but for development it makes more sense to be linked to the code for the demos instead of their rendered view on GitHub Pages.

Best used in templates for repos, cf. [template-gh](#hh-lohmann-template-gh)

*[hh lohmann &lt;hh.lohmann@gmail.com&gt;](mailto:hh.lohmann@gmail.com?subject=github-readme-demos-switch)*

<!-- see https://hh-lohmann.github.io/github-readme-pages-switch -->
<p align="center" id="github_readme_pages_switch" style="display:none;">
  <b><i>This page may be displayed more optimal in its
  <a href="https://hh-lohmann.github.io/github-readme-demos-switch/">GitHub Pages view</a>
  </i></b>
</p>


## Synopsis

* **From README to demos**

  * For GitHub (serving both for repo view and GitHub Pages, therefore real switch):
    ```html
    <!-- see https://hh-lohmann.github.io/github-readme-demos-switch -->
    <p id="github_readme_demos_switch">
      See <a href="https://...repo-owner....github.io/...repo-name.../demos" onclick="if(location.hostname.replace(/\d/g,'').replaceAll('.','')===''||location.hostname==='localhost'){this.href='./demos/';alert('Dev environment detected - switching to local version');}">demos</a><span style="display:none;"> on GitHub Pages for this repo</span>
    </p>
    ```

  * For npm publish version (npmjs.com / npmx.dev = always repo view only = no switch)
    ```md
    <!-- see https://hh-lohmann.github.io/github-readme-demos-switch -->
    See [demos](https://...repo-owner....github.io/...repo-name.../demos) on GitHub Pages for this repo
    ```

* **From demos to README**

  * Only relevant for GitHub since demos are to be rendered only there
    ```html
    <!-- see https://hh-lohmann.github.io/github-readme-demos-switch -->
    <p id="github_readme_demos_switch">
      See <a href="https://...repo-owner....github.io/...repo-name..." onclick="if(location.hostname.replace(/\d/g,'').replaceAll('.','')===''||location.hostname==='localhost'){this.href='/'; alert('Dev environment detected - switching to local version');}">main page</a> for general information about ...project-title...
    </p>
    ```


## Installation

* **From README to demos**

  * Copy appropriate example from [Synopsis](#synopsis) to a "Demo" section of your project's README
  
  * Replace placeholders
    * `...repo-owner...` with the owner of the repo
      * e.g.: `joe-doe`
    * `...repo-name...` with the name of the repo
      * e.g.: `my-fantastic-project`

* **From demos to README**

  * Copy example from [Synopsis](#synopsis) to to the beginning of your "Demo" page
  
  * Replace placeholders
    * `...repo-owner...` with the owner of the repo
      * e.g.: `joe-doe`
    * `...repo-name...` with the name of the repo
      * e.g.: `my-fantastic-project`
    * `...project-title...` with the name of the repo
      * e.g.: `Approach fantastic things without losing time for planning`




## Details

  * GitHub repo view applies the [Disallowed Raw HTML extension](#github-flavored-markdown-disallowed-raw-html-extension), so a GitHub Pages view is linked where this restriciton is not active
  * In dev a GitHub Pages view would require a Pages build for any change to check instead of live reloading, so JavaScript is utilized here to detect a dev environment and reroute the link to the local repo instance
    * NB: JavaScript is stripped off in GitHub repo view
  * "dev environment" is defined by using "localhost" or a numerical ID as hostname
    * NB RegEx: `.replace( /\d/g, '' ).replaceAll( '.', '' )` instead of `location.hostname.replace( /[\d\.]/g, '' )` to avoid `[]` which may mislead Markdown parsers to read it as link syntax
  * The JavaScript here has to be pressed into an "onclick" since the [Disallowed Raw HTML extension](#github-flavored-markdown-disallowed-raw-html-extension) in GitHub repo view would make a `<script>` tag to literal content

  * The contextualizing "on GitHub Pages for this repo" is not displayed if already on GitHub Pages via style "display:none"


## References

### GitHub Flavored Markdown: Disallowed Raw HTML (extension)
  * <https://github.github.com/gfm/#disallowed-raw-html-extension->

### hh lohmann: template-gh
  * Template for new GitHub repo, especially with `gh repo create ... -p`
  * <https://github.com/hh-lohmann/template-gh>


<!-- see https://hh-lohmann.github.io/html-endspacer -->
<p id="endspacer" data-version="0.2.0" title="Endspacer - helps to align scrolling and positioning link targets | Scroll up to content or click / touch to jump to page top" align="center"><a href="#top"><img alt="Endspacer: './markdown-assets/endspacer.png' missing - see https://hh-lohmann.github.io/html-endspacer" src="./markdown-assets/endspacer.png" height="1000" width="100%"><br>[top]</a></p>
