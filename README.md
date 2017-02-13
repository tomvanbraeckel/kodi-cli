kodi-cli
========

Kodi/XBMC bash script to send Kodi commands using JSON RPC. It also allows sending youtube videos to Kodi.

#Usage

`kodi-cli -[p|i|s|(y|q) youtbe URL/ID|t "text to send"|o "youtube title"|r 'magnet://ss']`

#Arguments
```
-p Play/Pause the current played video
-s Stop the current played video
-y play youtube video. Use either URL/ID (of video)
-q queue youtube video to the current list. Use either URL/ID (of video). Use after -y.
-o play youtube video directly on Kodi. Use the name of video.
-i interactive navigation mode. Accept keyboard keys of Up, Down, Left, Right, Back, information and context menu.
-t "text to send"
-r 'magnetlink' Magnet link or link to a torrent to play via xbmctorrent
-T twitch-channel-name
-D direct http link
```

#Dependencies
* curl(1) is used to make actual JSON RPC requests
* for the "-o" option to work you'll need to install [mps-youtube](https://github.com/np1/mps-youtube)

#Version
1.0
