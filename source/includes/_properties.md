# Properties

```php
<?php

/**
 * Example of the default options.
 */

papi_property([
  'capabilities' => array(),
  'default'      => '',
  'description'  => '',
  'disabled'     => false,
  'lang'         => false,
  'raw'          => false,
  'required'     => false,
  'settings'     => array(),
  'sidebar'      => true,
  'slug'         => '',
  'sort_order'   => 100,
  'title'        => '',
  'type'         => ''
])
```

Papi does support 19 core properties (a field is a property in the page type) to start with and you can easy create your own using our [Yeoman generator](). The are several keys that all properties have.

Key          | Default      | Description
-------------|--------------|---------------------------------------------------
capabilities | array()      | Can be a string with a role or capability or a array with many values
default      | empty string | The default value that are presented in the property
description  | empty string | The introduction text that will appear below the title text of the property. You could write your help text here. Since version 1.2.0 you can have "\n" to create new lines in the description
disabled     | false        | Disable the property, won’t show in WordPress admin
lang         | false        | When using this key you can specify which language will show the property
raw          | false        | This will render the property without a table, good to use when creating a custom property that uses other properties
required     | false        | By default all fields are non required in Papi but this can be changed with required option
sidebar      | true         | Boolean that shows the sidebar on each property. If false the sidebar won’t show
settings     | array()      | Array with custom settings for the property
sort_order   | 1000         | Numeric value, lowest value in the meta box will be at the top and the highest value at the bottom
slug         | empty string | The slug of property. If empty or not used the title will be generated to slug value
title        | empty string | The title of the property. Can be empty for blank title
type         | empty string | The property type (lower case is preferred to use)

**Note:** be sure to have different slug for each properties on a page type, the same slug will not work great and you will lose data if you are using same slug for multiple properties.

## Bool

**type** `bool`

```php
<?php

/**
 * Example of bool.
 */

papi_property([
  'title'    => 'True or false?',
  'slug'     => 'my_true_or_false_slug',
  'type'     => 'bool'
])

/**
 * Example output.
 */

boolean true
```

### Description

The property output a single checkbox, when clicked the output value will be true otherwise false.

### Settings

No settings exists.

## Checkbox

**type** `checkbox`

```php
<?php

/**
 * Example of checkbox.
 */

papi_property([
  'title'    => 'Categories',
  'slug'     => 'my_categories_slug',
  'type'     => 'checkbox',
  'settings' => [
    'items' => [
      'White' => '#ffffff',
      'Black' => '#000000'
    ]
  ]
])

/**
 * Example output.
 */

Array
(
  [0] => '#ffffff'
)
```

### Description

With this property you can add multiple checkboxes. The key is the value that the user will se in the WordPress admin and the value is the value saved in the database.

### Settings

Key      | Default | Description
---------|---------|------------------------------------------------------------
items    | array() | Array with checkboxes, value or key/value
selected | array() | The seleceted key or array of keys

## Color

**type** `color`

```php
<?php

/**
 * Example of color.
 */

papi_property([
  'title'    => 'Color',
  'slug'     => 'my_color_slug',
  'type'     => 'color'
])

/**
 * Example output.
 */

string '#ffffff'
```

### Description

The property output the WordPress color picker.

### Settings

Key        | Default | Description
-----------|---------|----------------------------------------------------------
show_input | true    | Show the text input
palettes   | array() | Array with hex colors

## Datetime

**type** `datetime`

```php
<?php

/**
 * Example of datetime.
 */

papi_property([
  'title'    => 'Datetime',
  'slug'     => 'my_datetime_slug',
  'type'     => 'datetime'
])

/**
 * Example output.
 */

string '2014-11-21'
```

### Description

The date property has a picker build in using [Pikaday](https://github.com/owenmead/Pikaday) with time support.

### Settings

Key          | Default             | Description
-------------|---------------------|------------------------------------------
format       | YYYY-MM-DD hh:mm:ss | Show the text input
show_seconds | false               | Array with hex colors
show_time    | true                | Array with hex colors
use_24_hours | false               | Array with hex colors

## Divider

**type** `divider`

```php
<?php

/**
 * Example of divider.
 */

papi_property([
  'title'       => 'Divider',
  'type'        => 'divider',
  'description' => 'Non volutpat ultricies bibendum odio luctus.'
])

/**
 * Example output.
 */

string '#ffffff'
```

### Description

This property don't output any form or something like that. It outputs a h3 tag with the title inside and the description below.

### Settings

No settings exists.

## Dropdown

**type** `dropdown`

```php
<?php

/**
 * Example of select.
 */

papi_property([
  'title'    => 'Dropdown',
  'slug'     => 'my_dropdown_slug',
  'type'     => 'dropdown',
  'settings' => [
    'items' => [
      'White' => '#ffffff',
      'Black' => '#000000'
    ]
  ]
])

/**
 * Example output.
 */

string '#ffffff'
```

### Description

With this property you can add a dropdown. The key is the value that the user will se in the WordPress admin and the value is the value saved in the database.

### Settings

Key      | Default            | Description
---------|--------------------|-------------------------------------------------
items    | array() (no limit) | Array with options, value or key/value
selected | empty string       | The select item that will be selected from start. The value should match a key of your items

## Editor

**type** `editor`
**since** `1.2.0`

```php
<?php

/**
 * Example of Property Editor.
 */

papi_property([
  'title' => 'Editor',
  'slug'  => 'my_editor_slug',
  'type'  => 'editor'
])

/**
 * Example output.
 */

// String of text.
```

### Description

The WordPress editor.

### Settings

No settings exists.

## Gallery

**type** `gallery`
**since** `1.2.0`

```php
<?php

/**
 * Example of gallery.
 */

papi_property([
  'title' => 'Gallery',
  'slug'  => 'my_gallery_slug',
  'type'  => 'gallery'
])

/**
 * Example output.
 */

Array(
  stdClass Object
  (
      [width] => 800
      [height] => 600
      [file] => '2014/09/cube.jpg'
      [sizes] => Array
        (
          [thumbnail] => Array
          (
            [file] => 'cube-150x150.jpg'
            [width] => 150
            [height] => 150
            [mime-type] => 'image/jpeg'
          )

          [medium] => Array
          (
            [file] => 'cube-300x225.jpg'
            [width] => 300
            [height] => 225
            [mime-type] => 'image/jpeg'
          )

      )

      [image_meta] => Array
        (
          [aperture] => 0
          [credit] =>
          [camera] =>
          [caption] =>
          [created_timestamp] => 0
          [copyright] =>
          [focal_length] => 0
          [iso] => 0
          [shutter_speed] => 0
          [title] =>
          [orientation] => 1
        )
      [alt] => 'Alt text'
      [caption] => 'Caption text'
      [description] => 'Description text'
      [id] => 6
      [is_image] => 1
      [title] => 'Title text'
      [url] => 'http://site.com/wp-content/uploads/2014/09/cube.jpg'
  )
)
```

### Description

With this property you can add a multiple image from the WordPress media library.

### Settings

No settings exists.

## Html

**type** `html`

```php
<?php

/**
 * Example of html.
 */

papi_property([
  'title'    => 'Information',
  'type'     => 'html',
  'settings' => [
    'html' => '<p>Hello, world</p>'
  ]
])

/**
 * Example output.
 */

string '#ffffff'
```

### Description

The property output custom html row on the page type in WordPress admin.

### Settings

Key  | Default      | Description
-----|--------------|----------------------------------------------------------
html | empty string | String with html or a callable function or method.

## Image

**type** `image`

```php
<?php

/**
 * Example of image.
 */

papi_property([
  'title' => 'Image',
  'slug'  => 'my_image_slug',
  'type'  => 'image'
])

/**
 * Example output.
 */

stdClass Object
(
      [width] => 800
      [height] => 600
      [file] => '2014/09/cube.jpg'
      [sizes] => Array
        (
          [thumbnail] => Array
          (
            [file] => 'cube-150x150.jpg'
            [width] => 150
            [height] => 150
            [mime-type] => 'image/jpeg'
          )

          [medium] => Array
          (
            [file] => 'cube-300x225.jpg'
            [width] => 300
            [height] => 225
            [mime-type] => 'image/jpeg'
          )

      )

      [image_meta] => Array
        (
          [aperture] => 0
          [credit] =>
          [camera] =>
          [caption] =>
          [created_timestamp] => 0
          [copyright] =>
          [focal_length] => 0
          [iso] => 0
          [shutter_speed] => 0
          [title] =>
          [orientation] => 1
        )
      [alt] => 'Alt text'
      [caption] => 'Caption text'
      [description] => 'Description text'
      [id] => 6
      [is_image] => 1
      [title] => 'Title text'
      [url] => 'http://site.com/wp-content/uploads/2014/09/cube.jpg'
)
```

![Image example](/images/docs/property-image.png)

### Description

With this property you can add a image from the WordPress media library. If the gallery setting is set to true the output will be a array with objects instead of just one object.

### Settings

Key  | Default      | Description
-----|--------------|----------------------------------------------------------
html | empty string | String with html or a callable function or method.

## Number

**type** `number`

```php
<?php

/**
 * Example of number.
 */

papi_property([
  'title' => 'Number',
  'slug'  => 'my_number_slug',
  'type'  => 'number'
])

/**
 * Example output.
 */

int 10
```

### Description

The number property is the HTML5 number input field. No custom validation exists only the browsers validation will kick in. The value is saved as a string and the output is a string.

### Settings

No settings exists.

## Post

**type** `post`

```php
<?php

/**
 * Example of post.
 */

papi_property([
  'title'    => 'Post',
  'slug'     => 'my_post_slug',
  'type'     => 'post'
])

/**
 * Example output.
 */

WP_Post Object
(
  [ID] => 203
  [post_author] => 1
  [post_date] => 2014-11-18 22:07:38
  [post_date_gmt] => 2014-11-18 22:07:38
  [post_content] =>
  [post_title] => 'The post title'
  [post_excerpt] =>
  [post_status] => publish
  [comment_status] => closed
  [ping_status] => closed
  [post_password] =>
  [post_name] => 'the_post_title'
  [to_ping] =>
  [pinged] =>
  [post_modified] => 2014-11-18 22:09:05
  [post_modified_gmt] => 2014-11-18 22:09:05
  [post_content_filtered] =>
  [post_parent] => 0
  [guid] => 'http://site.com/?page_id=203'
  [menu_order] => 0
  [post_type] => 'page'
  [post_mime_type] =>
  [comment_count] => 0
  [filter] => 'raw'
)
```

### Description

With this property you can add reference to another post. It can't handle multiple references like [relationship](#relationship)

Since version 1.2.0 the post property by default include a blank row in the dropdown, this can be disabled by `include_blank`

### Settings

Key           | Default       | Description
--------------|---------------|--------------------------------------------------
blank_text    | empty string  | Change the blank text to something else
include_blank | true          | Include the blank row or not
post_type     | 'post'        | The post type that the property will load posts from. Can only be one post type
query         | array()       | Append a `WP_Query` on all post types. Gist reference over `WP_Query`. Note that `post_type` in query will always be removed
text          | 'Select Post' | The text above the dropdown. If this text is a empty string the p tag will be hidden

## Radio buttons

**type** `radio`

```php
<?php

/**
 * Example of radio buttons.
 */

papi_property([
  'title'    => 'Colors',
  'slug'     => 'my_radio_slug',
  'type'     => 'radio',
  'settings' => [
      'items' => [
        'White' => '#ffffff',
        'Black' => '#000000'
      ]
  ]
])

/**
 * Example output.
 */

string '#ffffff'
```

### Description

With this property you can create a list of radio buttons. The key is the value that the user will se in the WordPress admin and the value is the value saved in the database.

### Settings

Key      | Default      | Description
---------|--------------|-------------------------------------------------------
items    | array()      | Array with radio buttons, value or key/value
selected | empty string | The radio button that will be selected from start. The value should match a key of your items

## Reference

**type** `reference`

**since** `1.2.0`

```php
<?php

/**
 * Example of reference.
 */

papi_property([
  'title'    => 'References',
  'type'     => 'reference',
  'settings' => [
    'slug'      => 'top_module',
    'page_type' => 'start-page-type'
  ]
])

/**
 * Example output:
 * The reference property does not save any values.
 */
```

### Description

When using Post or Relationship property to load modules or something like that.
You may what to check which pages are loading the module. This is where the reference property comes in hand,
it will show which pages that has a reference to the module.

![Reference example](/images/docs/property-reference.png)

### Settings

Key       | Default      | Description
----------|--------------|-------------------------------------------------------
slug      | array()      | String or array of slugs to look for references
page_type | empty string | String or array of page types (the file name of the page type) to check

## Relationship

**type** `relationship`

```php
<?php

/**
 * Example of relationship.
 */

papi_property([
  'title'    => 'Relationship',
  'slug'     => 'my_relationship_slug',
  'type'     => 'relationship',
  'settings' => [
    'choose_max' => 3,
    'post_type'  => ['post', 'pages', 'my-custom-post-type']
  ]
])

/**
 * Example output:
 */

Array
(
  [0] => WP_Post Object
  (
    [ID] => 203
    [post_author] => 1
    [post_date] => 2014-11-18 22:07:38
    [post_date_gmt] => 2014-11-18 22:07:38
    [post_content] =>
    [post_title] => 'The post title'
    [post_excerpt] =>
    [post_status] => 'publish'
    [comment_status] => 'closed'
    [ping_status] => 'closed'
    [post_password] =>
    [post_name] => 'the_post_title'
    [to_ping] =>
    [pinged] =>
    [post_modified] => 2014-11-18 22:09:05
    [post_modified_gmt] => 2014-11-18 22:09:05
    [post_content_filtered] =>
    [post_parent] => 0
    [guid] => 'http://site.com/?page_id=203'
    [menu_order] => 0
    [post_type] => 'page'
    [post_mime_type] =>
    [comment_count] => 0
    [filter] => 'raw'
  )
)
```

### Description

With this property you can link posts, pages or custom post types together. With the `post_type` setting you can diced witch post types to use, default is page.

![Relationship example](/images/docs/property-relationship.png)

### Settings

Key          | Default       | Description
-------------|---------------|--------------------------------------------------
choose_max   | -1 (no limit) | Prevent how many post references that can be added
post_type    | 'page'        | Change which post types it loads post objects from
query        | array()       | Append a `WP_Query` on all post types. Gist reference over `WP_Query`. Note that `post_type` in query will always be removed
show_sort_by | true          | Show the sort by dropdown or not.

### Filters

```php
<?php

/**
 * Example of `papi/property/relationship/sort_options` filter.
 */

add_filter('papi/property/relationship/sort_options', function ($not_allowed) {
  return array_merge($not_allowed, [
    'Name (alphabetically)' => function ($a, $b) {
      return strcmp(strtolower($a->post_title), strtolower($b->post_title));
    }
  ]);
});
```

Filter                                  | Description
----------------------------------------|-------------
papi/property/relationship/sort_options | Add more sort options to property relationship. The array key is the name and the value that is saved as the sort order identification

## Repeater

**type** `repeater`

```php
<?php

/**
 * Example of repeater.
 */

papi_property([
  'title'    => 'Repeater',
  'slug'     => 'my_repeater_slug',
  'type'     => 'Repeater',
  'settings' => [
    'items' => [
      [
        'type'  => 'string',
        'title' => 'Title',
        'slug'  => 'my_string_slug'
      ],
      [
        'type'     => 'dropdown',
        'title'    => 'Color',
        'slug'     => 'my_dropdown_slug',
        'settings' => [
          'items' => [
            'White' => '#ffffff',
            'Black' => '#000000'
          ]
        ]
      ]
    ]
  ]
])

/**
 * Example output:
 */

Array
(
  [0] => Array
  (
    [my_string_slug] => 'Test 1'
    [my_dropdown_slug] => '#ffffff'
  )

  [1] => Array
  (
    [my_string_slug] => 'Test 2'
    [my_dropdown_slug] => '#000000'
  )
)
```

### Description

The repeater property can create a repeater of sub fields which can be repeated again and again.

![Repeater example](/images/docs/property-repeater.png)

### Settings

Key   | Default | Description
------|---------|----------------------------------------------------------
items | array() | The array of properties, the same key/values as the `$this->property` method or `papi_property` function has. You can't use property repeater inside a repeater.

### Filters

```php
<?php

/**
 * Example of `papi/property/repeater/exclude` filter.
 */

add_filter('papi/property/repeater/exclude', function ($exclude) {
  return array_merge($exclude, [
    'string'
  ]);
});
```

Filter                         | Description
-------------------------------|-------------
papi/property/repeater/exclude | Prevent properties from render and working in repeater

## String

**type** `string`

```php
<?php

/**
 * Example of string.
 */

papi_property([
  'title' => 'Name',
  'slug'  => 'my_name_slug',
  'type'  => 'string'
])

/**
 * Example output.
 */

string 'Fredrik'
```

### Description

The string property is just a text input field. The value is saved as a string and the output is a string.

### Settings

No settings exists.

## Text

**type** `text`

```php
<?php

/**
 * Example of text.
 */

papi_property([
  'title' => 'Text',
  'slug'  => 'my_text_slug',
  'type'  => 'text'
])

/**
 * Example output.
 */

string 'Fredrik'
```

### Description

This property will output the textarea tag and the output will be a string with all text from the textarea.

### Settings

No settings exists.

## Url

**type** `url`

```php
<?php

/**
 * Example of url.
 */

papi_property([
  'title'    => 'Url with button',
  'slug'     => 'my_url_slug',
  'type'     => 'url',
  'settings' => [
    'mediauploader' => true
  ]
])

/**
 * Example output.
 */

string 'http://site.com/wp-content/uploads/2014/11/image.png'
```

### Description

This property will output the textarea tag and the output will be a string with all text from the textarea.

![Url example](/images/docs/property-url.png)

### Settings

Key           | Default | Description
--------------|---------|------------
mediauploader | false   | When this is `true` a button will show next to the input field where you can open the WordPress media library
