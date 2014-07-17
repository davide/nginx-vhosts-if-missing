nginx-vhosts-if-missing
==============

nginx-vhosts-if-missing is a clone of the default nginx-vhosts plugin that comes
with dokku (cloned at 4f5fc58629 / 2014-05-07) with only one difference:

- If the file `/home/dokku/$APP/nginx.conf` already exists (lets say with your
customizations) it won't overwrite it.


Installation and Usage
----------------------

This plugin has been tested on dokku version 0.2.3.

1. Remove the default `nginx-vhost` plugin:
   ```sh
   rm -rf /var/lib/dokku/plugins/nginx-vhost
   ```
   
2. Install the plugin by cloning into the dokku plugins directory:
    ```sh
    git clone https://github.com/davide/nginx-vhosts-if-missing.git /var/lib/dokku/plugins/nginx-vhosts-if-missing
    ```

4. Re-push your app as needed.
   The `/home/dokku/$APP/nginx.conf` file is only generated if it doesn't already exist.
   If you're setting up SSL you might want to remove the file to let the plugin set up the SSL server block for you.


License
-------

The MIT License (MIT)