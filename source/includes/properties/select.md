# Select

**type** `select`

## Description

With this property you can add a select/dropdown input. The key is the value that the user will se in the WordPress admin and the value is the value saved in the database.

## Settings

##### items

The array with checkboxes items, value or key/value.

Default value is `empty array` (no limit).

##### selected

The select item that will be selected from start. The value should match a key of your items.

Default value is `empty string`.

## Example

```php
papi_property([
  'title'    => 'Dropdown',
  'slug'     => 'my_dropdown_slug',
  'type'     => 'select',
  'settings' => [
    'items' => [
      'White' => '#ffffff',
      'Black' => '#000000'
    ]
  ]
]);
```

![Property Reference](/assets/images/docs/property-relationship.png)

## Example output

```php
string '#ffffff'
```
