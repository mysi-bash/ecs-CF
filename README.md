# WordPress Docker Container

Lightweight WordPress container with Nginx 1.18 & PHP-FPM 7.3 based on Alpine Linux.

_WordPress version currently installed:_ **5.6**


## Usage
For using ,Clone the Repo,open the folder in terminal and paste the command given below in the terminal.

    docker-compose up



### WP-CLI.

This image includes [wp-cli](https://wp-cli.org/) which can be used like this:

    docker exec <your container name> /usr/local/bin/wp --path=/usr/src/wordpress <your command>