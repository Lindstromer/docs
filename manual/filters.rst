Filters
============

Property: Format value
----------------------

.. attribute:: tag: papi/format_value/{$property_type}

Format the value of the property before we output it to the application.

Example:

.. code-block:: php

  <?php

  function format_value_string( $value, $slug, $post_id ) {
    // do some magic with the value and return it.
    return $value;
  }

  add_filter('papi/format_value/string', 'format_value_string');

Property: Load value
--------------------

.. attribute:: tag: papi/load_value/{$property_type}

This filter is applied after the $value is loaded in the database.

Example:

.. code-block:: php

  <?php

  function load_value_string( $value, $slug, $post_id ) {
    // do some magic with the value and return it.
    return $value;
  }

  add_filter('papi/load_value/string', 'load_value_string');

Property: Update value
----------------------

.. attribute:: tag: papi/update_value/{$property_type}

This filter is applied before the $value is saved in the database.

Example:

.. code-block:: php

  <?php

  function update_value_string( $value, $slug, $post_id ) {
    // do some magic with the value and return it.
    return $value;
  }

  add_filter('papi/load_value/string', 'update_value_string');

Setting: Change default sort order
----------------------------------

.. attribute:: tag: papi/settings/sort_order

Change the default sort order for page types, meta boxes, tabs and properties.

Default sort order is **1000**.

Example:

.. code-block:: php

  <?php

  function change_default_sort_order() {
    return 1;
  }

  add_filter('papi/settings/sort_order', 'change_default_sort_order');

Setting: Only page type for post type
-------------------------------------

.. attribute:: tag: papi/settings/only_page_type_{$post_type}

With this filter you can change the add new link for a post type to go direct to a single page type and jump over the "add new page type" view.

The value you should return is the file name of your page type without `.php`.

Default value is **empty string**.

Example:

.. code-block:: php

  <?php

  function only_page_type_post() {
    return 'video-page-type';
  }

  add_filter('papi/settings/only_page_type_post', 'only_page_type_post');

Setting: Page type directories
------------------------------

.. attribute:: tag: papi/settings/directories

This filter is used to register all page type directories that Papi should look for page types in.

You can return a string or a array of strings.

Default value is **empty array**.

Example:

.. code-block:: php

  <?php

  function page_type_directories() {
    return dirname(__FILE__) . '/page-types';
  }

  add_filter('papi/settings/directories', 'page_type_directories');

Setting: Load page type from post id query string
-------------------------------------------------

.. attribute:: tag: papi/settings/page_type_from_post_qs

.. attribute:: since version 1.2.0

This filter is used to load a page type from a query string that have another post id.

When using plugins as Polylang the query string "from_post" is used to tell which post the current post was created from.

Papi will not now which page type to load then and it should be the same as the "from_post". So that's when this filter will be useful.

This filter is not post type specific and will work on every post type.

Default value is **from_post**.

Example:

.. code-block:: php

  <?php

  function change_page_type_from_post_qs() {
    return 'parent_post';
  }

  add_filter('papi/settings/page_type_from_post_qs', 'change_page_type_from_post_qs');

Setting: Show page type on add new page type view
-------------------------------------------------

.. attribute:: tag: papi/settings/show_page_type_{$post_type}

.. attribute:: since version: 1.2.0

This filter is used to filter which page types that can be listed on the add new page type view.

The function will send in the file name of post types as a argument.

Returning false on a page type will hide the page type on the add new page type view.

Default value for every page type is **true**.

Example:

.. code-block:: php

  <?php

  function hide_start_page_type($page_type) {
    if ($page_type === 'start-page-type') {
      return false;
    }

    return true;
  }

  add_filter('papi/settings/show_page_type_page', 'hide_start_page_type');

Setting: Change standard page description for post type
-------------------------------------------------------

.. attribute:: tag: papi/settings/standard_page_description_{$post_type}

.. attribute:: since version: 1.2.0

This filter is used to change the standard page description for a post type.

Default value is the translation of **Just the normal WordPress page**.

Example:

.. code-block:: php

  <?php

  function change_standard_page_description() {
    return __('The standard blog post', 'my_theme');
  }

  add_filter('papi/settings/standard_page_description_post', 'change_standard_page_description');

Setting: Change standard page name for post type
-------------------------------------------------------

.. attribute:: tag: papi/settings/standard_page_name_{$post_type}

.. attribute:: since version: 1.2.0

This filter is used to change the standard page name for a post type.

Default value is the translation of **Standard Page**.

Example:

.. code-block:: php

  <?php

  function change_standard_page_name() {
    return __('Standard Post', 'my_theme');
  }

  add_filter('papi/settings/standard_page_name_post', 'change_standard_page_name');


Setting: Show standard page type for post type
----------------------------------------------

.. attribute:: tag: papi/settings/standard_page_type_{$post_type}

This filter allows you to hide the standard page on the "add new page type" view.

Default value for every post type is **true**.

Example:

.. code-block:: php

  <?php

  function show_standard_page_type_post() {
    return false;
  }

  add_filter('papi/settings/standard_page_type_post', 'show_standard_page_type_post');

Setting: Change standard page thumbnail for post type
-------------------------------------------------------

.. attribute:: tag: papi/settings/standard_page_thumbnail_{$post_type}

.. attribute:: since version: 1.2.0

This filter is used to change the standard page thumbnail for a post type.

Default value is the translation of **empty string**.

Example:

.. code-block:: php

  <?php

  function change_standard_page_thumbnail() {
    return '/path/to/thumbnail.png'
  }

  add_filter('papi/settings/standard_page_thumbnail_post', 'change_standard_page_thumbnail');
