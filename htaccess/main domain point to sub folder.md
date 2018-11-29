# Main domain point to sub folder
```php
RewriteEngine On

RewriteCond %{HTTP_HOST} ^(?:www\.)?domain-name\.com.kh$ [NC]
RewriteCond %{REQUEST_URI} !^/uat_folder/ [NC]
RewriteRule ^(.*)$ /live_folder/$1 [L]
```
