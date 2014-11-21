Datetime
============

.. attribute:: type: datetime

The date property has a picker build in using `Pikaday <https://github.com/owenmead/Pikaday>`_ with time support.

Settings
-----------

.. attribute:: format

The format of the date. Look at `moment.js <http://momentjs.com/>`_ formats.

Default value is **YYYY-MM-DD hh:mm:ss**.

.. attribute:: show_seconds

Show the sconds dropdown or not.

Default value is **false**.

.. attribute:: show_time

Show the hour and minute dropdown or not.

Default value is **true**.

.. attribute:: use_24_hours

Use 24 hours instead of PM/AM.

Default value is **false**.

Example
-----------

.. code-block:: php

  <?php

  $this->property([
      'title'    => 'Datetime',
      'slug'     => 'my_date_slug',
      'type'     => 'datetime'
  ])

Example output
-----------

.. code-block:: php

  string '2014-11-21'
