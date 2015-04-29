# Color

**type** `color`

## Description

The property output the WordPress color picker.

## Settings

##### show_input

Show the text input.

Default value is `true`.

##### palettes

Array with hex colors

Default value is `empty array`.

## Example

```php
papi_property([
  'title'    => 'Color',
  'slug'     => 'my_color_slug',
  'type'     => 'color'
])
```

## Example output

```php
string '#ffffff'
```
