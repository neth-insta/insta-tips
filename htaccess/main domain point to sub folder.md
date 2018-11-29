RewriteEngine On

RewriteCond %{HTTP_HOST} ^(?:www\.)?mekongmicroinsurance\.com.kh$ [NC]
RewriteCond %{REQUEST_URI} !^/mmi_website/public/ [NC]
RewriteRule ^(.*)$ /mmi_website/public/$1 [L]
