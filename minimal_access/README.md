# Topology

![image](./images/topology1.jpg)

# LibreSBC

* Node: sbc02
* Public ip: XX.XX.XX.XX
* Internet DNS: sbc02.sample.com
* Private ip: 10.101.8.2
* Access User Directory: 1005-1009

## Config

![image](./images/config.jpg)

# PBX(FreeSWITCH)

* Using defaut configuration
* Default account: 1000-1019
* Internal: 10.101.7.2
* Internal DNS: freeswicth02.sample.com

### test internal call between ext 1000 and 1001

* It is ok.

# How to

Here are some summary steps need to be done on LibreSBC

1. Define cluster node, netalias
2. Define 2 SIP profile 1 for public and 1 for private
3. Define Media Class, Capacity Class
4. For Private IP (libresbc) ----> Private IP (FreeSWITCH as a PBX). = libreapi/interconnection/outbound + libreapi/base/gateway
5. Routing Table: /libreapi/routing/table with action=route and routes=<outbound-connection-in-step-4>
6. For Public-IP (User) ---> Public IP (libresbc) = libreapi/interconnection/inbound

# access config

* access_domain.json
* access_service.json
