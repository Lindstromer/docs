Box method
============

Documentation of the `box` method. `box` is a short name for `metabox` in Papi.

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

  The title of the meta box. This can't be empty, seamless mode will not show the title.

  When passing a string as the first argument for box method it will become `array('title' => 'the title')` automatic.

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

**Callable method**

Since version 1.2.0 it's possible to use callable method as a second argument in your box method.

The important part is to use the render method (can take a property, tab or array of properties or tabs) so the properties are rendered.

But that isn't all the callable method can do, you can print your own html between the properties.

You should wrap your custom html in a div with the class "papi-custom-html" to get it look nice.

**Note about custom html and tabs**

Custom html with tabs will not look nice since tabs and properties can't be one the same row.

When using tabs in your box you should only have tabs with properties inside not tabs after or before properties.

**tab

.. image:: /_static/papi/custom-html-between-properties.png

Example:

.. code-block:: php

  <?php

  public function register() {
    $this->box('Content', array($this, 'content_box'));
  }

  public function content_box() {
    $this->render($this->property([
      'type'  => 'string',
      'title' => 'Name'
    ]));

    // Example of custom html between properties

    $this->render([
      $this->property([
        'type'  => 'string',
        'title' => 'Name'
      ]),
      $this->property([
        'type'  => 'email',
        'title' => 'Email'
      ])
    ));

    ?>
      <div class="papi-custom-html">
        <h3>Information</h3>
        <p>Custom text about the property or something</p>
      </div>
    <?php

    $this->render($this->property([
      'type'  => 'relationship',
      'title' => 'Modules'
    ]));
  }
