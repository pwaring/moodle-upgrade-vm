Moodle Upgrade VM
=================

Vagrant configuration for testing Moodle upgrade from 1.9.19 to 2.5.4.

Unlikely to be of much use unless you meet all the following criteria:

 * Need to upgrade Moodle from 1.x to 2.x (major version bump, lots of changes).
 * Use Gentoo as your Linux distribution.
 * Use Apache as your web server.
 * Use MySQL as your database server.
 
Requirements
------------
 
 * Vagrant 1.4.x or later.
 * VirtualBox 4.3.x or later.

Vagrant box
-----------

The box used is a standard x86 Gentoo install, with the following changes:

 * `gentoo-sources` is 3.4.76, as this VM needs to run on a machine without support for hardware virtualization. Gentoo kernels from 3.10 onwards hang - see: https://www.virtualbox.org/ticket/12469

In addition, the following packages have been installed:

```
www-servers/apache
dev-db/mysql
dev-lang/php
app-admin/puppet
```

The global `USE` variable is set to: `bindist -X apache2 mysql php`