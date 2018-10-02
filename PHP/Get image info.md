# Get image information
```php
$image_info = getimagesize('image_url');
print_r($image_info);
```
Result return as array
```php
Array
(
    [0] => 1184
    [1] => 670
    [2] => 2
    [3] => width="1184" height="670"
    [bits] => 8
    [channels] => 3
    [mime] => image/jpeg
)

```
