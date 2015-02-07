Post
============

.. attribute:: type: post

With this property you can add reference to another post. It can't handle multiple references like `relationship property <relationship.html>`_

Since version 1.2.0 the post property by default include a blank row in the dropdown, this can be disabled by "include_blank"

Settings
-----------

.. attribute:: include_blank

  Include the blank row or not.

  Default value is **true**.

.. attribute:: post_type

  The post type that the property will load posts from. Can only be one post type.

  Default value is **post** post type.

.. attribute:: query

  Append a WP_Query on all post types. Gist reference over WP_Query. Note that **post_type** in query will always be removed.

  Default value is **empty array**.

.. attribute:: text

  The text above the dropdown. If this text is a empty string the p tag will be hidden.

  Default value is **Select post** when you have english activated.

Example
-----------

.. code-block:: php

  <?php

  $this->property([
      'title'    => 'Post',
      'slug'     => 'my_post_slug',
      'type'     => 'post'
  ])

Example output
-----------

.. code-block:: php

  WP_Post Object
  (
      [ID] => 203
      [post_author] => 1
      [post_date] => 2014-11-18 22:07:38
      [post_date_gmt] => 2014-11-18 22:07:38
      [post_content] =>
      [post_title] => The post title
      [post_excerpt] =>
      [post_status] => publish
      [comment_status] => closed
      [ping_status] => closed
      [post_password] =>
      [post_name] => the_post_title
      [to_ping] =>
      [pinged] =>
      [post_modified] => 2014-11-18 22:09:05
      [post_modified_gmt] => 2014-11-18 22:09:05
      [post_content_filtered] =>
      [post_parent] => 0
      [guid] => http://site.com/?page_id=203
      [menu_order] => 0
      [post_type] => page
      [post_mime_type] =>
      [comment_count] => 0
      [filter] => raw
  )
