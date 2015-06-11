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

Option type class extends the [page type class](#page-type) so you can create options pages with Papi!

### Differents between option type and a page type

- Does not save the option type id in the database since options don't have a post id. So you can't have different option types that has the same property slug.
- The `page_type` method is named `option_type`.

## Namespaces

```php
<?php

namespace Foo\Bar;

/**
 * Example of a option type with namespace.
 */

class Test_Option_Type extends \Papi_Option_Type {}
```

Papi has no problem to work with option types that have namespaces.
