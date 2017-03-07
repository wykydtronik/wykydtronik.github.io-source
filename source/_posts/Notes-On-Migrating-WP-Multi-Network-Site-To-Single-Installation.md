---
title: Notes On Migrating WP Multi Network Site To Single Installation
date: 2017-03-03 15:06:46
tags: WordPress
---
Just taking notes on how to migrate a site from a WP Multi Network instance and bring it into a single WP installation instance.

1.) Get The blog_id and site_id of target site. This can be obtained through wp_blog
2.) Export the appropriate tables pertaining to the targeted WP Multi Network site. Include the Drop statement.
3.) Find and Replace the prefixes for the new installation, for example lets revert back to wp_
4.) Editing your hosts file and redirect traffic from targetdomain.com to 127.0.0.1 - this will allow you to mock up the new installation and have it resolve. You might run into cookie issues, so be sure to run incognito only when your local LAMP/XAMP setup is setup. Personally, I use vhosts.
5.) Install WP on your localhost. Copy all the active plugins and the theme into the new localhost installation.
6.) Download all the files in the specific media directory in blogs.dir - retain the Mu blogs.dir file path.
7.) Import the exported sql file

There can be metadata that breaks with this, off the top of my head in wp_options file upload URL and various serialized data with paths might break. Theme options are one of these. I would recommend using [Database Search And Replace Script in PHP by Interconnect/it](https://interconnectit.com/products/search-and-replace-for-wordpress-databases/). In most of my cases, I have to fix header, logo, and favicon paths. Depending on what theme you're dealing with, this could be either simple or complex enough to run the script mentioned above.

UPDATE: I just realized, there is another adjustment that needs to be made in wp_options which is crucial. In wp_options, look for the option_name similar to wp_user_roles. If you have a different prefix on your Multi Network, this name needs to change. For example, if it's called myblogprefix_user_roles - the user roles are broken upon signing in. Just quickly go in and change this to wp_user_roles

There's obviously a lot of steps missing, these are merely notes.

Remember backup everything.
