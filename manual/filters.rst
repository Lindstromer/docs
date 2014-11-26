Filters
============

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
