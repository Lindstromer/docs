Actions
============

Include custom properties
-----------

.. attribute:: action: papi/include_properties

With this action you can include your own properties. Third party properties should use this action when they load there custom property in the plugin.

Example:

.. code-block:: php

  <?php

  function include_property_kvack() {
    include_once('class-papi-property-kvack.php');
  }

  add_action('papi/include_properties', 'include_property_kvack');
