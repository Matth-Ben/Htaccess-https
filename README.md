# Htaccess-https
#Wordpress

#Passer un site de Http à Https, pensez a refaire les permalinks

#et refaire son dossier Htaccess comme-ci



# BEGIN WordPress

<IfModule mod_rewrite.c>
  
  RewriteEngine On
  
  RewriteCond %{SERVER_PORT} !^443$
  
  RewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI} [R=301,L]
  
  RewriteBase /
  
  RewriteRule ^index\.php$ - [L]
  
  RewriteCond %{REQUEST_FILENAME} !-f
  
  RewriteCond %{REQUEST_FILENAME} !-d
  
  RewriteRule . /index.php [L]

</IfModule>
