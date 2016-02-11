# manydoors doorbot
ManyLabs has a collaborative CoorBot.  No one owns it, we all manage it together, from this page.

Purpose: Record and share tap-in, tap-out actions of members (with a ISO 14443A keyfob/card) and document workspace usage.

## Getting Started
1. Get a keyfob or keycard (if you have one already, you can use it)
2. Add your rfid number and name/alias to https://github.com/jhpoelen/manydoors/blob/master/ids.csv (ask for help if this is hard for you)
3. Tap-in and Tap-out when entering and leaving ManyLabs by placing your keyfob on the inside/outside facing coils on the door.
4. See your enter/exit actions on the Slack Channel

## features

1. use rfid to record entry/exit at the manylabs door.
2. automatically updates ids from this github repo when new ones are available
3. keeps a local event log on the pi
4. posts a enter/exit events on the [#door channel of manylabs slack](https://manylabs.slack.com/archives/door/)

# Code setup/ service maintenance

1. Login to pi (ask for location and access crededitals on Slack)
2. clone github repo using ```git clone https://github.com/jhpoelen/manydoors.git access_control```
3. create symlink to start service ```sudo ln -s /home/pi/rfid/access_control/access_control.conf /etc/init/access_control.conf```
4. restart service using ```sudo service access_control restart```
5. edit crontab for synching github repo ```crontab -e```
6. add ```* * * * * cd /home/pi/rfid/access_control && git pull --rebase```

