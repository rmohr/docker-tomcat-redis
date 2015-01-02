Tomcat with Redis Session Manager
=================================

This tomcat docker image uses redis as session store, made possible by the  [Tomcat Redis Session Manager](https://github.com/rmohr/tomcat-redis-session-manager) Project.

Start Redis
-----------

```
docker run -d --name redis-session-store redis
```

Start Tomcat
------------
```
docker run -d --link redis-session-store:redis -p 8080:8080 rmohr/docker-tomcat-redis:7.0
```

Connection Properties
---------------------------

To modify the Redis connection setting, adjust the environment variable `REDIS_HOST` and `REDIS_PORT` to your needs.



