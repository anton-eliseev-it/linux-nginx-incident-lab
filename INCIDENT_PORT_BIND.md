# Incident: TCP Port 80 Already in Use

## Description

nginx failed to start because TCP port 80 was already occupied by another process.

This scenario simulates a common production issue where multiple services compete
for the same network port.

## Symptoms

- nginx service failed to start
- systemctl reported startup failure
- journalctl showed bind() error

## Investigation

1. Checked service status:
   systemctl status nginx

2. Reviewed detailed logs:
   journalctl -xeu nginx.service

3. Identified error message:
   bind() to 0.0.0.0:80 failed (98: Address already in use)

4. Verified port usage:
   ss -tulpn | grep :80

5. Identified conflicting process occupying port 80

## Root Cause

Another process was already listening on TCP port 80, preventing nginx from binding
to the required port.

## Resolution

- Stopped the conflicting process
- Restarted nginx service
- Verified successful service startup

## Lessons Learned

- Port ownership is controlled by the kernel, not by service names
- journalctl is essential for diagnosing service startup failures
- ss is a reliable tool for identifying port conflicts
