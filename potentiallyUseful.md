- To create custom terms page:
  - create a file named `<SINGLE>.terms.html` in `layouts/taxonomy`
    - This is the highest look up order (or spcificity) thus, it will get displayed
    - Read more about lookup order [here](https://gohugobrasil.netlify.com/templates/taxonomy-templates/)

- You can print the currnet context that you're in using
  - ``<script>console.log({{ . }})</script>``
    - This will be avilable in console of browser