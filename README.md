## Changes from Forked Repository:
- Update to latest version of SugarCRM Community Edition (6.5.23)
- Add persistence to SugarCRM image from docker-compose script (courtesy of fork by [@johnosorio](https://github.com/johnosorio/docker-sugarcrm))

## How to use this image

### Running with Docker Compose

The [full Github project](https://github.com/nishedcob/docker-sugarcrm) defines a Docker Compose environment which runs SugarCRM in one container and a MySQL instance in another. To set up SugarCRM using this approach, please do the following:

1. Install [Docker and Docker Compose](https://docs.docker.com/compose/install/)
2. Clone the [project](https://github.com/nishedcob/docker-sugarcrm) from Github.
3. Run `docker-compose up` from the root of this project.
4. Access `http://{docker_host}:2080` from your web browser to finish setting up SugarCRM.

### Running with Docker Run

If you already have MySQL installed or want to use a platform service line Amazon RDS, you can run the SugarCRM container seperately using Docker run. To set up SugarCRM using this approach, please do the following:

1. Install [Docker](http://docs.docker.com/installation/)
2. Run `docker run --name some-sugarcrm -e DB_HOST_NAME=yourhostname -e DATABASE_NAME=yourdatabasename -e DB_USER_NAME=yourusername -e DB_PASSWORD=yourpassword -e DB_TYPE=mysql -e DB_TCP_PORT=3306 -e DB_MANAGER=MysqlManager -p 2080:80 -d nishedcob/sugarcrm`
3. Access `http://{docker_host}:2080` from your web browser to finish setting up SugarCRM.

### Additional Tips
curl -L https://github.com/docker/compose/releases/download/1.3.3/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
docker-compose ps
docker-compose up
docker-compose up --no-recreate
