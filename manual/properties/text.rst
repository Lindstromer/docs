Text/WordPress editor
============

.. attribute:: type: text

This property will output the textarea tag and the output will be a string with all text from the textarea.

Settings
-----------

.. attribute:: editor

  When this is true the **wp_editor** will be showed.

  Default value is **false**.

Example
-----------

.. code-block:: php

  <?php

  $this->property([
      'title'    => 'Text',
      'slug'     => 'my_text_slug',
      'type'     => 'text'
  ])

Example output
-----------

.. code-block:: php

  string 'Fredrik'