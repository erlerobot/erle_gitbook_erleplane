# Telemetry

Telemetry is the highly automated communications process by which measurements are made and other data collected at remote or inaccessible points and transmitted to receiving equipment for monitoring.

Drones generally include a radio frequency link that is used for telemetry and Ground Control Station communications. APM (the autopilot software) allows several ways of communication:
- serial port, generally used together with a [Telemetry Radio](http://copter.ardupilot.com/wiki/3dradio/).
- UDP socket
- TCP socket

Erle-copter can use either a Telemetry radio (serial port) or a USB WiFi dongle (UDP, TCP sockets).