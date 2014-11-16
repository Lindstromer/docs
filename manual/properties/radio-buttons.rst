Radio buttons
============

.. attribute:: type: radio

With this property you can create a list of radio buttons. The key is the value that the user will se in the WordPress admin and the value is the value saved in the database.

Settings
-----------

.. attribute:: items

  The array with checkboxes items, value or key/value.

.. attribute:: selected

  The radio button that will be selected from start. The value should match a key of your items.

Example
-----------

.. code-block:: php

  <?php

  $this->property([
      'title'    => 'Colors',
      'slug'     => 'my_radio_slug',
      'type'     => 'radio',
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