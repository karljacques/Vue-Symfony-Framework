# Vue-Symfony-Framework

* In `./php-fpm/nginx.conf` change `INSERT_YOUR_URL` to a URL you have set up in your hosts file to point at localhost.
* In `client/src/App.vue` change `YOUR_URL_HERE` to the same URL as above.
* In root, run `docker-compose up -d`
* In `./client` run `npm run serve`

Navigate to your `localhost:8080`, the word `pong` should appear.
