# Reference

**since** 1.2.0

**type** `reference`

## Description

When using Post or Relationship property to load modules or something like that.
You may what to check which pages are loading the module. This is where the reference property comes in hand,
it will show which pages that has a reference to the module.

## Settings

##### slug

String or array of slugs to look for references.

Default value is `empty string`.

##### page_type

String or array of page types (the file name of the page type) to check.

Default value is `empty array`.

## Example

```php
papi_property([
  'title'    => 'Reference',
  'type'     => 'reference',
  'settings' => [
    'slug'      => 'top_module',
    'page_type' => 'start-page-type'
  ]
])
```

![Property Reference](/assets/images/docs/property-reference.png)

## Example output

The reference property does not save any values.
