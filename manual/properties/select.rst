Select
============

.. attribute:: type: select

With this property you can add a select/dropdown input. The key is the value that the user will se in the WordPress admin and the value is the value saved in the database.

Settings
-----------

.. attribute:: items

  The array with checkboxes items, value or key/value.

  Default value is **empty array**.

.. attribute:: selected

  The dropdown item that will be selected from start. The value should match a key of your items.

  Default value is **empty string**.

Example
-----------

.. code-block:: php

  <?php

  $this->property([
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

Example output
-----------

.. code-block:: php

  string '#ffffff'