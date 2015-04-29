# Checkbox

**type** `checkbox`

## Description

With this property you can add multiple checkboxes. The key is the value that the user will se in the WordPress admin and the value is the value saved in the database.

## Settings

##### items

The array with checkboxes items, value or key/value.

Default value is `empty array`.

##### selected

The selected key or array of keys

Default value is `empty array`.

## Example

```php
papi_property([
  'title'    => 'Categories',
  'slug'     => 'my_categories_slug',
  'type'     => 'checkbox',
  'settings' => [
    'items' => [
      'White' => '#ffffff',
      'Black' => '#000000'
    ]
  ]
])
```

## Example output

```php
Array
(
  [0] => '#ffffff'
)
```
