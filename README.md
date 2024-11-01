```
docker compose up -d
```

And check is it works now:
```
redis-cli -a SuperRedisPasswordPutHere
redis-cli --user APPUSER --pass PASSWORD
```

Don't forget to enable memory overcommit on host machine

```
sudo echo "vm.overcommit_memory=1" | sudo tee -a /etc/sysctl.conf
sudo sysctl -p
```

And check that it's applied
```cat /proc/sys/vm/overcommit_memory```

Or you will get an error:
```
WARNING Memory overcommit must be enabled! Without it, a background save or replication may fail under low memory condition. Being disabled, it can also cause failures without low memory condition, see https://github.com/jemalloc/jemalloc/issues/1328. To fix this issue add 'vm.overcommit_memory = 1' to /etc/sysctl.conf and then reboot or run the command 'sysctl vm.overcommit_memory=1' for this to take effect.
```
