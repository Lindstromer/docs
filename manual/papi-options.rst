Papi options
============

Papi have some global options that can changed using a filter.

The default values:

.. code-block:: php

  <?php

  $options = array(

    // Post types options

    /**
     * Show the standard page or not.
     * On post and page it's true by default
     *
     * Adding another post type is easy,
     * just copy page or post and replace the
     * page or post key with your post type name in lower cases.
     */

    'post_type.page.show_standard_page' => true,
    'post_type.post.show_standard_page' => true
  );


To change a option you change the values in the options array that are the argument of **papi/options** filter.

Example:

.. code-block:: php

  <?php

  function site_change_papi_options( $options ) {
    return array_merge($options, [
      'post_type.post.show_standard_page' => false
    ]);
  }

  add_filter('papi/options', 'site_change_papi_options');

There are some dynamic keys you can add to use only one page type with a post type and skip the "add new page type" view.

For example to skip the "add new page type" view with page and use "Video_Page_Type" page type you can add **post_type.%s.only_page_type** key, where **%s** is the file name of the page type file.

Code example:

.. code-block:: php

  <?php

  function site_change_papi_options( $options ) {
    return array_merge($options, [
      'post_type.page.only_page_type' => 'video-page-type.php'
    ]);
  }

  add_filter('papi/options', 'site_change_papi_options');
