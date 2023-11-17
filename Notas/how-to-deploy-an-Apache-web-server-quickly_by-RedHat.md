# How to deploy an Apache web server quickly

https://www.redhat.com/sysadmin/install-apache-web-server

Sometimes you need to deploy a web server quickly. A web server makes it easy to do things like test web applications, implement a proof-of-concept project, or just get familiar with web development.

The steps below cover how to do that using the venerable Apache HTTP Server. I'll begin with installation, then continue with editing a basic configuration file, creating a few documents, setting the firewall, and finally, testing the service.

Note that this is a very basic test deployment. It's not suitable for internet-facing web servers. To be production-ready, you must [configure firewalls](https://www.redhat.com/sysadmin/secure-linux-network-firewall-cmd) and [audit your server settings](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/security_hardening/overview-of-security-hardening-security-hardening).

## Install Apache

If your Linux distribution doesn't already include Apache, run the following command to install the package:

```
$ sudo dnf install httpd
```

Adjust the command accordingly if you use a different package manager.

## Edit the config file

Using your text editor of choice (mine is [Vim](https://www.redhat.com/sysadmin/four-things-vim), but [Nano](https://www.redhat.com/sysadmin/four-things-nano) or others work just as well), open `/etc/httpd/conf/httpd.conf`.

These two values may already be set in that file, but confirm them to be sure:

```
DocumentRoot /var/www/html
Listen 80
```

Use the search function in your editor to find the appropriate stanzas. You may need to uncomment the `DocumentRoot` stanza. This article uses the standard location at `/var/www/html`.

The `Listen` directive simply indicates which port the service listens on. In this case, use the standard port 80 for HTTP.

**_\[ Better integrate security into your software lifecycle. Download the [guide to implementing DevSecOps](https://opensource.com/downloads/guide-implementing-devsecops?intcmp=701f20000012ngPAAQ). \]_**

## Manage the service

You've installed a web server, but you haven't started running it yet. Use the `systemctl` command to start and enable the `httpd` service:

```
$ sudo systemctl start httpd
$ sudo systemctl status httpd
```

Starting a service doesn't mean it will start automatically from now on. To make your web server start automatically after a reboot, use the `enable` subcommand:

```
$ sudo systemctl enable --now httpd
```

## Open port 80

Now that the site is configured (and in a real-world situation, secured), it's time to open the firewall. I'll assume you're [using `firewalld`](https://www.redhat.com/sysadmin/how-to-configure-firewalld), so type the following commands to permit HTTP traffic into the server:

```
$ sudo firewall-cmd --permanent --zone=public --add-service=http
$ sudo firewall-cmd --reload
$ sudo firewall-cmd --list-all --zone=public
```

You may need to adjust the zone value, depending on your distribution.

## Test the server

First, test the server with a browser. Launch Firefox and navigate to `localhost:80` to see the Apache web server's default confirmation page.

## Create content

You probably didn't install a web server just to see "It works!" in your browser. To make your server a little more interesting, launch your favorite text editor using `sudo`, and create a few pages to simulate a website. Feel free to make this as simple or complex as you'd like. You can also create a text file to test downloads from the site.

Your site's homepage is by default `index.html`, and it's located in `/var/www/html`. Make a backup copy of the existing `index.html` file and create a new one containing the following code:

```
<html>
<head>
<title>Welcome to my test site!</title>
</head>
<body>
This site is for testing purposes only
</body>
</html>
```

Additionally, create a new text file called `download-this.txt` with the following content so that you can test the `curl` and `wget` commands later:

```
If you can read this, the download succeeded!
```

Store these two files at `/var/www/html`.

## Look at files

Assuming that works, do a test download of the `download-this.txt` file.

Use a different system on the same segment to test the web service. On the new system, launch a web browser. In the address bar, type the web server's IP address.

Don't forget, you can launch a browser and point it at a site from the terminal:

```
$ firefox http://IP
```

Do you see your welcome page?

Sysadmins frequently use `curl` or `wget` to download files using HTTP. This ability is particularly handy for hands-free downloads in scripts or other automation scenarios.

Run these two commands to confirm file download functionality:

```
$ sudo dnf -y install curl

$ curl -O http://IP/download-this.txt
```

```
$ sudo dnf -y install wget

$ wget http://IP/download-this.txt
```

Did you receive the `download-this.txt` file? Use `ls` to display the file and `cat` to read its contents. You might have two copies of the file if you tested the download using both the `curl` and `wget` commands.

**_\[ Download the eBook [Manage your Linux environment for success](https://www.redhat.com/en/engage/linux-management-ebook-s-201912231121?intcmp=701f20000012ngPAAQ). \]_**

## Check the logs

Check the Apache log files for access information. For example, type the following to see log entries indicating the file download transactions:

```
$ sudo cat /var/log/httpd/access_log | grep -I download-this.txt
```

## Wrap up

That's it! You've installed, configured, and tested a very basic web server deployment in just a few steps. Don't forget to investigate security settings before placing such a deployment in your production environment or exposing it to the outside world.
