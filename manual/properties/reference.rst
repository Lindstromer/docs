Reference
============

.. attribute:: type: reference

When using Post or Relationship property to load modules or something like that.
You may what to check which pages are loading the module. This is where the reference property comes in hand,
it will show which pages that has a reference to the module.

Settings
-----------

.. attribute:: slug

  String or array of slugs to look for references.

  Default value is **empty array**.

.. attribute:: post_type

  String or array of post types to check.

  Default value is **"post"**.

.. attribute:: page_type

  String or array of page types (the file name of the page type) to check.

  Default value is **empty array**.

Example
-----------

.. code-block:: php

  <?php

  $this->property([
      'title'    => 'References',
      'type'     => 'reference',
      'settings' => [
        'slug'      => 'top_module',
        'post_type' => 'post',
        'page_type' => 'start-page-type'
      ]
  ])

.. image:: /_static/papi/property-reference.png

Example output
-----------

The reference property does not save any values.
