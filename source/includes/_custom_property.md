# Create your own property

It's easy to create your own property with Papi. You can use our [Yo generator](http://github.com/wp-papi/generator-property)

It's important that the class follow the Papi class name.

```php
<?php

// Bad
class PropertyStringx extends Papi_Property {}

class Property_Stringx extends Papi_Property {}

class Papi_Property_String_x extends Papi_Property {}

// Good
class Papi_Property_Stringx extends Papi_Property {}
```

Example bootstrap and property class:

The html method is the important one, with out that there aren't going to be any property output in WordPress admin.

You can check how the [properties](#properties) are to figure out how to do your custom properties.

```php
<?php

// bootstrap.php
add_action('papi/include', function () {
  require_once 'class-papi-property-stringx.php';
});

// class-papi-property-stringx.php

// Exit if accessed directly
defined( 'ABSPATH' ) || exit;

/**
 * Papi - Custom property string
 *
 * @package Papi
 * @version 1.0.0
 */

class Papi_Property_Stringx extends Papi_Property {

  /**
   * The default value.
   *
   * @var string
   * @since 1.0.0
   */

  public $default_value = '';

  /**
   * Generate the HTML for the property.
   *
   * @since 1.0.0
   */

  public function html() {
    $options = $this->get_options();
    $value   = $this->get_value();

    ?>
      <input type="text" name="<?php echo $options->slug; ?>" value="<?php echo $value; ?>" />
    <?php
  }

}
```
