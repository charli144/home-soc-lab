## Goal
Deploy Wazuh SIEM on Ubuntu Server.

## Environment
- OS: Ubuntu Server 24.04
- Network: Host-only + NAT

## Steps Taken
1. Configured dual NIC networking
2. Fixed IPv4 DHCP issues via netplan
3. Installed enterprise CA certificate
4. Ran Wazuh installer with OS override

## Issues Encountered
- NAT interface down
- IPv6 preferred over IPv4
- HTTPS interception breaking curl

## Resolution
- Forced IPv4 DHCP
- Imported Techloq root CA
- Verified TLS trust before install

## Evidence
See screenshots in `/screenshots/02-wazuh-install`
