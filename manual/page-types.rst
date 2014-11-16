Page types
============

Page type meta options
-----------

The `page_type()` is a required method of the page type class. It should return an array containing the required keys:

.. attribute:: name

    The name of the page type

**Additional keys are:**

.. attribute:: description

    The description of the page type

.. attribute:: post_types

    Array of post types that the page type should be registered on. Default is `page`.

.. attribute:: sort_order

    The sort order number of the page type. This required the Papi option ...

.. attribute:: template

    The template file to render

.. attribute:: thumbnail

    The thumbnail image that should apper on the add new page.

Example:

.. code-block:: php

  <?php

  public class Video_Page_Type extends Papi_Page_Type {

    /**
     * The page type meta options.
     *
     * @return array
     */

    public function page_type () {
      return [
        'name'        => 'Video page',
        'description' => 'A page where you can embed videos',
        'template'    => 'pages/video-page.php'
      ];
    }

  }

When you using `template` key you can get a better structure of all pages type you are using and which template file it used.

For example

.. code-block:: php

  themes/
    my-theme/
      pages/
        about-page.php
        contact-page.php
        video-page.php

When creating a new page you will get a new view before you get the edit view for your page where you should choose which page type to use. This will happen for all post types that uses page types.

.. image:: /_static/papi/add-new-page-type.png