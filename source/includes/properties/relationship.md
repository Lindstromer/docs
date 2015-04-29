# Relationship

**type** `relationship`

## Description

With this property you can link posts, pages or custom post types together. With the `post_type` setting you can diced witch post types to use, default is page.

## Settings

##### choose_max

Prevent how many post references that can be added.

Default value is `-1` (no limit).

##### post_type

Change which post types it loads post objects from.

Default value is `page`.

##### query

Append a WP_Query on all post types. Gist reference over WP_Query. Note that `post_type` in query will always be removed.

Default value is `empty array`.

##### show_sort_by

Show the sort by dropdown or not.

Default value is `true`.

## Filters

**tag** `papi/property/relationship/sort_options`

Add more sort options to property relationship. The array key is the name and the value that is saved as the sort order identification. All sort order functions is

```php
add_filter('papi_property_relationship_sort_options', function ($not_allowed) {
  return array_merge($not_allowed, [
    'Name (alphabetically)' => function ($a, $b) {
      return strcmp(strtolower($a->post_title), strtolower($b->post_title));
    }
  ]);
});
```

## Example

```php
papi_property([
  'title'    => 'Relationship',
  'slug'     => 'my_relationship_slug',
  'type'     => 'relationship',
  'settings' => [
    'choose_max' => 3,
    'post_type'  => ['post', 'pages', 'my-custom-post-type']
  ]
])
```

![Property Relationship](/assets/images/docs/property-relationship.png)

## Example output

```php
Array
(
  [0] => WP_Post Object
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
)
```
