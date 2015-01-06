Box
============

.. attribute:: capabilities

  Can be a string with a role or capability or a array with many values.

  Default value is **empty array**.
  
.. attribute:: context

  The same value as for context in `add_meta_box`. 

  Default value is **normal**.

.. attribute:: mode

  `standard` or `seamless` (no metabox). 

  Default value is **standard**.

.. attribute:: post_type

  The post types where the box should be available. 

  Default value is **page**.

.. attribute:: priority

  The same value as for priority in `add_meta_box`. 

  Default value is **default**.

.. attribute:: sort_order

  Numeric value, lowest value in the meta box will be at the top and the highest value at the bottom.

  Default value is **1000**.

.. attribute:: title

  The title of the meta box. When passing a string as the first argument for box method it will become `array('title' => 'the title')` automatic.

  Default value is **empty string**.

 **Example of the default options:**

.. code-block:: php
  
  <?php
  
  $this->box([
    'capabilities' => array(),
    'context'      => 'normal',
    'mode'         => 'standard',
    'post_type'    => 'page',
    'priority'     => 'default',
    'sort_order'   => 1000,
    'title'        => ''
  ]);
