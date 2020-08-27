# SASS Set up WordPress

Simple starting set up of SCSS files for integration in to WordPress including Bootstrap, fonts, common rules and interesting variables.

## Folder structure

```

fonts   /Merriweather.woff
        /OpenSans.woff (stack)

scss    /bootstrap  /mixins
                    /utilities
                    /vendor
                    /bootstrap.scss
        
        /wysiwyg-styles /_style-editor.scss

        /_animate.scss
        /_fonts.scss
        /_footer.scss
        /_front-page.scss
        /_gallery.scss
        /_general.scss
        /_header.scss
        /_modules.scss
        /_page.scss
        /_sliders.scss
        /_style-header.scss
        /_typography.scss
        /_variables.scss
        /_wordpress.scss

```

## How to use

[Install SASS](https://sass-lang.com/install) if not done so already.

The SASS set up will compile all of the .scss files into one style.css file in the root of the project folder.

Copy Contents of folder into the root of your project and run the following command from the command line or Git Bash:

NOTE: Run from the root of your project folder where style.css should be.

### Unminified version

```

sass --watch scss/_modules.scss:style.css

```

### WYSIWYG editor styles

NOTE: Run from the root of your project folder, this will produce style-editor.css.

```

sass --watch scss/wysiwyg-styles/_style-editor.scss:style-editor.css --style compressed

```

This should be included in the functions.php of your WordPress theme:

```

/**
 * Add support for editor styles.
 */
add_theme_support( 'editor-styles' );


/**
 * Locate TinyMCE custom stylesheet
 */
add_editor_style(get_template_directory_uri().'/style-editor.css');

```

## Existing styles

If you are working with an existing stylesheet you can copy it into the _wordpress.scss_ file or create a new one and @import it in the _modules.scss_.

The SASS set up will compile all of the .scss files into one style.css file replacing any style.css file that was there before.