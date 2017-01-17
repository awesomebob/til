# `is_page_template('page.php')` does not work as expected.

The `is_page_template()` function uses `get_page_template_slug()` internally, which returns `null` when a default template is being used.

`is_page_template()` is therefore only helpful when checking for custom templates.

Here is an alternative:

```php
if (basename(get_page_template()) == 'page.php'){
  // ...
}
```

