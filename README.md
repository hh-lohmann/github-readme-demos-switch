###### Concept

# GitHub README demos switch

Markdown snippet to switch demos link to local dev version instead of display on GitHub Pages

A link to demos with really running code is a valuable feature for code projects, and GitHub Pages is a good tool for rendering demo code hosted in a GitHub repo, but for development it makes more sense to be linked to the code for the demos instead of their rendered view on GitHub Pages.

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
      See <a href="https://OWNER.github.io/REPO/demos"
      onclick="if( location.hostname.replace( /\d/g, '' ).replaceAll( '.', '' ) === ''
      || location.hostname === 'localhost' ){ this.href='./demos/';
      alert( 'Dev environment detected - switching to local version' ); }"
      >demos</a><span style="display:none;"> on GitHub Pages for this repo</span>
    </p>
    ```

  * For npm publish version (npmjs.com / npmx.dev = always repo view only = no switch)
    ```md
    <!-- see https://hh-lohmann.github.io/github-readme-demos-switch -->
    See [demos](https://OWNER.github.io/REPO/demos)
    ```

* **From demos to README**

  * Only relevant for GitHub since demos are to be rendered only there
    ```html
    <!-- see https://hh-lohmann.github.io/github-readme-demos-switch -->
    <p id="github_readme_demos_switch">
      See <a href="https://OWNER.github.io/REPO"
      onclick="if( location.hostname.replace( /\d/g, '' ).replaceAll( '.', '' ) === ''
      || location.hostname === 'localhost' ){ this.href='/';
      alert( 'Dev environment detected - switching to local version' ); }"
      >main page</a> for general information about ...project-title...
    </p>
    ```


## Installation

Copy appropriate example from [Synopsis](#synopsis) to the beginning of target README and replace OWNER with the owner of the repo and REPO with the name of the repo.

Best used in templates for repos.


## Details

  * GitHub repo view does not render HTML, so a GitHub Pages view is linked
  * In dev a GitHub Pages view would require a Pages build for any change to check instead of live reloading, so JavaScript is utilized here to detect a dev environment and reroute the link to the local repo instance
    * NB: JavaScript is stripped off in GitHub repo view
  * "dev environment" is defined by using "localhost" or a numerical ID as hostname
    * NB RegEx: `.replace( /\d/g, '' ).replaceAll( '.', '' )` instead of `location.hostname.replace( /[\d\.]/g, '' )` to avoid `[]` which may mislead Markdown parsers to read it as link syntax
  * Unfortunately GitHub repo view displays `<script>` tags and their contents as literal content (for security), so the JavaScript here has to be pressed into an "onclick"
  * The contextualizing "on GitHub Pages for this repo" is not displayed if already on GitHub Pages via style "display:none"
