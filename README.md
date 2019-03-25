# Alexa Powered Light Switch

## Requirements
- I needed a simple switch that connected a live wire (common + normally open via relay)
- Most alexa powered switches require a neutral, live, and ground (which I did not have here).
- Wanted to use a relay and spare raspberry pi I had (planning to make a full dashboard later on)

## What I Did

- Used the `fauxmo.py` script (emulates a Belkin WeMo Device)
- Modified the code to tailor to two lights (Office/Cameras) in GPIO Pins (35/37)
- Added a startup script to make sure this always runs
- Connected this in series with a light switch for redundance (I want it to work even if the relay/pi dies)

## Fauxmo
Complete instructions can be found in numerous sources [here is the one](https://github.com/appteur/fauxmo) I liked best.

## Startup Script

1. Make script executable:
```
sudo chmod +x fauxmo.py
```

2. Edit `rc.local` before the `exit 0` (make sure to keep this) 
```
sudo nano /etc/rc.local
```

3. Add Command
```
sudo python /home/pi/alexa-switch/fauxmo.py
```

4. Test it!
```
sudo reboot
```

Expected script to run: <span style="color: white; background: darkgreen; padding: 2px 4px;">Success</span>