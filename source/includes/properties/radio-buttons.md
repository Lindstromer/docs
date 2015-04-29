# Radio buttons

**type** `radio`

## Description

With this property you can create a list of radio buttons. The key is the value that the user will se in the WordPress admin and the value is the value saved in the database.

## Settings

##### items

The array with checkboxes items, value or key/value.

Default value is `empty array`.

##### selected

The radio button that will be selected from start. The value should match a key of your items.

Default value is `empty string`.

## Example

```php
papi_property([
  'title'    => 'Colors',
  'slug'     => 'my_radio_slug',
  'type'     => 'radio',
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
string '#ffffff'
```
