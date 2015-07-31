Bounce
======

Bounce is a Bash script that quickly restarts applications, system services, network interfaces—anything it knows about.

Sometimes one of these services, for short, needs to be restarted because it's acting funny, because of planned maintenance, or just because. Restarting the whole machine may be only a few clicks or a clever command away, but that's kind of like using a sledgehammer to "slice" an avocado.

Restarting individual services typically requires multiple commands, the knowledge of which is only unlocked after reading liberal amounts of `man <whatever>` and `sudo`ing around without a helmet, hoping nothing breaks.

Bounce makes restarting individual services convenient one-liners so you can stay [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) and not get guacamole everywhere.


Requirements
------------

- OS X 10.10 Yosemite and later.


Installation
------------

Copy `bounce` to a directory in your `PATH` and make it executable.


Usage
-----

When run as a normal user, Bounce only asks for your password when `sudo` is required.

Bounce's syntax is super simple. Restarting Wi-Fi is as easy as:

```
bounce airport
```

To restart wired networking:

```
bounce ethernet
```

Do both together:

```
bounce wifi ethernet
```

Bounce uses aliases for some services. In this case, `bounce airport` and `bounce wifi` are identical under the hood. Likewise, if you want to restart Spotlight, both `bounce spotlight` and `bounce mds` will take care of any `mds`, `mds_stores`, and `mdworker` processes. You can use whichever name you prefer or remember most easily.

Bounce only works on applications and services it knows about. For full usage and a list of all supported services:

```
bounce -h
```

**Note:** Bounce does not check whether a service is already running. Stopped services will be started, and running services will be restarted.


License
-------

Copyright 2015 Bradley Sepos
Released under the MIT License. See [LICENSE](LICENSE) for details.
