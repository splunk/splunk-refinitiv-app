# Splunk App for Refinitiv Market Data system (RTDS)

## Summary

Splunk App for Refinitiv allows financial insituation to monitor the health of their mission critical systems and trading components such as ADS, ADH, ATS, and DACS.

## Detail

This solution is divided into two components. One is collection and another one is app that helps realizes business value to end-user.

Collection mechanism is a Splunk add-on that can be deployed to Universal Forwarders.

App is comprized of dashboards/reports/alerts.

### Components
- Dashboard App: Splunk App for Refinitv
- Input App: Splunk Add-on for Refinitiv
  
### Architecture

- Five Dashboards
  - Overview: This page describes the health/heartbeat of the UF add-on sending the data to Splunk.
    - \# of Hots
    - Per host component data feed over time
    - Services Overview
    - Hosts Overview
  - ads:  BufferUsage, Info, Mounts, Servers, Services, ServicesN, and Users
  - adh:  2x Com Info, Info, Routes, Servers, Services, ServiceUpdates, and sessions
  - ats
    - BU
    - License Info
    - Memory Stats
    - SvrStats - Curr Minute
    - SvrStats - Curr Hour
    - SvrStats - Last Minute
    - SvrStats - Last Hour
    - SvrStats - Since Started
    - Version
    - Web
    - IPC
  - dacs
    - Snkdinfo
    - Transinfo
    - Srvinfo
    - SrvSizes
    - FrmServer
    - FrmWANL
    - Overview
    - Pinginfo
    - ToServer
    - ToWANL
    - UsageCollection

### Refresh Rate 

#### Input/Query
- RTDS Components are queried at ~40 seconds and sent over to Splunk via HEC (HTTP Event Collector).
- Customizable via `inputs.conf`

### Dashboard

> Refresh rates are granular and customizable per panel/tab.
> Default Look back: last 3 minutes look back 
- ADS: `30 seconds to 1 minute` refresh 
- ADH: `30 seconds` refresh
- ATS: `1 minute` refresh  
- DACS: `1 minute` refresh

## Installation

- App should be installed in SHC and Indexer
- Add-on should be deployed in UF with servers where Refinitiv components are installed.

## Troubleshooting

### Search Head

- SPL: `index=* sourcetype=refinitiv:*`

### Input


index=_internal *

## Contact

f d s e [at] splunk { dot } com

## Version History

v1.0
