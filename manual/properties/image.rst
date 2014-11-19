Image/Gallery
============

.. attribute:: type: image

With this property you can add a image from the WordPress media library. If the gallery setting is set to true the output will be a array with objects instead of just one object.

Settings
-----------

.. attribute:: gallery

  When this is true you can add as many images you like.

  Default value is **false**.

Example
-----------

.. code-block:: php

  <?php

  $this->property([
      'title' => 'Image',
      'slug'  => 'my_image_slug',
      'type'  => 'image'
  ])

.. image:: /_static/papi/property-image.png

Example output
-----------

.. code-block:: php

  stdClass Object
  (
          [width] => 800
          [height] => 600
          [file] => 2014/09/cube.jpg
          [sizes] => Array
                  (
                          [thumbnail] => Array
                                  (
                                          [file] => cube-150x150.jpg
                                          [width] => 150
                                          [height] => 150
                                          [mime-type] => image/jpeg
                                  )

                          [medium] => Array
                                  (
                                          [file] => cube-300x225.jpg
                                          [width] => 300
                                          [height] => 225
                                          [mime-type] => image/jpeg
                                  )

                  )

          [image_meta] => Array
                  (
                          [aperture] => 0
                          [credit] =>
                          [camera] =>
                          [caption] =>
                          [created_timestamp] => 0
                          [copyright] =>
                          [focal_length] => 0
                          [iso] => 0
                          [shutter_speed] => 0
                          [title] =>
                          [orientation] => 1
                  )

          [is_image] => 1
          [url] => http://site.com/wp-content/uploads/2014/09/cube.jpg
          [id] => 6
  )