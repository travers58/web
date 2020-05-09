---
path: "/content/sample01/"
date: "2020-04-08"
title: "Sample 1"
tags: ["example"]
---

#### Here is the first page

----

```
# Sets the default security model of the Apache2 HTTPD server. It does
# not allow access to the root filesystem outside of /usr/share and /var/www.
# The former is used by web applications packaged in Debian,
# the latter may be used for local directories served by the web server. If
# your system is serving content from a sub-directory in /srv you must allow
# access here, or in any related virtual host.
<Directory />
        Options Indexes FollowSymLinks Includes ExecCGI
        AllowOverride All
        Require all granted
</Directory>

<Directory /usr/share>
        AllowOverride None
        Require all granted
</Directory>

<Directory /var/www/>
        Options Indexes FollowSymLinks
        AllowOverride None
        Require all granted
</Directory>
```

> Testing the downstream jenkins job.

> test2

> The third test is always the best test.

> Now is the acid test.


> here we go again the item should bind to changes made on build #10

> Check to see if content pull from upstream  - look for build # 23

>Ok.  The text should show up on the CDN and the smoke job is #4.

>Look for a upstream project trigger here job is #4 on the master branch

>Update to web repo will trigger master on gatsby/master Success is job #5

> Look for job seven here
> 
> Git web hook.
> 
> Let's try again.