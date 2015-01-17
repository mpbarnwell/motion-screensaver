# motion-screensaver
Simple script to turn off screensaver upon motion detection through webcam, uses the excellent [motion](http://www.lavrsen.dk/foswiki/bin/view/Motion/WebHome) tool.

## Installation
1. ```sudo apt-get install motion```
2. Edit `/etc/default/motion` and change `start_motion_deamon` to `yes`
3. Replace `/etc/init.d/motion` with modified `motion.init`
4. Edit `/etc/init.d/motion` and replace `USER=bob` with the user who logged into X (the motion deamon needs to run as the same user so it has permissions to stop the screensaver)
5. Update `/etc/motion/motion.conf` with the sample included in this repo
6. Put `disable-screensaver` somewhere sensible and update the path to it in `/etc/motion/motion.conf`
7. ```sudo service start motion```

## TODO
- Create dedicated project that can run along side motion so it doesn't require hacking a bunch of system files
- Figure out how run motion as a dedicated user instead of the currently logged in user
- Add a start screensaver script and update config so when motion event ends, the screensaver will start again

## License
Apache License, Version 2.0