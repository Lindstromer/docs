# Actions

## Include plugins or properties build for Papi

**action** `papi/include`

```php
<?php

/**
 * Example of `papi/include` action that will include a custom property.
 */

add_action('papi/include', function () {
  require_once 'class-papi-property-kvack.php';
});
```

## Description

With this action you can include plugins or properties build for Papi. Third party properties should use this action when they load there custom property in the plugin.
