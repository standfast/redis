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

## set an unique name

```bash
$ redis-cli
redis 127.0.0.1:6379> client list
addr=127.0.0.1:53535 fd=5 name= age=11 idle=0 flags=N db=0 sub=0 psub=0 multi=-1 qbuf=0 qbuf-free=32768 obl=0 oll=0 omem=0 events=r cmd=client
redis 127.0.0.1:6379> client unique laputa
OK
redis 127.0.0.1:6379> client list
addr=127.0.0.1:53535 fd=5 name=laputa age=20 idle=0 flags=N db=0 sub=0 psub=0 multi=-1 qbuf=0 qbuf-free=32768 obl=0 oll=0 omem=0 events=r cmd=client
redis 127.0.0.1:6379> client unique laputa
(error) ERR client already exists
```

