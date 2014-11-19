Url
============

.. attribute:: type: url

The number property is the HTML5 url input field. No custom validation exists only the browsers validation will kick in. The value is saved as a string and the output is a string.

Settings
-----------

.. attribute:: mediauploader

  When this is true a button will show next to the input field where you can open the WordPress media library.

  Default value is **false**.

Example
-----------

.. code-block:: php

  <?php

  $this->property([
      'title'    => 'Url with button',
      'slug'     => 'my_url_slug',
      'type'     => 'url',
      'settings' => [
          'mediauploader' => true
      ]
  ])

.. image:: /_static/papi/property-url.png

Example output
-----------

.. code-block:: php

  string 'http://site.com/wp-content/uploads/2014/11/image.png'