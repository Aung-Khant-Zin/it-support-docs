# Network Connectivity Issues — Troubleshooting Guide

## 1. No Internet Access

**Symptoms:** Browser shows "No Internet" or pages fail to load.

**Steps:**
1. Check if other devices on the same network have internet — isolates device vs network issue
2. Run Windows Network Troubleshooter: `Settings → Troubleshoot → Internet Connections`
3. Release and renew IP address:
   ```
   ipconfig /release
   ipconfig /renew
   ```
4. Flush DNS cache:
   ```
   ipconfig /flushdns
   ```
5. Reset TCP/IP stack:
   ```
   netsh int ip reset
   netsh winsock reset
   ```
6. Restart the router/switch if issue affects multiple devices
7. Check with ISP if full network is down

---

## 2. Wi-Fi Connected But No Internet

**Symptoms:** Device shows Wi-Fi connected but cannot browse.

**Steps:**
1. Ping the default gateway:
   ```
   ipconfig → note Default Gateway → ping <gateway IP>
   ```
2. If gateway responds but no internet → ISP or router issue
3. Forget and reconnect to the Wi-Fi network
4. Check DNS settings — try setting DNS to `8.8.8.8` (Google) manually
5. Disable and re-enable the Wi-Fi adapter: `Device Manager → Network Adapters`
6. Update Wi-Fi driver if issue persists

---

## 3. Cannot Connect to VPN

**Symptoms:** VPN client fails to connect or disconnects frequently.

**Steps:**
1. Confirm internet connection is working before attempting VPN
2. Check VPN credentials — ensure username/password are correct and not expired
3. Try connecting from a different network (e.g. mobile hotspot) to rule out firewall blocking
4. Check if VPN client software is up to date
5. Restart VPN client and try again
6. Check with IT admin if VPN server is down or if user account has VPN access
7. Review firewall/antivirus settings — some block VPN ports (UDP 1194, TCP 443)

---

## 4. Slow Network / High Latency

**Symptoms:** Network is connected but very slow, video calls drop, file transfers are slow.

**Steps:**
1. Run a speed test at `fast.com` or `speedtest.net` — compare to expected speeds
2. Check if other users on the same network are affected
3. Ping a known host to check latency:
   ```
   ping google.com -t
   ```
4. Check for bandwidth-heavy applications running in background (Windows Update, cloud sync)
5. Connect via ethernet cable instead of Wi-Fi if possible
6. Check switch/router for errors — escalate to network team if infrastructure issue suspected

---

## 5. DNS Resolution Failures

**Symptoms:** Websites won't load by name but work by IP address.

**Steps:**
1. Test DNS resolution:
   ```
   nslookup google.com
   ```
2. Flush DNS cache:
   ```
   ipconfig /flushdns
   ```
3. Change DNS server to `8.8.8.8` (Google) or `1.1.1.1` (Cloudflare) temporarily
4. Check if internal DNS server is reachable (for domain-joined machines)
5. Escalate to network/server team if internal DNS is unresponsive

---

*Last updated: July 2026*
