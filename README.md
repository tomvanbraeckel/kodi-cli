kodi-cli
========

Kodi/XBMC bash script to send Kodi commands using JSON RPC. It also allows sending youtube videos to Kodi.

#Usage

`kodi-cli -[p|i|s|(y|q) youtbe URL/ID|t "text to send"|o "youtube title"|r 'magnet://ss']`

#Arguments
```
 -p Play/Pause the current playing video.
 -s Stop the current playing video.
 -y Play youtube video. Use either URL/ID (of video).
 -q Queue youtube video to the current list. Use either URL/ID (of video). Use instead of -y.
 -o Play youtube video directly on Kodi. Use the name of video.
 -i Interactive navigation mode. Accept keyboard keys of Up, Down, Left, Right, Back,
   Context menu and information
 -T Play Twitch live stream. Needs name of channel as argument.
 -D Play a direct video link. Needs name of channel as argument.
 -t Send text to Kodi to display on screen. Pass 'text to send as a parameter.'
 -r 'magnetlink' Magnet link to play via xbmctorrent
 -u Increase the volume on Kodi
 -a Interact with the addons namespace, you can use the following subcommands
 	  list [filter] - Retrieves a list of addons. Optionally accepts a filter i.e. xbmc.addon.video 
 	  exec addon action - Execute an action on an addon
 	  play addon subdir [subdir...] file - Chdirs into the subdirectories of the addon and starts playing a item. Useful for addons with changing URLs
 -L List files in a directory
 -d Decrease the volume on Kodi
 -f Toggle fullscreen
 -h Show this help message
```

#Examples
List all addons
`kodi-cli -a list`

List all video addons
`kodi-cli -a list xbmc.addon.video`

List contents of a directory (in this case an addon)  
`kodi-cli -a list 'plugin://net.rieter.xot/'`

Traverse through an addons directories to start playing an item. This can be handy, when addons store values in the URL and changes regulary.
`kodi-cli -a play 'net.rieter.xot' "Uitzendinggemist (NPO.nl)" "Live TV" "3FM Live"`


#Dependencies
* curl(1) is used to make actual JSON RPC requests
* for the "-o" option to work you'll need to install [mps-youtube](https://github.com/np1/mps-youtube)
* jq for reading out json responses https://stedolan.github.io/jq/

#Version
1.0
