# Redirect to www with http
```php
RewriteCond %{HTTPS} on
RewriteRule ^(.*) http://%{SERVER_NAME}%{REQUEST_URI} [L,R=301]
```
