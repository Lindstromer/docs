Getting started
============

To start using Papi the easiest way is to download the plugin from `Github <http://github.com/wp-papi/papi>`_.

Register page type directory
-----------

To create a page type you need to register a page type directory with Papi using `register_page_types_directory` function.

Example:

.. code-block:: php

  <?php

  // In your functions file
  register_page_types_directory('path/to/page-types');

  // If you do this is mu-plugins directory or outside your theme.
  function my_register_page_types_directory () {
    register_page_types_directory('path/to/page-types');
  }
  add_action('after_setup_theme', 'my_register_page_types_directory');