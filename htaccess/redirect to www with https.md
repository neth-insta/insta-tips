# Redirect to www with https
```php
RewriteEngine On

RewriteCond %{HTTP_HOST} !^www\. [NC]
RewriteRule ^(.*) https://www.%{SERVER_NAME}%{REQUEST_URI} [L,R=301]

RewriteCond %{HTTPS} off
RewriteRule ^(.*) https://%{SERVER_NAME}%{REQUEST_URI} [L,R=301]
```
