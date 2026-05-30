# Networking Notes

## Check Network
```bash
ip a
```
Identifies:
- Ethernet details
- Wi-Fi details
- Assigned IP addresses
- Interface states
Example Interfaces:
- 'eno1' = Ethernet
- 'wlan0' = Wi-Fi

## Verify Connectivity 
```bash
ping google.com
```
CTRL+C to stop ping, LOL

## SSH to PI time (example ip)
```bash
ssh username@192.168.12.160
```
Upon first time connection, you will be prompted to confirm. 
Future connections require only the PW. 

## To monitor SSH status
```bash
sudo systemctl status sshd
```

## Enable SSH permanently
```bash
sudo systemctl enable --now sshd
```

## VIew Saved Networks
```bash
nmcli device wifi list
```
If you need to download Network Manager Package
```bash
sudo dnf install Network Manager
```
## Connect via nmcli
```bash
nmcli wifi list
```
Connect:
```bash
nmcli device wifi connect "Example" password "Password"
```
Of course, replace the "example" and "Password" with your own. 

## Static IP assign
Example Command: Use your own ipv4 and gateway address
```bash
sudo nmcli connection modify "Example" \ ipv4.addresses 192.168/00 \ ipv4.gateway 192.168 \ ipv4.method manual
```
Apply change:
```bash
sudo nmcli connection up "Example"
```
## Confirm IP change
```bash
ip a
```
