Getting started
============

To start using Papi the easiest way is to download the plugin from `Github <http://github.com/wp-papi/papi>`_.

Register page type directory
-----------

To create a page type you need to register a filter that returns a string or array of strings with directories with page type files in.

Example:

.. code-block:: php

  <?php
  function _site_papi_page_type_directories () {
  	return dirname( __FILE__ ) . '/data/page-types';
  }
	
  add_filter('papi_page_type_directories', '_site_papi_page_type_directories');
