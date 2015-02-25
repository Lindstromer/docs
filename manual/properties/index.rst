Properties
============

Papi does support 20 core properties (a field is a property in the page type) to start with and you can easy create your own using our Yeoman generator. The are several keys that all properties have:

.. attribute:: capabilities

  Can be a string with a role or capability or a array with many values.

.. attribute:: default

  The default value that are presented in the property.

.. attribute:: disabled

  Disable the property, won’t show in WordPress admin.

.. attribute:: description

  The introduction text that will appear below the title text of the property. You could write your help text here.
  
  Since version 1.2.0 you can have "\n" to create new lines in the description.

.. attribute:: lang

  When using this key you can specify which language will show the property.

  Since version 1.2.0 the default value is **false** so the language load feature can be turned off.

.. attribute:: raw

  This will render the property without a table, good to use when creating a custom property that uses other properties.

.. attribute:: required

  By default all fields are non required in Papi but this can be changed with required option.

.. attribute:: sidebar

  Boolean that shows the sidebar on each property. If false the sidebar won’t show. Default is true.

.. attribute:: settings

  Array with custom settings for the property.

.. attribute:: sort_order

  Numeric value, lowest value in the meta box will be at the top and the highest value at the bottom.

.. attribute:: slug

  The slug of property. If empty or not used the title will be generated to slug value.

.. attribute:: title

  The title of the property. Can be empty for blank title.

.. attribute:: type

  The property type (lower case is preferred to use)

**Example of the default options:**

.. code-block:: php

  <?php

  papi_property([
    'capabilities' => array(),
    'default'      => '',
    'description'  => '',
    'disabled'     => false,
    'lang'         => false,
    'raw'          => false,
    'settings'     => array(),
    'sidebar'      => true,
    'slug'         => '',
    'sort_order'   => 100,
    'required'     => false,
    'title'        => '',
    'type'         => ''
  ]);

**Note:** be sure to have different slug for each properties on a page type, the same slug will not work great and you will lose data if you are using same slug for multiple properties.

**The list of properties that Papi supports in the core are:**

.. toctree::
  :maxdepth: 1

  bool
  checkbox
  color
  datetime
  divider
  email
  image
  number
  post
  radio-buttons
  reference
  repeater
  relationship
  select
  string
  text
  url
