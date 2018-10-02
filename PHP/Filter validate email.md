# Filter validate email
For filter normal encoding email
```php
$is_email = filter_var('neth@gmail.com', FILTER_VALIDATE_EMAIL);
```
For filter unicode email
```php
$is_email = filter_var('néth@gmail.com', FILTER_VALIDATE_EMAIL, FILTER_FLAG_EMAIL_UNICODE); // PHP 7.1.*
```
