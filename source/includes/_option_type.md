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

## Namespaces

```php
<?php

namespace Foo\Bar;

class Test_Option_Type extends \Papi_Option_Type {}
```

Papi has no problem to work with page types that have namespaces.
