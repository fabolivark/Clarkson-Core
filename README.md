[![Build Status](https://travis-ci.org/level-level/Clarkson-Core.svg?branch=master)](https://travis-ci.org/level-level/Clarkson-Core)

# Clarkson Core
A plugin to write Object-Oriented code in combination with the Twig templating engine while keeping the WordPress Way of working in mind.

## Requirements
Composer, that's it.

## Whats does What?

Here is a brief explanation of the basics of Clarkson Core.

### Template Hierachy
Uses the internal [Template Hierarchy](https://developer.wordpress.org/themes/basics/template-hierarchy/) so you can replace `index.php` with `index.twig` or `archive-company.php` with `archive-company.twig` and still have all Posts or CPT's available in "The Loop".


```twig
{% extends "layouts/full-width.twig" %}

{% block content %}
    {% for object in objects %}
        {% include 'partials/teaser.twig' %}
    {% endfor %}
{% endblock %}
```

### Autoloading of WordPress-object classes per Custom Post Type.
It autoloads a default [Clarkson Object](https://github.com/level-level/Clarkson-Core/blob/master/wordpress-objects/Clarkson_Object.php) that is just like `WP_Post` but with some more handy stuff.
When you register a Custom Post Type `ll_company` your custom class `ll_company` gets loaded in the Twig context as `objects` variable within the `archive-company.twig`.  

[More info](https://github.com/level-level/Clarkson-Core/wiki/WordPress-objects) about WordPress objects.

## More documentation

- [Installation](https://github.com/level-level/Clarkson-Core/wiki/Installation)
- [Reference](https://level-level.github.io/Clarkson-Core/phpdoc/)
- [Explanation of loading WordPress Objects](https://github.com/level-level/Clarkson-Core/wiki/WordPress-objects)
- [Everything else](https://github.com/level-level/Clarkson-Core/wiki)

## Tests
Currently 
1. Clone repository `git@github.com:level-level/Clarkson-Core.git clarkson-core`.
1. Run `composer install` in the new `clarkson-core` directory.
1. Run `composer run test`.
