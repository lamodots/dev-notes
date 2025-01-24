## HOW TO DEPLOY REACTJS APPLICATION TO CPANEL
Step 1: In the `public` directory create a `.htaccess` file. Add the following code
  ```apache
//This configuration ensures that when users access sub-routes like /login, the server will serve index.html, and React Router will handle the routing logic.

      <IfModule mod_rewrite.c>
          RewriteEngine On
          RewriteBase /
          RewriteRule ^index\.html$ - [L]
          RewriteCond %{REQUEST_FILENAME} !-f
          RewriteCond %{REQUEST_FILENAME} !-d
          RewriteCond %{REQUEST_FILENAME} !-l
          RewriteRule . /index.html [L]
      </IfModule>
```
Step 2: Open `package.json` file and add a `homepage` property which will point to the domain where you will host your React app, as so `"homepage": "https://ksn.membersng.com/",`.

Step 3: On your code editor build your react app , type `npm run build`.

Step 4: Zip build file and upload to Cpanel.
