Date
============

.. attribute:: type: date

The date property has a picker build in using `Pikaday <http://dbushell.github.io/Pikaday/>`_. The format is YYYY-MM-DD in WordPress admin, this can’t be change for now.

The output will be converted to time using `strtotime <http://php.net/manual/en/function.strtotime.php>`_.

Settings
-----------

No settings exists.

Example
-----------

.. code-block:: php

  <?php

  $this->property([
      'title'    => 'Date',
      'slug'     => 'my_date_slug',
      'type'     => 'date'
  ])

Example output
-----------

.. code-block:: php

  int 1396562400