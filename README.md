# docker_rails_spring_mysql_template

## outline

This is the docker + rails + spring + mysql encironment starter.
This program reffers to "https://qiita.com/kawasin73/items/2253523be18e5afd994f" or "https://github.com/kawasin73/rails_docker_template.git".
kawasin73 uses postgresql but I use mysql as DB.

You can build the environment by just typing the command writtten below.

## Usage

```
$ git clone this repostitory
$ cd this project
$ script init && bootstrap
```

### MySQL root user password and how to connect mysql on docker

You can connect to the mysql built in docker container by executing the command below

```
$ mysql -u root -h 127.0.0.1 -P 13306 --protocol=tcp -p
```

On executing this, you are going to be asked password of mysql on docker.
Default password is set to be "password".
You may change the mysql password as you like.

### how to execute rails command

You can use rails command on spring container like below

```
$ docker-compose exec spring < commadn you want to use >

ex.)
$ docker-compose exec spring rails db:migrate
$ docker-compose exec spring bundle install
```

By using spring container, you can execute rails command fast.

### Why using entirkit?

By executing "bundle install" in ENTRYPOINT, it is possible to cache gems into Docker Volume.
You don't have to install all gems every time when add some gems in your project.
