This plugin is too old and not maintained anymore. I'm afraid it's better to use `config:set` and env vars.

----

dokku-timezone-plugin
=====================

A plugin to set timezone on buildstep image created

## Install

```bash
$ cd /var/lib/dokku/plugins
$ git clone https://github.com/udzura/dokku-timezone-plugin.git timezone
```

* No `plugins-install` command needed
* Detecting timezone via `/etc/timezone` on dokku host.

```shell-session
[shell]$ git push dokku master
Counting objects: 1, done.
Writing objects: 100% (1/1), 188 bytes | 0 bytes/s, done.
Total 1 (delta 0), reused 0 (delta 0)
remote: Cloning into '/tmp/tmp.pUIXrBCKAg'...
-----> Cleaning up ...
-----> Building sample ...
remote: done.
remote: HEAD is now at 5e23906... To deploy
-----> Setting up timezone
-----> Timezone is set to Asia/Tokyo
...
```

## Setting

This plugin detects timezone via `/etc/timezone` by default.

If you want to customize default timezone, please set `${DOKKU_ROOT:=/home/dokku}/dokkurc` below:

```
export TIMEZONE=Asia/Tokyo
```

## Note

This plugin requires `/etc/timezone` file. So may work well onlly on Ubuntu/Debian.

## FAQ

### Do you know `TZ` environment variable?

Yes! But we sometimes forget to set `TZ`. This plugin helps you from such situation.
