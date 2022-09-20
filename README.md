# kSnarf
kSnarf operates in Linux for extracting various intelligence correlation data points from the RF spectrum.  Those gathered points can be monitored in real time or for a period of time in the past.

The default usage for kSnarf is aimed at wireless traffic and works with any network card so long as it can drop to monitor mode at a minimum.  [piCopilot](https://github.com/stryngs/piCopilot#lessons-learned-from-tools-like-picopilot) is one such tool leveraging the kSnarf libraries in this manner.

New public modules are added to kSnarf by request or as development takes place.  Current development for kSnarf is focused on [SDR](https://en.wikipedia.org/wiki/Software-defined_radio).

# Public modules
- [802.11](https://en.wikipedia.org/wiki/IEEE_802.11)
- [802.15](https://en.wikipedia.org/wiki/IEEE_802.15)
- [TPMS](https://en.wikipedia.org/wiki/Tire-pressure_monitoring_system)

# Privately available modules upon request
Support for various things such as Ethernet monitoring (802.3), IDS or IPS, **non-root code execution** and so forth may be requested via [chat](https://gitter.im/ICSec/kSnarf).  The room is checked once daily so if you do not receive an instant response please be patient and you should get a reply within 24 hours.

# Recommended, but optional hardware
- [HackRF One](https://greatscottgadgets.com/hackrf/one/)
- [SDR Dongle](https://hackerwarehouse.com/product/rtlsdr/)
- [Ubertooth One](https://greatscottgadgets.com/ubertoothone/)

# Required hardware
- Any 802.11 NIC capable of [Monitor mode](https://en.wikipedia.org/wiki/Monitor_mode)

# Recommended, but optional software
- [Aircrack-ng](https://www.aircrack-ng.org/)

# Getting started
Install PostgreSQL locally
```sql
CREATE ROLE root WITH SUPERUSER LOGIN;
ALTER USER root WITH PASSWORD 'idrop';
CREATE DATABASE idrop;
```

## Getting started with 802.11 ([Scapy](https://github.com/secdev/scapy))
Modify ./system.conf if nothing else to ensure prop.nic makes sense, by default prop.nic is set to wlan1mon.
```bash
sudo python3 ./kSnarf.py
```
```bash
sudo psql idrop
```
```sql
SELECT * FROM main;
```

## Getting started with 802.15 ([Ubertooth One](https://greatscottgadgets.com/ubertoothone/))
```bash
sudo python3 ./kBlue.py
```
```bash
sudo psql idrop
```
```sql
SELECT * FROM blue;
```

## Getting started with TPMS ([rtl_433](https://github.com/merbanan/rtl_433))
The current implementation is a proof of concept which will be classed out and grown as more vendors are verified.
```bash
python3 ./kTpms.py
```
```sql
SELECT * FROM tpms;
```
