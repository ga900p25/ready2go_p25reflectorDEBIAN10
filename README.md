This is ready2go and tested on a DEBIAN10 machine.  27June2024
The binary file 'P25Reflector' was replaced 28July2024 and retested on a DEBIAN 10 VPS. 
1. Create /opt/P25Reflector.

2. Create /var/log/mmdvm

3. Place P25Reflector.ini and P25Reflector in /opt/P25Reflector

4. The file /opt/P25Reflector/P25Reflector is the binary. Use this command to make it executable: chmod +x /opt/P25Reflector/P25Reflector

6. Place p25reflector.service in /lib/systemd/system

7. Edit /opt/P25Reflector/P25Reflector port= as required.  UDP41000 is normally correct. 

8. Start the service: systemctl start p25reflector

9. Check it and make sure it's operating correctly.  Connect to it with a p25gateway from a spot or repeater, use ps -ax, 
or netstat -unap and/or systemctl status p25reflector to confirm it is running normally.
Example:
# systemctl status p25reflector
● p25reflector.service - P25 Reflector Service
   Loaded: loaded (/lib/systemd/system/p25reflector.service; disabled; vendor preset: enabled)
   Active: active (running) since Mon 2024-07-29 14:36:52 EDT; 14s ago
  Process: 6716 ExecStartPre=/bin/sh -c echo "Starting P25Reflector: [`date +%T.%3N`]" >> /var/log/netcheck (code=exite
 Main PID: 6719 (P25Reflector)
    Tasks: 2 (limit: 1093)
   Memory: 604.0K
   CGroup: /system.slice/p25reflector.service
           └─6719 /opt/P25Reflector/P25Reflector /opt/P25Reflector/P25Reflector.ini

Jul 29 14:36:52 'servername' systemd[1]: Starting P25 Reflector Service...
Jul 29 14:36:52 'servername' systemd[1]: Started P25 Reflector Service.
NOTE: The service is running manually but disabled and will not yet run automatically. 

11. Assuming it is operating, let us enable the service so it starts automatically in future; systemctl enable p25reflector

Use at your own risk.  Good luck, W4NOC
