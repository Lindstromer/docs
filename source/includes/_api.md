# API

## current_page

```php
<?php

/**
 * Example of `current_page` function.
 */

echo current_page()->twitter_url;

// will be the same as
echo papi_field('twitter_url');
```

Get the current Papi page with all fields.

### Parameters

No parameters exists.

## papi_field

```php
<?php

/**
 * Example of `papi_field` function.
 */

echo papi_field('twitter_url');
```

### Description

The post id will be added automatic if you are one a post, page or custom post type page.

When fetching values from another post this argument will be required.

You can also use [the_papi_field](#the_papi_field) to display it without `echo`

### Parameters

Parameter | Default | Required | Description
----------|---------|----------|------------------------------------------------
$post_id  | null    | no       | The post id will be added automatic if you are one a post, page or custom post type page. When fetching values from another post this argument will be required
$slug     |         | yes      | The property slug to fetch value from
$default  | null    | no       | When a default value is passed as argument it will use that value as return value and echo it if the property value is empty or don't exists

## papi_fields

```php
<?php

/**
 * Example output from `papi_fields` function.
 */

array(
  'Content' => array(
    'top_module',
    'feature_module',
    'show_feature_module'
  )
);
```

### Description

Papi fields will return a array with meta box title as keys and array of all Papi field slugs in that meta box.

### Parameters

No parameters exists.

## papi_get_page

```php
<?php

/**
 * Example of `papi_get_page` function.
 */

echo papi_get_page()->twitter_url;

// with post id
echo papi_get_page(2)->twitter_url;
```

### Description

When given a post id it will fetch the Papi page for that post id instead.

The papi page function will do the same as current page function if no post id is used as a argument.

### Parameters

Parameter | Default | Required | Description
----------|---------|----------|------------------------------------------------
$post_id  | null    | no       | The post id will be added automatic if you are one a post, page or custom post type page. When fetching values from another post this argument will be required

## papi_property

```php
<?php

/**
 * Example of `papi_property` function.
 */

// my-page-type.php
$this->box('My meta box', [
  papi_property('properties/my-image.php', [
    'slug' => 'my_meta_box_image'
  ])
]);

// properties/my-image.php
return papi_property([
  'type'  => 'image',
  'title' => 'Image',
  'slug'  => 'custom_image_slug'
]);
```

### Description

This argument is only used when you load a template file, the array will be used to override property options from the template file.

This function will be the same as `$this->property` method on a page type.

When using a shared property file or another file that the property are stored in you can used it as a template file.

This is great to use when you will share properties over many page types and it will be less code to write.

### Parameters

Parameter         | Default | Required | Description
------------------|---------|----------|----------------------------------------
$file_or_options  |         | yes      | File path or a array containing property options
$values           | array() | no       | The values to override the template values with

## papi_tab

```php
<?php

/**
 * Example of `papi_tab` function.
 */

// my-page-type.php
$this->box('My meta box', [
  $this->tab('tabs/image-tab.php', [
    'title' => 'Background'
  ])
]);

// tabs/image.php
return papi_tabs([
  'title' => 'Images',
  'slug'  => 'custom_image_slug'
], [
  papi_property('properties/my-image.php'),
  papi_property([
    'type'  => 'string',
    'title' => 'Name',
    'slug'  => 'name'
  ])
]);
```

### Description

This argument is only used when you load a template file, the array will be used to override tab options from the template file.

This function will be the same as `$this->tab` method on a page type.

When using a shared tab file or another file that the tab are stored in you can used it as a template file.

This is great to use when you will share tabs over many page types and it will be less code to write.

### Parameters

Parameter         | Default | Required | Description
------------------|---------|----------|----------------------------------------
$file_or_options  |         | yes      | Title, file path or a array containing tab options
$properties       | array() | no       | The values to override the template values with or properties

## papi_template

```php
<?php

/**
 * Example of `papi_template` function.
 */

// my-page-type.php
$this->box('My meta box', [
  $this->property([
    'type'     => 'dropdown',
    'title'    => 'Dropdown',
    'slug'     => 'my_dropdown',
    'settings' => papi_template('settings/dropdown.php')
  ])
]);

// settings/dropdown.php
return [
  'items' => [
    'White' => '#ffffff',
    'Black' => '#000000'
  ]
];
```

### Description

`papi_property` function uses this function load template file. This function can be used to load template files that returns arrays. It can be handy when you will have to repeater or dropdown values in another file.

### Parameters

Parameter         | Default | Required | Description
------------------|---------|----------|----------------------------------------
$file_or_options  |         | yes      | File path to template file
$properties       | array() | no       | The values to override the template values with

## the_papi_field

```php
<?php

/**
 * Example of `the_papi_field` function.
 */

the_papi_field('twitter_url')

// with post id
the_papi_field(1, 'twitter_url')

// with default value
the_papi_field(1, 'twitter_url', 'http://twitter.com/frozzare');
```

### Description

This function will echo the value of a property using the property slug.

You can also use [papi_field](#papi_field) to fetch the value into a variable.

### Parameters

Parameter | Default | Required | Description
----------|---------|----------|------------------------------------------------
$post_id  | null    | no       | The post id will be added automatic if you are one a post, page or custom post type page. When fetching values from another post this argument will be required
$slug     |         | yes      | The property slug to fetch value from
$default  | null    | no       | When a default value is passed as argument it will use that value as return value and echo it if the property value is empty or don't exists
