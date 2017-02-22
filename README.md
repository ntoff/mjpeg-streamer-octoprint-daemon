mjpeg streamer daemon for octoprint

\_root\_ directory denotes the filesystem root, i.e. "/" and *NOT* the root user's directory.

`cd ~/mjpeg-streamer-octoprint-daemon/_root_`
`sudo cp ./etc/default/webcamd /etc/default/webcamd`
`sudo update-rc.d webcamd defaults`
`sudo cp ./etc/init.d/webcamd /etc/init.d/webcamd`
`sudo chmod +x /etc/init.d/webcamd`
`sudo cp ./bin/webcamd /bin/webcamd`
`sudo chmod +x /bin/webcamd`