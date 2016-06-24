---
title: Pivotal Cloud Foundry&reg; Metrics Release Notes
owner: Metrix
---

## Version 1.0.8

## Known Issues
* For applications that do not have any activity in the past 24 hours (which means no app events or http requests have been generated), users will not see any data in the UI. They will also need to refresh their browser after metrics are generated by the use of the app.
* While installing the PCF Metrics tile, the default Resource Config settings for each resource pool may be over-sized for POC/Beta purposes. You may adjust them manually to fit your environment. 
* No direct upgrade path. Operators can delete the installed tile and install the new tile.  This does result in downtime and data loss.