Filters
============

Property: Format value
--------------------------

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
--------------------------

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
--------------------------

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
--------------------------

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
------------------------------

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
---------------------

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

Setting: Show standard page for post type
--------------------------------

.. attribute:: tag: papi/settings/standard_page_{$post_type}

This filter allows you to hide the standard page on the "add new page type" view.

Default value for every post type is **true**.

Example:

.. code-block:: php

  <?php

  function show_standard_page_post() {
    return false;
  }

  add_filter('papi/settings/standard_page_post', 'show_standard_page_post');

