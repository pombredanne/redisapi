#redis-api

[![Build Status](https://travis-ci.org/globocom/redis-api.png?branch=master)](https://travis-ci.org/globocom/redis-api)

This API exposes a Redis service to application developers using [tsuru
PaaS](http://tsuru.io).

##Installation and configuration

This API is ready for being deployed as a tsuru application. It depends on the
following environment variables:

* **REDIS_SERVER_HOST**: the address of the server to which the API will
  provide access. _Default value:_ ``none``. redis-api will fail to start if
  this variable is not defined.
* **REDIS_SERVER_PORT**: port used to connect to the Redis server. _Default
  value:_ 6379.
* **REDIS_SERVER_PASSWORD**: password used to connect to the Redis server.
  _Default value:_ none. When undefined, access will be unauthenticated. For more
  details, check "Authentication feature" at <http://redis.io/topics/security>.
* **REDIS_PUBLIC_HOST**: the public hosts that apps will use to the connect to
  the redis server. This may be useful in the case where you have a public and
  a private IP, the private IP is used by the API to manage the server, and the
  public API is delivered to apps whenever tsuru binds it to a service
  instance. _Default value:_ the value of ``$REDIS_SERVER_HOST``.
