# Building and Running Wordpress

Follow the next steps to install and run Wordpress on your local machine:

## Build the project

Run `docker-compose up -d` from the project directory.

This runs `docker-compose up` in detached mode, pulls the needed Docker images, and starts the wordpress and database containers.

Note: WordPress Multisite works only on ports 80 and/or 443. If you get an error message about binding 0.0.0.0 to port 80 or 443 (depending on which one you specified), it is likely that the port you configured for WordPress is already in use by another service.

## Bring up WordPress in a web browser

At this point, WordPress should be running on port 8000 of your Docker Host, and you can complete the “famous five-minute installation” as a WordPress administrator.

Note: The WordPress site is not immediately available on port 8000 because the containers are still being initialized and may take a couple of minutes before the first load.

If you are using Docker Machine, you can run the command docker-machine ip MACHINE_VM to get the machine address, and then open http://MACHINE_VM_IP:8000 in a web browser.

If you are using Docker Desktop for Mac or Docker Desktop for Windows, you can use http://localhost as the IP address, and open http://localhost:8000 in a web browser.

## Shutdown and cleanup

The command `docker-compose down` removes the containers and default network, but preserves your WordPress database.

The command `docker-compose down --volumes` removes the containers, default network, and the WordPress database.

## Updating Wordpress version on Docker image

In order to update the Wordpress version, go to the project folder and run `docker pull` in the terminal. This will copy and update the Wordpress image to the latest version.