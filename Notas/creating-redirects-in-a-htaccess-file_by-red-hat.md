# redirects in a htaccess file
https://www.redhat.com/sysadmin/beginners-guide-redirects-htaccess


Have you ever felt a need to change the configuration of your website running on an Apache webserver without having root access to server configuration files (`httpd.conf`)? This is what the `.htaccess` file is for.

The `.htaccess` file provides a way to make configuration changes to your website on a per-directory basis. The file is created in a specific directory that contains one or more configuration directives that are applied to that directory and its subdirectories. In shared hosting, you will need to use a `.htaccess` file to make configuration changes to your server.


## Common uses of .htaccess file

The `.htaccess` file has several use cases. The most common examples include:

-   Redirections for certain URLs
-   Load custom error pages, like 404 pages
-   Force your website to HTTPS instead of HTTP
-   Allow or deny specific IP addresses access to your website
-   Password-protect certain directories on your server

## When not to use .htaccess?

The `.htaccess` file is commonly used when you don't have access to the main server configuration file `httpd.conf` or virtual host configuration, which only happens if you have purchased shared hosting. You can achieve all of the above-mentioned use cases by editing the main server configuration file(s) (e.g., `httpd.conf`) or virtual host configuration files, so you should not use `.htaccess` when you have access to those files. Any configuration that you need to put in a `.htaccess` file can just as effectively be added in a **<Directory>** section in your main server or virtual host configuration files.

## Reasons to avoid using .htaccess

There are two reasons to avoid the use of `.htaccess` files. Let's take a closer look at them.

**First**: Performance - When **AllowOverride** is set to allow the use of `.htaccess` files, `httpd` will look for `.htaccess` files in every directory starting from the parent directory. This will cause a performance impact, whether you're using it or not. The `.htaccess` file is loaded every time a document is requested from a directory.

To have a full view of the directives that it must apply, `httpd` will always look for `.htaccess` files starting with the parent directory until it reaches the target sub-directory. If a file is requested from directory `/public_html/test_web/content`, `httpd` must look for the following files:

-   `/.htaccess`
-   `/public_html/.htaccess`
-   `/public_html/test_web/.htaccess`
-   `/public_html/test_web/content/.htaccess`

So, four file-system accesses were performed for each file access from a sub-directory content even if the file is not present.

**Second**: Security - granting users permission to make changes in `.htaccess` files gives them full control over the server configuration of that particular website or virtual host. Any directive in the `.htaccess` file has the same effect as any placed in the `httpd` configuration file itself, and changes made to this file are live instantly without a need to restart the server. This can become risky in terms of the security of a webserver and a website.

## Enable the .htaccess file

To enable the `.htaccess` file, you need to have sudo/root privileges on the server.

Open the `httpd` configuration file of your website:

`/etc/httpd/conf/test.conf`

You should add the following configuration directive in the server's virtual host file to allow the `.htaccess` file in the **DocumentRoot** directory. If the following lines are not added, the `.htaccess` file will not work:

```
</VirtualHost>
<Directory /var/www/test.com/public_html>
    Options Indexes FollowSymLinks
    AllowOverride All
    Require all granted
</Directory>
```

In the case of shared hosting, this is already allowed by the hosting service providers. All you need to do is to create a `.htaccess` file in the `public_html` directory to which the service provider has given you access and to which you will upload your website files.

## Redirect URLs

If your goal is to simply redirect one URL to another, the **Redirect** directive is the best option you can use. Whenever a request comes from a client on an old URL, it forwards it to a new URL at a new location.

If you want to do a complete redirect to a different domain, you can set the following:

```
# Redirect to a different domain
Redirect 301 "/service" "https://newdomain.com/service"
```

If you just want to redirect an old URL to a new URL on the same host:

```
# Redirect to a URL on the same domain or host
Redirect 301 "/old_url.html" "/new_url.html"
Load a custom 404 Error page
```

For a better user experience, load a custom error page when any of the links on your website point to the wrong location or the document has been deleted.

To create a custom 404 page, simply create a web page that will work as a 404 page and then add the following code to your `.htaccess` file:

```
ErrorDocument 404 /error/pagenotfound.html
```

You should change `/error/pagenotfound.html` to the location of your 404 page.

## Force the use of HTTPS instead of HTTP for your website

If you want to force your website to use HTTPS, you need to use the **RewriteEngine** module in the `.htaccess` file. First of all, you need to turn on the **RewriteEngine** module in the `.htaccess` file and then specify the conditions you want to check. If those conditions are satisfied, then you apply rules to those conditions.

The following code snippet rewrites all the requests to HTTPS:

```
# Turn on the rewrite engine
RewriteEngine On

# Force HTTPS and WWW
RewriteCond %{HTTP_HOST} !^www\.(.*)$ [OR,NC]
RewriteCond %{https} off  
RewriteRule ^(.*)$ https://www.test-website.com/$1 [R=301,L]
```

Let's go through each line.

**RewriteEngine on** turns on the **RewriteEngine** module. This is required; otherwise, conditions and rules won't work.

The first condition checks if `www` is entered. **\[OR, NC\]** stands for _no case_, which means even if the entered URL has a mix of upper or lowercase case letters.

Next, it checks if the HTTPS protocol was already entered by the user. **%{https} off** means that HTTPS protocol was not used.

When the **RewriteCond** is satisfied, we use **RewriteRule** to redirect the URL to HTTPS. Note that in this case, all URLs will be redirected to HTTPS whenever any request is made.

_**\[ A free guide from Red Hat: [5 steps to automate your business](https://www.redhat.com/en/engage/5-steps-to-automate-your-business-ebook?intcmp=701f20000012ngPAAQ). \]**_ 

## Wrap up

Website owners often use the `.htaccess` file to control the behavior of their website. In this article, we have covered the basics of the `.htaccess` file and some common use cases in place on most of the websites.
