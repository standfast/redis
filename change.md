## support atexit

```bash
$ redis-cli
redis 127.0.0.1:6379> script load "redis.call('set', 'laputa', 'come here to swim')"
"6b4027544f3be9cd70bbffbc4fa8652555e8212e"
redis 127.0.0.1:6379> atexit 6b4027544f3be9cd70bbffbc4fa8652555e8212e 0
OK
redis 127.0.0.1:6379> get laputa
(nil)
redis 127.0.0.1:6379>
$ redis-cli
redis 127.0.0.1:6379> get laputa
"come here to swim"
```

