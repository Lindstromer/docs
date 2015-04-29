# Repeater

**type** `repeater`

## Description

The repeater property can create a repeater of sub fields which can be repeated again and again.

## Settings

##### items

The array of properties, the same key/values as the `$this->property` method or `papi_property` function has.

You can't use property repeater inside a repeater.

Default value is `empty array`.

## Filters

**tag** `papi/property/repeater/exclude`

Prevent properties from render and working in repeater.

```php
add_filter('papi/property/repeater/exclude', function ($exclude) {
  return array_merge($exclude, [
    'string'
  ]);
});
```

## Example

```php
papi_property([
  'title'    => 'Repeater',
  'slug'     => 'my_repeater_slug',
  'type'     => 'Repeater',
  'settings' => [
    'items' => [
      [
        'type'  => 'string',
        'title' => 'Title',
        'slug'  => 'my_string_slug'
      ],
      [
        'type'     => 'dropdown',
        'title'    => 'Color',
        'slug'     => 'my_dropdown_slug',
        'settings' => [
          'items' => [
            'White' => '#ffffff',
            'Black' => '#000000'
          ]
        ]
      ]
    ]
  ]
])
```

![Property Repeater](/assets/images/docs/property-repeater.png)

## Example output

```php
Array
(
  [0] => Array
  (
    [my_string_slug] => "Test 1"
    [my_dropdown_slug] => "#ffffff"
  )

  [1] => Array
  (
    [my_string_slug] => "Test 2"
    [my_dropdown_slug] => "#000000"
  )
)
```
