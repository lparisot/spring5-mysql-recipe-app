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

