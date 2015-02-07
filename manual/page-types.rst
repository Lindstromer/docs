Page types
============

Page type meta options
----------------------

The `page_type()` is a required method of the page type class. It should return an array containing the required keys:

.. attribute:: name

    The name of the page type

**Additional keys are:**

.. attribute:: description

    The description of the page type

.. attribute:: labels

    Since version 1.2.0 all post type can handle the **labels** object that exists on a `post type <http://codex.wordpress.org/Function_Reference/get_post_type_object>`_.

    So this means that you can change "Add New Page" for every page type and have something like "Add New Startpage".

    Just create a array with the **lables** keys and values on your page type meta array.

.. attribute:: post_type

    Array of post types that the page type should be registered on. Default is `page`.

.. attribute:: sort_order

    The sort order number of the page type.

.. attribute:: template

    The template file to render

.. attribute:: thumbnail

    The thumbnail image that should apper on the add new page.

Example:

.. code-block:: php

  <?php

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

When you using `template` key you can get a better structure of all pages type you are using and which template file it used.

For example

.. code-block:: php

  themes/
    my-theme/
      pages/
        about-page.php
        contact-page.php
        video-page.php

When creating a new page you will get a new view before you get the edit view for your page where you should choose which page type to use. This will happen for all post types that uses page types.

.. image:: /_static/papi/add-new-page-type.png


Remove meta box
---------
It's easy to remove metaboxes with the `remove` method. Check the `WordPress Codex <http://codex.wordpress.org/Function_Reference/remove_meta_box#Parameters>`_ for right metabox slug.

.. code-block:: php

    <?php

    public function register() {

        // A single metabox
        $this->remove( 'comments' );

        // Multiple metaboxes
        $this->remove( array( 'comments', 'editor' ) );

    }

The register method
-------------------

This method is used to register all properties, tabs and remove meta boxes as described above.

Since version 1.2.0 the box method can has callable method as the second argument so you can output custom html between your properties.

Read more about that under `box method <box.html>`_ page.

Templates
---------

Papi has build in template support, which means that you can write your properties, tabs or boxes in seperated files. When loading them you can override the values with a array.

You can more about this functions under `API <api.html>`_ page.

Example $this->box

.. code-block:: php

  <?php

  // my-page-type.php
  $this->box('boxes/custom-meta-box.php');

  // boxes/custom-meta-box.php
  return [
    'title' => 'My meta box',
    papi_property([
      'type'     => 'dropdown',
      'title'    => 'Dropdown',
      'slug'     => 'my_dropdown',
      'settings' => [
        'items' => [
          'White' => '#ffffff',
          'Black' => '#000000'
        ]
      ]
    ])
  ];

Example $this->property or papi_property

.. code-block:: php

  <?php

  // my-page-type.php
  $this->box('My meta box', [
    $this->property('properties/dropdown.php')
  ]);

  // properties/dropdown.php
  return papi_property([
    'type'     => 'dropdown',
    'title'    => 'Dropdown',
    'slug'     => 'my_dropdown',
    'settings' => papi_template('settings/dropdown.php')
  ]);

Example $this->tab or papi_tab

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

Example papi_template

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
