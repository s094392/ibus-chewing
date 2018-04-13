# IBus-Chewing

IBus-Chewing is an IBus front-end of Chewing, an intelligent Chinese input method for Zhuyin (BoPoMoFo) users.

Following documents provide further instruction:

 * COPYING: GPLv2 Licence
 * INSTALL: Installation instruction.
 * USER-GUIDE: How to use ibus-chewing

Bugs and enhancement can be filed to either:

 * [Red Hat Bugzilla](https://bugzilla.redhat.com/enter_bug.cgi?product=Fedora&component=ibus-chewing)
 * [GitHub ibus-chewing](https://github.com/definite/ibus-chewing/issues)


# Development

We use **[K&R](https://en.wikipedia.org/wiki/Indent_style#K.26R_style), 4 spaces** coding style to make our review easier, so if you like to contribute, please set the git pre-commit hook by:
```sh
ln -s ../../pre-commit .git/hooks/pre-commit
```

## Instalation guide
0. Required: 
    cmake      >= 2.6.2
    ibus       >= 1.3
    glib       >= 2
    gob        >= 2.0.16
    gtk        >= 2
    libchewing >= 0.3.3
    libX11

1. Clone this repository
```sh
git clone --recursive https://github.com/s094392/ibus-chewing.git
```

2. Make & install
```sh
cd ibus-chewing
cmake . -DCMAKE_INSTALL_PREFIX='/usr' -DLIBEXEC_DIR='/usr/libexec'
make
sudo make install
```

3. Restart ibus
```sh
ibus restart
```

## For debugging ibus-chewing

1. Quit existing ibus-daemon
	* By right click on IBus systray icon, then quit, or
	* kill the process, or
	* with command: `ibus exit`

2. Edit `/usr/share/ibus/component/chewing.xml`, add `-v 7` to turn verbose level 7

3. Run ibus-daemon in command line with following command:
```
export G_MESSAGES_DEBUG=all
ibus-daemon -rvx
```
