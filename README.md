#Webcam daemon for OctoPrint

Install OctoPrint and mjpeg streamer as usual https://github.com/foosel/OctoPrint/wiki/Setup-on-a-Raspberry-Pi-running-Raspbian making sure to stick to the directory names outlined in the instructions.

Then to create the auto start daemon for mjpeg-streamer, clone the repository:

    cd ~
    git clone https://github.com/ntoff/mjpeg-streamer-octoprint-daemon
    cd ~/mjpeg-streamer-octoprint-daemon/_root_

Make sure the path to mjpeg streamer in \_root\_/bin/webcamd is correctly set e.g. `MJPGSTREAMER_HOME=/home/pi/mjpg-streamer/mjpg-streamer-experimental` and note this does _not_ include the binary name, only the path to the binary.

Copy the files to their relevant locations, and setting them to be executable:

    sudo cp ./etc/default/webcamd /etc/default/webcamd
    sudo cp ./etc/init.d/webcamd /etc/init.d/webcamd
    sudo cp ./bin/webcamd /bin/webcamd
    sudo chmod +x /etc/init.d/webcamd
    sudo chmod +x /bin/webcamd
    sudo update-rc.d webcamd defaults
    
Once done, the contents of this directory can be removed if one wishes, or kept around for safe keeping.

Webcam service should now auto start on boot and can now be started and stopped via 

    sudo service webcamd start|stop|resetart
    
Optional: Create /boot/octopi.txt and include camera options such as framerate or resolution.

The scripts were taken from here: https://github.com/guysoft/OctoPi/ and slightly modified to fit the paths outlined in the manual OctoPrint install wiki page.

Tested working under raspbian jessie lite and armbian 5.25
