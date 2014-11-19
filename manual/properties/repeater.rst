Repeater
============

.. attribute:: type: repeater

The repeater property can create a repeater of sub fields which can be repeated again and again.

Settings
-----------

.. attribute:: items

  The array of properties, the same key/values as the `$this->property` method has.

  Default value is **empty array**.

Example
-----------

.. code-block:: php

  <?php

  $this->property([
      'type'     => 'repeater',
      'title'    => 'Repeater',
      'slug'     => 'my_repeater_slug',
      'settings' => [
          'items' => [
              [
                  'type'  => 'string',
                  'title' => 'Title',
                  'slug'  => 'my_string_slug'
              ],
              [
                  'type'     => 'dropdown',
                  'title'    => 'Color',
                  'slug'     => 'my_dropdown_slug',
                  'settings' => [
                      'items' => [
                          'White' => '#ffffff',
                          'Black' => '#000000'
                      ]
                  ]
              ]
          ]
      ]
  ])

.. image:: /_static/papi/property-repeater.png

Example output
-----------

.. code-block:: php

  Array
  (
          [0] => Array
                  (
                          [my_string_slug] => "Test 1"
                          [my_dropdown_slug] => "#ffffff"
                  )

          [1] => Array
                  (
                          [my_string_slug] => "Test 2"
                          [my_dropdown_slug] => "#000000"
                  )

  )