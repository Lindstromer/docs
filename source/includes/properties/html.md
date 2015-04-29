# Html

**type** `html`

**since** 1.2.0

## Description

The property output custom html row on the page type in WordPress admin.

## Settings

##### html

String with html or a callable function or method.

Default value is `empty string`.

## Example

```php
papi_property([
  'title'    => 'Information',
  'type'     => 'html',
  'settings' => [
    'html' => '<p>Hello, world</p>'
  ]
])
```

## Example output

```php
The html property does not save any values.
```
