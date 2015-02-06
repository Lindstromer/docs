Color
============

.. attribute:: type: color

The property output the WordPress color picker.

Settings
-----------

.. attribute:: palettes

  Array with hex colors

  Default value is **empty array**.

Example
-----------

.. code-block:: php

  <?php

  $this->property([
      'title'    => 'Background color',
      'slug'     => 'my_color_slug',
      'type'     => 'color'
  ])

Example output
-----------

.. code-block:: php

  string '#ffffff'
