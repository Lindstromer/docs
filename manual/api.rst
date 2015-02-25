API
===

There are some function that you can use in your page type.

current_page
------------

**Arguments**

No arguments exists.

**Description**

The current page function will return the Papi page with all fields.

.. code-block:: php

  <?php

  echo current_page()->twitter_url;

  // will be the same as

  echo papi_field('twitter_url');


papi_field
----------

**Arguments**

.. attribute:: $post_id = null (optional)

The post id will be added automatic if you are one a post, page or custom post type page.

When fetching values from another post this argument will be required.

.. attribute:: $slug

The property slug to fetch value from.

.. attribute:: $default = null (optional)

When a default value is passed as argument it will use that value as return value if the property value is empty or don't exists.

**Description**

This function will return the value of a property using the property slug.

.. code-block:: php

  <?php

  echo papi_field('twitter_url')

  // with post id

  echo papi_field(1, 'twitter_url')

  // with default value

  echo papi_field(1, 'twitter_url', 'http://twitter.com/frozzare');

papi_fields
-----------

**Arguments**

No arguments exists.

**Description**

This function will return a array with meta box title as keys and array of all Papi field slugs in that meta box.

.. code-block:: php

  <?php

  $output = array(
    'Content' => array(
      'top_module',
      'feature_module',
      'show_feature_module'
    )
  );

papi_get_page
---------

**Arguments**

.. attribute:: $post_id = null (optional)

**Description**

When given a post id it will fetch the Papi page for that post id instead.

The papi page function will do the same as current page function if no post id is used as a argument.

.. code-block:: php

  <?php

  echo papi_get_page()->twitter_url;

  // with post id

  echo papi_get_page(2)->twitter_url;


papi_property
-------------

**Arguments**

.. attribute:: $file_or_options

File path or a array containing property options

.. attribute:: $values = array() (optional)

The values to override the template values with.

**Description**

This argument is only used when you load a template file, the array will be used to override property options from the template file.

This function will be the same as **$this->property** method on a page type.

When using a shared property file or another file that the property are stored in you can used it as a template file.

This is great to use when you will share properties over many page types and it will be less code to write.

.. code-block:: php

  <?php

  // my-page-type.php
  $this->box('My meta box', [
    $this->property('properties/my-image.php', [
      'slug' => 'my_meta_box_image'
    ])
  ]);

  // properties/my-image.php
  return papi_property([
    'type'  => 'image',
    'title' => 'Image',
    'slug'  => 'custom_image_slug'
  ]);


papi_tab
-------------

**Arguments**

.. attribute:: $file_or_options

File path or a array containing tab options

.. attribute:: $properties

**Description**

This argument is only used when you load a template file, the array will be used to override tab options from the template file.

This function will be the same as **$this->tab** method on a page type.

When using a shared tab file or another file that the tab are stored in you can used it as a template file.

This is great to use when you will share tabs over many page types and it will be less code to write.

.. code-block:: php

  <?php

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


papi_template
-------------

**Arguments**

.. attribute:: $file_or_options

File path to template file.

.. attribute:: $values = array() (optional)

The values to override the template values with.

The

**Description**

`papi_property` function uses this function load template file. This function can be used to load template files that returns arrays. It can be handy when you will have to repeater or dropdown values in another file.

.. code-block:: php

  <?php

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



the_papi_field
--------------

**Arguments**

.. attribute:: $post_id = null (optional)

The post id will be added automatic if you are one a post, page or custom post type page.

When fetching values from another post this argument will be required.

.. attribute:: $slug

The property slug to fetch value from.

.. attribute:: $default = null (optional)

When a default value is passed as argument it will use that value as return value and echo it if the property value is empty or don't exists.

**Description**

This function will echo the value of a property using the property slug.

.. code-block:: php

  <?php

  the_papi_field('twitter_url')

  // with post id

  the_papi_field(1, 'twitter_url')

  // with default value

  the_papi_field(1, 'twitter_url', 'http://twitter.com/frozzare');
