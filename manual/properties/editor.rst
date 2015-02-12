Editor
============

.. attribute:: type: Editor

.. attribute:: since version: 1.2.0

This property is a shortcut property that extends property text and changes the default value of "editor" to "true".

Settings
-----------

No settings exists.

Example
-----------

.. code-block:: php

  <?php

  $this->property([
      'title' => 'Editor',
      'slug'  => 'my_editor_slug',
      'type'  => 'editor'
  ])

Output
-----------

String of text.
