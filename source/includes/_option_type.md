# Option type

```php
<?php

/**
 * Example of a option type with no properties.
 */

class Header_Option_Type extends Papi_Option_Type {

  /**
   * The option type meta options.
   *
   * @return array
   */

  public function option_type() {
    return [
      'menu' => 'options-general.php',
      'name' => 'Header'
    ];
  }

}
```
