---
title: Papi docs

language_tabs:
  - php

toc_footers:
  - <a href='http://github.com/wp-papi/papi'>Fork me on GitHub</a>

includes:
  - actions
  - api
  - box
  - custom_property
  - page_type
  - properties
  - property_filters
  - setting_filters

search: true
---

# Introduction

Papi has a different approach on how to work with fields and page types in WordPress. The idea is coming from how Page Type Builder in EPiServer works and has been loved by the developers.

So we though why don't use the same approach in WordPress? Papi is today running in production and has been easy to work with when it came to add new fields. Papi don't have any admin user interface where should add all fields, we use classes in PHP, where one class represents one page type and in your class you add all fields you need. It's that easy!

# Page Type Directory

Papi does require a directory in your theme, plugin or somewhere in your WordPress site where your page types exists. You can add multiplied directories.

```php
<?php

/**
 * Register page types directory with Papi.
 */

add_filter('papi/settings/directories', function () {
  return __DIR__ . '/includes/page-types';
});
```
