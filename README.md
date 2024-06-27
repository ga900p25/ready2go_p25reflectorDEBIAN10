This is ready2go and tested on a DEBIAN10 machine.  
Create /opt/P25Reflector.
Create /var/log/mmdvm
Place P25Reflector.ini and P25Reflector in /opt/P25Reflector
/opt/P25Reflector/P25Reflector is the binary executable.  chmod +x /opt/P25Reflector/P25Reflector
Place p25reflector.service in /lib/systemd/system
Edit /opt/P25Reflector/P25Reflector port= as required.  UDP41000 is normally correct. 
Start the service: systemctl start p25reflector
Check it and make sure it's operating correctly.  Connect to it with a p25gateway from a spot or repeater, use ps -ax, 
or netstat -unap and/or systemctl status p25reflector to confirm it is running normally.
Assuming it is operating, let us enable the service so it starts automatically in future; systemctl enable p25reflector
Use at your own risk.  Good luck, W4NOC
