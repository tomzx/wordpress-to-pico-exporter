WordPress to Pico Exporter
============================

One-click WordPress plugin that converts all posts, pages, taxonomies, metadata, and settings to Markdown which can be dropped into [Pico CMS](http://pico.dev7studios.com/).

Features
--------

* Converts all posts, pages, and settings from WordPress for use in Pico
* Export what your users see, not what the database stores (runs post content through `the_content` filter prior to export, allowing third-party plugins to modify the output)
* Converts all `post_content` to Markdown Extra (using Markdownify)
* Converts all `post_meta` and fields within the `wp_posts` table to meta data for parsing with Pico
* Generates a `_config.yml` with all settings in the `wp_options` table
* Outputs a single zip file with `_config.yml`, pages, and `_posts` folder containing `.md` files for each post in the proper Pico CMS naming convention and file tree
* No settings. Just a single click.

Usage
-----

1. Place plugin in `/wp-content/plugins/` folder
2. Make sure `extension=zip.so` line is uncommented in your `php.ini`
3. Activate plugin in WordPress dashboard
4. Select `Export to Pico` from the `Tools` menu

Command-line Usage
------------------

If you're having trouble with your web server timing out before the export is complete, or if you just like terminal better, you may enjoy the command-line tool.

It works just like the plugin, but produces the zipfile on STDOUT:

    php pico-export-cli.php > pico-export.zip

Alternatively, if you have [WP-CLI](http://wp-cli.org) installed, you can run:

```
wp pico-export > export.zip
```

The WP-CLI version will provide greater compatibility for alternate WordPress environments, such as when `wp-content` isn't in the usual location.

Changelog
---------

**[View Past Releases](https://github.com/z720/wordpress-to-pico-exporter/tags)**

### 1.5 

* Initial Release for Pico Conversion

 
**Previous history before fork from [wordpress-to-jekyll-exporter](https://github.com/benbalter/wordpress-to-jekyll-exporter/tags)**

### 1.4

* Made license explicit
* Removed word-wrap from YAML export to prevent breaking permalinks

### 1.3

* Use [fork of Markdownify](https://github.com/Pixel418/Markdownify) rather than external API to convert content from HTML to markdown
* Better memory utilization for larger sites, props @ghelleks

### 1.2

* Commmand-line support, props @ghelleks and @scribu

### 1.1

* Use WP_Filesystem for better compatability
* 1.1.1 - Use heckyeahmarkdown to prevent PHP errors when Markdownify chokes on malformed HTML
* 1.1.2 - clarify zip.so requirement in readme

### 1.0 

* Initial Release

License
-------

The project is licensed under the GPLv3 or later

