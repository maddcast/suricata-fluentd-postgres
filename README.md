# Install and run suricata
```
cd suricata-installation
bash ./suricata.sh
cd ..
```

# Enable alerts tracking

```
cd track-alerts
docker-compose up -d
```

# Generate events
```
apt install tcpreplay
wget https://redmine.openinfosecfoundation.org/attachments/download/1356/malware.pcap
tcpreplay -i eth0 malware.pcap
```

