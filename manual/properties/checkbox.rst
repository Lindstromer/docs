Checkbox
============

.. attribute:: type: checkbox

With this property you can add multiple checkboxes. The key is the value that the user will se in the WordPress admin and the value is the value saved in the database.

Settings
-----------

.. attribute:: items

  The array with checkboxes items, value or key/value.

.. attribute:: selected

  The selected key or array of keys

Example
-----------

.. code-block:: php

  <?php

  $this->property([
      'title'    => 'Categories',
      'slug'     => 'my_categories_slug',
      'type'     => 'checkbox',
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

  Array
  (
    [0] => '#ffffff'
  )