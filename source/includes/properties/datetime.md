# Datetime

**type** `datetime`

## Description

The date property has a picker build in using [Pikaday](https://github.com/owenmead/Pikaday) with time support.

## Settings

##### format

The format of the date. Look at [moment.js](http://momentjs.com/) formats.

Default value is `YYYY-MM-DD hh:mm:ss`.

##### show_seconds

Show the sconds dropdown or not.

Default value is `false`.

##### show_time

Show the sconds dropdown or not.

Default value is `true`.

##### use_24_hours

Use 24 hours instead of PM/AM.

Default value is `false`.

## Example

```php
papi_property([
  'title'    => 'Datetime',
  'slug'     => 'my_datetime_slug',
  'type'     => 'datetime'
])
```

## Example output

```php
string '2014-11-21'
```
