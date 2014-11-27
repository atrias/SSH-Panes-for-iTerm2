SSH-Panes for iTerm2
====================

SSH-Panes for iTerm2 is written in Applescript and makes connecting to multiple SSH hosts easy. After connecting, the keyboard input is directed to all hosts simultaneously.

The script has been tested with currently latest iTerm2 (build 2.0.0.20141103) in OSX Mavericks.

## Installation

Just place **SSH-Panes.scpt** script in **~/Library/Application Support/iTerm/Scripts** directory. Create the directory if it does not exist. 
Restart iTerm and a new Script menu will appear which contains a link that will allow you to run the script.

## Configuration

Create file **~/serverlist** with the connection strings for the hosts that you want to connect to. Each connection string should be placed on a new line. Empty lines are ignored. Lines starting with # are also ignored and can be used as comments.

For each connection string you can specify whatever you would have written after the "ssh" command on a terminal. For example:

- hostname, *server.example.com*
- ip address, *192.168.1.1*
- specify username, *username@host*
- specify port, *host -p 522*
- combinations of the above
- any other ssh command option

You can also define host specific or default ssh configurations in your [.ssh/config file](http://linux.die.net/man/5/ssh_config).

## Usage

After creating your *serverlist* file just click *SSH-Panes.scpt* in Script menu to see the magic! For each host a new pane will be created in the current tab. At the end you will be asked if you want to direct keyboard input to all panes simultaneously. Click OK and you are ready to go!

### Thanks

My script is based on [Wim Deblauwe's](https://wimdeblauwe.wordpress.com/2014/07/16/opening-multiple-ssh-sessions-with-iterm-automatically/) script.
Changes are these:

- Make comments possible in serverlist file by using # as first character
- Fixed a bug where the script would not work if there was no iTerm window open
- Removed "root@" from ssh execution command to allow more flexibility for connection strings in serverlist file
- Added code to switch keyboard input to all panes automatically after connection (this works nicely for connections using [SSH keys](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys--2))

