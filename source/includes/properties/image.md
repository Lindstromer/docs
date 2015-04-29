# Image

**type** `image`

## Description

With this property you can add a image from the WordPress media library. If the gallery setting is set to true the output will be a array with objects instead of just one object.

> Since version 1.1.0 the image object contains "alt", "caption", "description" and "text".

> Since version 1.2.0 you could also use the [property gallery](/properties/gallery/) without any settings.

## Settings

No settings exists.

## Example

```php
papi_property([
  'title' => 'Image',
  'slug'  => 'my_image_slug',
  'type'  => 'image'
])
```

![Property Image](/assets/images/docs/property-image.png)


## Example output

```php
stdClass Object
(
      [width] => 800
      [height] => 600
      [file] => 2014/09/cube.jpg
      [sizes] => Array
              (
                      [thumbnail] => Array
                              (
                                      [file] => cube-150x150.jpg
                                      [width] => 150
                                      [height] => 150
                                      [mime-type] => image/jpeg
                              )

                      [medium] => Array
                              (
                                      [file] => cube-300x225.jpg
                                      [width] => 300
                                      [height] => 225
                                      [mime-type] => image/jpeg
                              )

              )

      [image_meta] => Array
              (
                      [aperture] => 0
                      [credit] =>
                      [camera] =>
                      [caption] =>
                      [created_timestamp] => 0
                      [copyright] =>
                      [focal_length] => 0
                      [iso] => 0
                      [shutter_speed] => 0
                      [title] =>
                      [orientation] => 1
              )
      [alt] => 'Alt text'
      [caption] => 'Caption text'
      [description] => 'Description text'
      [id] => 6
      [is_image] => 1
      [title] => 'Title text'
      [url] => http://site.com/wp-content/uploads/2014/09/cube.jpg
)
```
