# spring5-recipe-app

[![CircleCI](https://circleci.com/gh/lparisot/spring5-mysql-recipe-app.svg?style=svg)](https://circleci.com/gh/lparisot/spring5-mysql-recipe-app)
[![codecov](https://codecov.io/gh/lparisot/spring5-mysql-recipe-app/branch/master/graph/badge.svg)](https://codecov.io/gh/lparisot/spring5-mysql-recipe-app)

### Add project lombok

```
Add dependency:
    groupId: org.projectlombok
    artifactId: lombok

Add plugin
    In preferences/plugin, add lombok
```

### Automatic reload when code modification

1. add spring-boot-devtools in your project
1. meta+shift+a
    1. select registry
    1. search for compiler.automake.allow.when.app.running
    1. set to true
1. open preferences
    1. in build/compiler, set build project automatically
1. add plugin livereload in the browser

### Database

Profile by default will works with an H2 database.

Profiles dev and prod will work with a MySQL database.

Profile dev will work in sfg_dev database with sfg_dev_user user name.

Profile prod will work in sfg_prod database with sfg_prod_user user name.

You can switch profile in application.properties file, property spring.profiles.active.

#### <span style="color:blue">H2</span>

The H2 database will be populate by data-h2.sql file and RecipeBootstrap class.

#### <span style="color:blue">MySQL</span>

I use a container to set my database:
```bash
$ docker volume create mysql-vol
$ docker run --name lpa-mysqldb -p 3306:3306 -e MYSQL_ALLOW_EMPTY_PASSWORD=yes -v mysql-vol:/var/lib/mysql -d mysql
```

Actually for MySQL, you must manually apply:

    . configure-mysql.sql script to create the databases and associated users.
    . database-create.sql script to create tables

The database will be populate by the BootstrapMySQL class.
