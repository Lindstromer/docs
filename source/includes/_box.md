# Box

```php
<?php

/**
 * Example of the default options
 */

$this->box([
  'capabilities' => array(),
  'context'      => 'normal',
  'mode'         => 'standard',
  'post_type'    => 'page',
  'priority'     => 'default',
  'sort_order'   => 1000,
  'title'        => ''
]);
```

Documentation of the `box` method. `box` is a short name for `metabox` in Papi.

### Options

Key          | Default
-------------|--------------|---------------------------------------------------
capabilities | array()      | Can be a string with a role or capability or a array with many values
context      | 'normal'     | The same value as for context in `add_meta_box`
mode         | 'standard'   | `standard` or `seamless` (no metabox)
post_type    | 'page'       | The post types where the box should be available
priority     | 'default'    | The same value as for priority in `add_meta_box`
sort_order   | 1000         |
Numeric value, lowest value in the meta box will be at the top and the highest value at the bottom
title        | empty string | The title of the meta box. This can't be empty, seamless mode will not show the title. When passing a string as the first argument for box method it will become `array('title' => 'the title')` automatic


### Callable method

Since version 1.2.0 it's possible to use callable method as a second argument in your box method
that returns a array with properties or tabs.

```php
<?php

/**
 * Example of using the callable parameter.
 */

public function register() {
  $this->box('Content', array($this, 'content_box'));
}

public function content_box() {
  return [
    $this->property([
      'type'  => 'string',
      'title' => 'Name'
    ]),
    $this->property([
      'type'  => 'text',
      'title' => 'About'
    ])
  ];
}
```
