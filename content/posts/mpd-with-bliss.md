+++
title="How to set up mpd with blissify"
Author="Nikhil"
math="true"
date="2021-07-02"
description="Step-by-step instructions to get started with music player daemon and creating intelligent playlists offline"
tags=["mpd", "music", "linux"]
+++


[MPD](https://github.com/MusicPlayerDaemon/MPD) is a server-side music player, which can be further improved by using different plugins and libraries to enhance overall music listening experience on all the devices on a network.

As it is a server-side application you'll also need a client to go along with it, usually MPD can relay its output to different channels at the same time so you can enjoy it on anything that can process a http stream and is on the same network (any device with a web browser). 

To create playlists and to get more fine-grained control, consider installing `ncmpcpp` or `ncmpc` former is written in C++ and latter in C.


[Bliss](https://github.com/Polochon-street/bliss) is a C library that computes distance between songs, so once you run it through your complete music collection, it will help you generate playlists on the song or album you are currently playing by queuing similar tracks.

```sh
sudo pacman -S ncmpcpp mpd mpc
```


## Why should you use MPD?

Is your music collection over 100GB which doesn't fit on a sd card so you have to choose what songs to store in your mobile? Some music players can't process that kind of collection at once.

Do you want to run your own local radio station using songs from your collection, accessible from all your devices?

It looks good on polybar, and is very rice friendly. You can even use your phone as a remote control.



## Minimal configuration of mpd

Create a config file for mpd and ncmpcpp in your `CONFIG_HOME`
```sh
mkdir .config/ncmpcpp
mkdir .config/mpd
touch .config/mpd/mpd.conf
touch .config/ncmpcpp/config
```

Now edit `mpd.conf`  as shown below and make changes accordingly

```text

music_directory	"PATH_TO_YOUR_MUSIC_FOLDER" 
db_file 	"~/.config/mpd/database"
log_file	"~/.config/mpd/log"
pid_file	"~/.config/mpd/pid"
state_file	"~/.config/mpd/state"
sticker_file	"~/.config/mpd/sticker.sql"


#music daemon options
bind_to_address	"any"
port	"6600"
log_level	"notice"
save_absolute_paths_in_playlists	"no"   #writing no so that playlists are portable (path-independent)
auto_update	"yes"
auto_update_depth "3"

audio_output {
	type	"pulse"
	name	"PULSE OUTPUT"
}

audio_output {
	type	"httpd"
	name	"My HTTP Stream"
	port	"8080"
	bind_to_address	"0.0.0.0"
	bitrate	"128"
	format	"44100:16:1"
	max_clients "0"
}

```



These are bare-minimum options.

`/etc/mpd.conf` points to example configuration file stored as `/usr/share/doc/mpd/mpdconf.example` you can look at that for all available options. I will be setting up only the required settings to get you up and running.



To configure `ncmpcpp` change the contents of `config` in `.config/ncmpcpp` to following
```sh
ncmpcpp_directory=~/.config/ncmpcpp
mpd_port=6700
mpd_music_dir="PATH_TO_MUSIC_DIRECTORY"
```


Now to test if everything works fine run `mpd` then run `ncmpcpp`
```sh
mpd
mpc update
ncmpcpp 
```

---


## Set up blissify

There are some dependencies needed to build `blissify`, if you have `ffmpeg` already installed no need to worry about them.
```sh
sudo pacman -S ffmpeg
```

Clone and build blissify
```sh
git clone --recursive https://github.com/phyks/blissify
cd blissify; mkdir build; cd build
cmake ..
make
```

Move `blissify` binary thus made in build folder to `/usr/bin`
```sh
cp build/blissify /usr/bin/
```


Now build the distance database by running `server.py` script in `blissify/mpd` folder. MPD should be running right now for this script to work, as it has to make a connection to the port MPD is running on. If you used a different port other than `6600` then change the ports in the scripts as well.

```sh
python server.py --full-rescan "PATH_TO_MUSIC_DIRECTORY"
```

It will take some time and doesn't support m4a, wav and aif codecs


After `server.py` script stops adding songs to the database, you can create playlists by running `client.py` as

```sh
python client.py --queue-length "NUMBER OF SONGS YOU WANT" --song-based
```

`--song-based` option creates playlist on the basis of the song currently playing or last played song and `--album-based` option uses the last album as the basis.

















