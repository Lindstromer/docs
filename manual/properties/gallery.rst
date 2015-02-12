Gallery
============

.. attribute:: type: gallery

This property is a shortcut property that extends property image and changes the default value of "gallery" to "true".

Settings
-----------

No settings exists.

Example
-----------

.. code-block:: php

  <?php

  $this->property([
      'title' => 'Gallery',
      'slug'  => 'my_gallery_slug',
      'type'  => 'gallery'
  ])

Example output
-----------

A array of image objects as described in `property image <image.html>`_.
