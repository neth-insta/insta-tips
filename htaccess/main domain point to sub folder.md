# Main domain point to sub folder
```php
# -- Force main domain point to sub folder
RewriteEngine On

RewriteCond %{HTTP_HOST} ^(?:www\.)?domain-name\.com.kh$ [NC]
RewriteCond %{REQUEST_URI} !^/folder/folder/ [NC]
RewriteRule ^(.*)$ /folder/folder/$1 [L]

<IfModule mod_rewrite.c>
  RewriteCond %{HTTPS} off [OR]
  RewriteCond %{HTTP_HOST} !^www\. [NC]
  RewriteCond %{HTTP_HOST} ^(.*)$  [NC]
  RewriteRule (.*) https://www.%1/$1 [R=301,L]
</IfModule>
```
