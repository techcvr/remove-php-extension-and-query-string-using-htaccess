```html
RewriteEngine on
RewriteRule ^residential-gallery/(.*)?$ gallery.php?type=$1 [L,QSA]

RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME}\.php -f
RewriteRule ^(.*)$ $1.php [NC,L]
RewriteCond %{HTTP_HOST} ^domain\.in$ [OR]
RewriteCond %{HTTP_HOST} ^www\.domain\.in$
RewriteRule ^/?$ "https\:\/\/www\.domain\.in\/" [R=301,L]

RewriteCond %{THE_REQUEST} ^.*/index\.php
RewriteRule ^(.*)index.php$ /$1 [R=301,L]
```
