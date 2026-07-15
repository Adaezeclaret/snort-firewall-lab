# Commands Used

This file contains the commands executed during the Snort and Firewall Rules lab.

## 1. Main Terminal (analyst@secOps)

```bash
ping www.cisco.com
```

```bash
sudo ./lab.support.files/scripts/configure_as_dhcp.sh
```

```bash
sudo ./lab.support.files/scripts/cyberops_extended_topo_no_fw.py
```

---

## 2. Mininet CLI

```bash
xterm R1
```

```bash
xterm H5
```

```bash
xterm H10
```

---

## 3. R1 Terminal

Start Snort IDS:

```bash
sudo snort -i R1-eth1 -c /etc/snort/snort.conf
```

Monitor Snort alerts:

```bash
tail -f /var/log/snort/alert
```

---

## 4. H5 Terminal

Generate ICMP traffic:

```bash
ping -c 5 209.165.202.133
```

Capture network packets:

```bash
tcpdump -i H5-eth0 -w nimda.download.pcap &
```

Download the sample file used for testing:

```bash
wget http://209.165.202.133:6666/W32.Nimda.Amm.exe
```

---

## 5. H10 Terminal

Start the malware simulation server:

```bash
./lab.support.files/scripts/mal_server_start.sh
```

Verify listening services:

```bash
netstat -tunpa
```

## 6. Firewall Configuration

Create and apply the firewall rule:

```bash
sudo iptables -I FORWARD
```

List the active firewall rules and verify the rule was added:

```bash
sudo iptables -L -v
```
