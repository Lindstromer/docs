Filters
============

Property: Format value
--------------------------

.. attribute:: action: papi/format_value/$property_type

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

.. attribute:: action: papi/load_value/$property_type

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

.. attribute:: action: papi/update_value/$property_type

This filter is applied before the $value is saved in the database.

Example:

.. code-block:: php

  <?php

  function update_value_string( $value, $slug, $post_id ) {
    // do some magic with the value and return it.
    return $value;
  }

  add_filter('papi/load_value/string', 'update_value_string');
