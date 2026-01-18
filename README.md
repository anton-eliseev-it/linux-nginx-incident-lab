# Linux Nginx Incident Troubleshooting Lab

This lab demonstrates practical troubleshooting of common nginx service incidents
encountered in Linux support and NOC environments.

The focus is on identifying root causes using system tools, logs, and service status,
and restoring service availability in a controlled manner.

## Covered Scenarios

- nginx configuration syntax error
- TCP port binding conflict
- Service startup failure analysis
- Log-based incident investigation

## Tools Used

- systemctl
- journalctl
- ss
- nginx -t

## Environment

- OS: Ubuntu Server
- Web server: nginx
- Access: Local console and multiple TTY sessions

All incidents were intentionally reproduced to simulate real-world operational scenarios.
