Html
============

.. attribute:: type: html

The property output custom html row on the page type in WordPress admin.

Settings
-----------

.. attribute:: html

  String with html or a callable function or method.
  
  Default value is **empty string**.

Example
-----------

.. code-block:: php

  <?php

  $this->property([
      'title'    => 'Information',
      'type'     => 'html',
      'settings' => [
        'html' => '<p>Hello, world</p>'
      ]
  ])

Example output
-----------

The reference property does not save any values.
