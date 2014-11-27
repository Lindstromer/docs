Filters
============

Change default sort order
--------------------------

.. attribute:: tag: papi_default_sort_order

Change the default sort order for page types, meta boxes, tabs and properties.

Default sort order is **1000**.

Example:

.. code-block:: php

  <?php

  function change_default_sort_order() {
    return 1;
  }

  add_filter('papi_default_sort_order', 'change_default_sort_order');

Only page type for a post type
------------------------------

.. attribute:: tag: papi_only_page_type_for_$post_type

With this filter you can change the add new link for a post type to go direct to a single page type and jump over the "add new page type" view.

The value you should return is the file name of your page type without `.php`.

Default value is **empty string**.

Example:

.. code-block:: php

  <?php

  function only_page_type_for_post() {
    return 'video-page-type';
  }

  add_filter('papi_only_page_type_for_post', 'only_page_type_for_post');


Property: Format value
--------------------------

.. attribute:: tag: papi_format_value_$property_type

Format the value of the property before we output it to the application.

Example:

.. code-block:: php

  <?php

  function format_value_string( $value, $slug, $post_id ) {
    // do some magic with the value and return it.
    return $value;
  }

  add_filter('papi_format_value_string', 'format_value_string');

Property: Load value
--------------------------

.. attribute:: tag: papi_load_value_$property_type

This filter is applied after the $value is loaded in the database.

Example:

.. code-block:: php

  <?php

  function load_value_string( $value, $slug, $post_id ) {
    // do some magic with the value and return it.
    return $value;
  }

  add_filter('papi_load_value_string', 'load_value_string');

Property: Update value
--------------------------

.. attribute:: tag: papi_update_value_$property_type

This filter is applied before the $value is saved in the database.

Example:

.. code-block:: php

  <?php

  function update_value_string( $value, $slug, $post_id ) {
    // do some magic with the value and return it.
    return $value;
  }

  add_filter('papi_load_value_string', 'update_value_string');

Show standard page for post type
--------------------------------

.. attribute:: tag: papi_show_standard_page_for_$post_type

This filter allows you to hide the standard page on the "add new page type" view.

Default value for every post type is **true**.

Example:

.. code-block:: php

  <?php

  function show_standard_page_for_post() {
    return false;
  }

  add_filter('papi_show_standard_page_for_post', 'show_standard_page_for_post');

Page type directories
---------------------

.. attribute:: tag: papi_page_type_directories

This filter is used to register all page type directories that Papi should look for page types in.

You can return a string or a array of strings.

Default value is **empty array**.

Example:

.. code-block:: php

  <?php

  function page_type_directories() {
    return dirname(__FILE__) . '/page-types';
  }

  add_filter('papi_page_type_directories', 'page_type_directories');
