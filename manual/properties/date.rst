Date
============

.. attribute:: type: date

The date property has a picker build in using `Pikaday <http://dbushell.github.io/Pikaday/>`_.

Settings
-----------

.. attribute:: format

The format of the date. Look at `moment.js <http://momentjs.com/>`_ formats.

Default format is **YYYY-MM-DD**.

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

  string '2014-11-21'
