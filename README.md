# Pelican-Chameleon

Pelican-chameleon, originally pelican-iliork, is a single-column blog-writing theme based on [Bootstrap][] for [pelican][]. It provides a elegant way to switch among different [Bootswatch][] themes (please see [Screen Shots][] below) like a **chameleon**.

Pelican-chameleon is built on [Bootstrap][] 3. Some notable features are:

- [Bootswatch][] theme support
- The css of this theme can be overwritten very easily
- Nestable menu items
- Google custom search support
- Multiple authors co-blogging

# Demo

Please check out

* **[http://yuex.in]()**, using [flatly][], mainly in Chinese.
* **[Screen Shots][]**, chameleon with different bootswatch theme

# Congfiguration

## Bootstrap 3 Version and URL Overwriting

You can overwrite the default url of boostrap css and js by setting following variables. If these variables are not defined, the theme will use the 3.0.0 version of bootstrap.

    BS3_URL = 'https://maxcdn.bootstrapcdn.com/bootstrap/3.3.1/css/bootstrap.min.css'
    BS3_JS  = 'https://maxcdn.bootstrapcdn.com/bootstrap/3.3.1/js/bootstrap.min.js'

## Use Bootstrap Theme

You can change the default appearance of Bootstrap to any Bootstrap theme you like. `BS3_THEME` defines the url of the theme's css file; `BS3_THEME_NAME` and `BS3_THEME_HOMEPAGE` define the name and url of bootstrap theme, which are used in the footer text.

See [Screen Shots][] for demos. For more theme to choose from, have a look at [Bootswatch][].

    # using flatly of bootswatch.com
    BS3_THEME = 'http://bootswatch.com/flatly/bootstrap.min.css'

## Theme CSS Overwriting

You can use your own css file for code highlight. If you do not provide this value, pelican-chameleon will the default css file, `solarized-light.css`.

pelican-chameleon provides a easy to way to overwrite the css style of pelican-chameleon by providing `CODE_HIGHLIGHT` and `CSS_OVERWRITE`. When switching Boostrap themes, you may find these useful.

For example, if you want to use your preferred code highlight css, set the following option in your `pelicanconf.py`

    CODE_HIGHLIGHT = 'url to your favorite code highlight css'

If you want to overwrite the css style of pelican-chameleon iteself, use

    CSS_OVERWRITE = 'url to your css'

## Nestable Menu Items

Menu items in pelican-chameleon is nestable. `MENUITEMS` are rendered as a top navbar. Nested menu items are rendered together as a drop-down button on the top navbar. But only 1-level nesting is allowed; it's clumsy, and perhaps wrong, to nest too much items in the menu. Here's a example.

    MENUITEMS = [
        ('Home', '/'),
        ('Archives', [
            ('Tags', '/tags.html'),
            ('Categories', '/categories.html'),
            ('Chronological', '/archives.html'),
            ]),
        ('Social', [
            ('Email', 'url to your email'),
            ('Github', 'url to your github'),
            ('Facebook', 'url to your facebook'),
            ]),
        ]

**NOTE**: If you use absolute domain like '/foo/bar/baz', your SITEURL will be inserted at the head to work around the redirection issue under non-root domain hosting like 'http://example.com/~user/'.

## Google Custom Search

Put following in your MENUITEMS to have a Google custom search box on top navbar. 'Search' is the key, mandatory.

    MENUITEMS = [
        ('Search', 'your Google custom search value'),
        ]

## Favicon

To use your favicon, set following option in `pelicanconf.py`

    FAVICON = u'url to your favicon'
    FAVICON_TYPE = u'png or jpeg or whatever'

## Multiple Author
You can direct the author link to whichever you want. It's not hard-coded in the theme.

    AUTHORS = {
        u'jack': '/about.html',
        u'mary': 'http://mary.info',
        u'tony': 'http://tony.me',
    }

# Screen Shots

pelican-chameleon with default boostrap theme

![default](./screenshot/default.png)

pelican-chameleon with [amelia][]

![amelia](./screenshot/amelia.png)

pelican-chameleon with [cosmo][]

![cosmo](./screenshot/cosmo.png)

pelican-chameleon with [superhero][]

![superhero](./screenshot/superhero.png)

pelican-chameleon with [united][]

![united](./screenshot/united.png)

[pelican]: https://github.com/getpelican/pelican
[Bootstrap]: http://getbootstrap.com
[Bootswatch]: http://bootswatch.com
[flatly]: http://bootswatch.com/flatly/
[amelia]: http://bootswatch.com/amelia/
[cosmo]: http://bootswatch.com/cosmo/
[superhero]: http://bootswatch.com/superhero/
[united]: http://bootswatch.com/united/
[Screen Shots]: #screen-shots
