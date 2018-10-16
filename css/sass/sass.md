### SASS

1. #### base/

   1. _reset.scss
   2. _typography.scss
   3. ...

2. #### components/

   1. _buttons.scss
   2. _carousel.scss
   3. _cover.scss
   4. _dropdown.scss
   5. _navigation.scss

3. #### helpers/

   1. _variables.scss
   2. _functions.scss
   3. _mixins.scss
   4. _helpers.scss  

4. #### layout/

   1. _grid.scss
   2. _header.scss
   3. _footer.scss
   4. _sidebar.scss
   5. _forms.scss

5. #### pages/

   1. _home.scss
   2. _contact.scss
   3. ...

6. #### themes/

   1. _theme.scss
   2. _admin.scss

7. #### vendors/

   1. _bootstrap.scss
   2. _jquery-ui.scss
   3. ...



### style.scss

```
@charset 'utf-8';

//helps
@import "helps/variables";
@import "helps/function";
@import "helps/mixins";
@import "helps/helpers";

//base
@import "base/normalize";
@import "base/base";
@import "base/typography";

//components
@import "components/icons";
@import "components/form";
@import "components/buttons";
@import "components/tabs";
@import "components/pagination";

//layout
@import "layout/layout";
@import "layout/topbar";
@import "layout/header";
@import "layout/banner";
@import "layout/footer";

//pages
@import "pages/interior";
@import "pages/effect";
@import "pages/login";

```

