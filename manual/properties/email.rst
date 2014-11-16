Email
============

.. attribute:: type: email

The email property is the HTML5 email input field. No custom validation exists only the browsers validation will kick in. The value is saved as a string and the output is a string.

Settings
-----------

No settings exists.

Example
-----------

.. code-block:: php

  <?php

  $this->property([
      'title'    => 'Email',
      'slug'     => 'my_email_slug',
      'type'     => 'email'
  ])

Example output
-----------

.. code-block:: php

  string 'hello@world.com'