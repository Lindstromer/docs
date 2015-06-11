# Page type

```php
<?php

/**
 * Example of a page type with no properties.
 */

class Video_Page_Type extends Papi_Page_Type {

  /**
   * The page type meta options.
   *
   * @return array
   */

  public function page_type () {
    return [
      'name'        => 'Video page',
      'description' => 'A page where you can embed videos',
      'template'    => 'pages/video-page.php'
    ];
  }

}
```

## Namespaces

```php
<?php

namespace Foo\Bar;

class Test_Page_Type extends \Papi_Page_Type {}
```

## Methods

### page_type method

The `page_type()` is a required method of the page type class. It should return an array containing the required keys.

Options     | Required | Description
------------|----------|------------
name        | yes      | The name of the page type
description | no       | The description of the page type
fill_labels | no       | When this is true it will add the page type name to `add_new_item`, `edit_item` and `view_item` label. Both in WordPress admin and the admin bar on the front. You can override this with the `labels` array.
labels      | no       | With this you can handle the `labels` object that exists on a [post type](http://codex.wordpress.org/Function_Reference/get_post_type_object). So this means that you can change "Add New Page" for every page type and have something like "Add New Startpage". Just create a array with the `labels` keys and values on your page type meta array
post_type   | no       | Array of post types that the page type should be registered on. Default is `page`
sort_order  | no       | The sort order number of the page type
template    | no       | The template file to render
thumbnail   | no       | The thumbnail image that should apper on the add new page

```javascript
/**
 * Example of template structure.
 */

themes/
  my-theme/
    pages/
      about-page.php
      contact-page.php
      video-page.php
```

When you using `template` key you can get a better structure of all pages type you are using and which template file it used.

When creating a new page you will get a new view before you get the edit view for your page where you should choose which page type to use. This will happen for all post types that uses page types.

### box method

This method is used to register all properties, tabs and remove meta boxes as described above.

The box method can has callable method as the second argument that returns a array with properties or tabs.

Read more about that under [box section](#box).

### display method

```php

/**
 * Example of `display` method.
 */

public function display($post_type) {
  if ($post_type === 'post') {
    return true;
  }

  return false;
}
```

This method is use to tell if the page type should be display or not on `Add new page type` page.

The method will take a `$post_type` argument. This is useful when the page type is register one more then one post type.

Returning anything else then true will hide the page type.

Default value is `true`.

### remove method

```php
<?php

public function register() {

  // A single metabox
  $this->remove( 'comments' );

  // Multiple metaboxes
  $this->remove( array( 'comments', 'editor' ) );

}
```

It's easy to remove metaboxes with the `remove` method.
You can remove both post type support and meta boxes with `remove.`

Check out [remove_post_type_support](http://codex.wordpress.org/Function_Reference/remove_post_type_support#Parameters) for right post type support or [remove_meta_box](https://codex.wordpress.org/Function_Reference/remove_meta_box#Parameters) for meta box slugs.
