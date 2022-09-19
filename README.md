# kSnarf
kSnarf is a Free and Open Source tool which operates in Linux for Intelligence Gathering with a nod to Data Visualization of any protocol.  The default usage for kSnarf is aimed at Wireless traffic and works with any network card so long as it can drop to Monitor mode at a minimum.

kSnarf has an experimental Bluetooth module called kBlue which leverages the [Ubertooth One](https://greatscottgadgets.com/ubertoothone/).  

Private modules are available upon [request](https://gitter.im/ICSec/kSnarf)  for supporting Ethernet style traffic and other such IDS or IPS type needs.

# Getting started
Install PostgreSQL locally
Modify ./system.conf if nothing else to ensure prop.nic makes sense, by default prop.nic is set to wlan1mon.
```sql
CREATE ROLE root WITH SUPERUSER LOGIN;
ALTER USER root WITH PASSWORD 'idrop';
CREATE DATABASE idrop;
```
```bash
sudo python3 ./kSnarf.py
```
```bash
sudo psql idrop
```
```sql
SELECT * FROM main;
```
