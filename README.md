# [Sage sans Bootstrap](https://roots.io/sage/)

Sage WordPress starter theme without Bootstrap. 

## Features
* Framework-free, Bootstrap has been completely removed
* WordPress Generated Classes have been re-added from the Codex [(see here for more info)](https://codex.wordpress.org/CSS#WordPress_Generated_Classes)

## Manually removing Bootstrap from Sage
1. Clone the official Sage repo:
    ```
    https://github.com/roots/sage.git <theme_name>
    ```

2. Edit *bower.json*, remove all Bootstrap-related depedencies and overrides; the modifed file should look as follows:
    ```
    {
        "name": "sage",
        "homepage": "https://roots.io/sage/",
        "authors": [
            "Ben Word <ben@benword.com>"
        ],
        "license": "MIT",
        "private": true,
        "dependencies": {
        },
        "overrides": {
        }
    }
    ```
3. Blank out the contents of the following files, **do not** delete the files themselves:
    * assets/styles/_variables.scss
    * assets/styles/_comments.scss
    * assets/styles/_forms.scss
    * assets/styles/_grid.scss
    * assets/styles/_wp-classes.scss

4. Re-add the *WordPress Generated Classes* from the [WordPress Codex](https://codex.wordpress.org/CSS#WordPress_Generated_Classes) to the following file:
    * assets/styles/_wp-classes.scss

5. Run ```bower prune``` and ```gulp``` in the theme's root directory

6. The following line should have automatically been removed from *<theme_root>/assets/styles/main.scss*:
    ```
    @import "../../bower_components/bootstrap-sass/assets/stylesheets/_bootstrap.scss";
    ````

    The code block should now read:
    ```
    // Automatically injected Bower dependencies via wiredep (never manually edit this block)
    // bower:scss
    // endbower
    ```

Sage documentation is available at [https://roots.io/sage/docs/](https://roots.io/sage/docs/).
