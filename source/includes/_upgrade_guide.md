# Upgrade guide

## Upgrade to 2.x from 1.x

### Properties

#### Dropdown and Post property

In 2.0.0 `placeholder` setting replaced `blank_text` and `include_blank`.


#### Relationship property

In 2.0.0 `choose_max` was renamed to `limit`.

### Settings filters

#### Show standard page type for post type

The filter `papi/settings/standard_page_type_{$post_type}` was renamed to `papi/settings/show_standard_page_type_{$post_type}`.
