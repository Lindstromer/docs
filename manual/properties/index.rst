Properties
============

Papi does support 17 core properties (a field is a property in the page type) to start with and you can easy create your own using our Yeoman generator. The are several keys that all properties have:

.. attribute:: capabilities

  Can be a string with a role or capability or a array with many values.

.. attribute:: capabilities

  Can be a string with a role or capability or a array with many values.

.. attribute:: default

  The default value that are presented in the property.

.. attribute:: disabled

  Disable the property, won’t show in WordPress admin.

.. attribute:: introduction

  The introduction text that will appear below the title text of the property. You could write your help text here.

.. attribute:: lang

  When using this key you can specify which language (2 letters language code) will show the property. Papi has build in support for Polylang and when you are using the query string lang.

.. attribute:: raw

  This will render the property without a table, good to use when creating a custom property that uses other properties.

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
    'lang'         => '',
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

The list of properties that Papi supports in the core are:
----------------------------------------------------------

.. toctree::
  :maxdepth: 1

  bool
  checkbox
  datetime
  divider
  email
  image
  number
  post
  radio-buttons
  repeater
  relationship
  select
  string
  text
  url
