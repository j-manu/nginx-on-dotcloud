Nginx-on-dotcloud
=================
Custom nginx install on dotcloud

How to use
----------
1. clone this repo
2. make any changes you need
3. dotcloud create <app_name>
4. cd into the nginx-on-dotcloud directory
5. dotcloud push <app_name> .


Config
------
If you need to change the way nginx is compiled, then you will need to look in the nginx/builder file.

If you need to change the nginx config, then you need to edit /nginx/nginx.conf.in

How it works
------------
When the custom service starts up it runs the nginx/builder file which compiles nginx and puts everything where it needs to be.

During deployment to the host the postinstall script will be run, and it will add the HTTP Port that it was assigned to the nginx.conf.in file.

It will then be started up, and if all went well you should be able to start seeing pages served from nginx.