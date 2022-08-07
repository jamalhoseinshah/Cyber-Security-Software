#### How to Install and Configure Nginx from Source on Linux

Nginx is written in C language by Igor Sysoev to overcome the C10K problem (i.e. Concurrently handling 10k(ten thousand) connections). The problem was how to optimize the network socket to handle numerous clients at the same time. Nginx is a solution to that problem. It is a free and open-source software for reverse proxying, load balancer, web serving, media streaming, etc

Function of nginx

    It supports reverse proxy with caching.
    It supports WebSockets, load balancing, and fault tolerance.
    It supports FastCGI  with caching.
    It can be used for handling static files, index files, and auto-indexing.
    It supports SSL.
    Both name-based and IP-based virtual servers can be configured in Nginx.
    HTTP basic authentication
    All the main mail proxy server features are supported in Nginx.
    
    
### Installation of Nginx
    
    
   * you can download the Nginx web server archive file by running the following command in the terminal.

               wget http://nginx.org/download/nginx-1.21.1.tar.gz

   * unzip folder by going to location right click unzip folder same location where you have downloaded.


  * What is libpcre3-dev

    This is a library of functions to support regular expressions whose syntax and semantics are as close as possible to those of the Perl 5 language.


               sudo apt install libpcre3 libpcre3-dev 
   
   *   Start the configuration installer of the Nginx.

              ./configure

   * Run the make install command to install the built package.

              sudo make install

   * Navigate to /usr/local/nginx using the cd command (change directory):

             cd /usr/local/nginx/sbin

   * To check what is the current installed version of the Nginx.

            ./nginx -v

    * Navigate to the default location where Nginx is installed by running the following command in the terminal.

             cd /usr/local/nginx/sbin

   *  Now, we can start the Nginx server by running the following command:

             sudo ./nginx

   * To see if it’s working, go to the local host or your URL.
   
   *  Steps to change the default Nginx Listen Port.

   *  Open the nginx.conf file by running the following command:

           sudo nano /usr/local/nginx/conf

   * Navigate to this server section and change listen 80; port to any other port number, e.g. 5555, etc.
   
   *  To see if it’s working, go to the local host or your URL.   localhost:5555 on url
   
   
   * To stop the Nginx server, we just need to add the flag -s  to stop the Nginx command as follows.

               sudo ./nginx -s stop

   * TO check o see if it’s working, go to the local host or your URL. if not ngnix page it mean it stopped.

   * To uninstall Nginx, run the following command in the terminal with superuser permissions, i.e. sudo :

             sudo rm -f -R /usr/local/nginx && rm -f /usr/local/sbin/nginx
    
   
   jamal hussain shah 
   
![Screenshot_2022-08-06_23_03_10](https://user-images.githubusercontent.com/95676591/183277430-dd24c2
![Screenshot_2022-08-06_23_03_51](https://user-images.githubusercontent.com/95676591/183277453-869cfb81-a4bc-49fa-bf33-3958c53c76e5.png)

![Screenshot_2022-08-07_09_45_58](https://user-images.githubusercontent.com/95676591/183277472-1ccd47dd-acb5-47bf-af3e-fbdf6da7a2b5.png)
 
   

   
