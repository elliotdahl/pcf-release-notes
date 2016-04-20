---
title: Pivotal Elastic Runtime&reg; v1.6.0.0 Release Notes
owner: Release Engineering
---
# 1.7.x Patches
None as of 2016-03-31.

# Version 1.7.0 New Features

## Elastic Runtime

Versions 1.7.0 and higher versions of Elastic Runtime consist of these Cloud Foundry versions:

- CF Release version: 232
- Diego version: 0.1467.0
- Garden version: 0.337
- CF MySQL version: 25.2
- etcd version: 45
- Apps Manager release version: 597
 
### Diego completely replaces DEAs

Before you upgrade to Pivotal Cloud Foundry 1.7, you must migrate all apps that are currently running on DEA architecture to run on Diego architecture. Pivotal does not support DEA architecture in Pivotal Cloud Foundry 1.7. You may need to scale up your VMs before migrating applications. More information can be found [here](http://docs-pcf-pre-release.cfapps.io/pivotalcf/customizing/apps-enable-diego.html).

If you have any issues migrating your applications to Diego, please contact [Support]().

### Postgres-to-MySQL migration

Upgrading to 1.7 will include a mandatory migration from postgres to MySQL if you are still using postgres databases. Do not delete postgres databases or scale down to `0` before upgrading. You must upgrade the Pivotal Elastic Runtime tile to 1.6.4 or higher before upgrading to 1.7. For further instructions, please reference the [Upgrading Operations Manager](http://www.docs.pivotal.io/pivotalcf/customizing/upgrading-pcf.html#prepareyourdatabaseandapps) and [Backing Up Pivotal Cloud Foundry&reg;](http://docs.pivotal.io/pivotalcf/customizing/backup-restore/backup-pcf.html) documents.

If you have any issues migrating your databses from postgres to MySQL, please contact [Support]().

### Elastic Runtime Tile UI Changes

The tile has been re-designed in layout to improve the configuration workflow for operators. Several configuration fields have been moved to different sections of the tile. Also, more advanced logic has been implemented for some sections to make configuring complicated networking use cases easier for operators.

### Compiled Releases

Installs and upgrades of Elastic Runtime are now much faster than before, as the installation now makes use of compiled binaries instead of source code.

### Automated Backups

Operators using Pivotal Elastic Runtime can enable automatic backup on S3-compatible blobstores. This feature can be enabled for ERT running AWS, OpenStack, or vSphere.

Please see [this document](http://docs.pivotal.io/pivotalcf/customizing/backup-restore/backup-pcf.html#backup-mysql) for more information.

### Docker Private Registries

Please see [this document](http://docs-pcf-pre-release.cfapps.io/pivotalcf/opsguide/docker-registry.html) for information on Docker Trusted and Private registries.

### Experimental Feature: Route Services
Route Services are a new kind of Marketplace Service that developers can use to apply various transformations to application requests by binding an application’s route to a service instance. Through integrations with service brokers and optionally with the Cloud Foundry routing tier, providers can offer these services to developers with a familiar automated, self-service, and on-demand user experience.

Please see [this document](http://docs.pivotal.io/pivotalcf/services/route-services.html) for more information.


### Experimental Feature: Disk & Memory Overcommit Settings

If your apps do not use the full allocation of disk space and memory set in the <strong>Resource Config</strong> tab, you may want use this feature. These fields control the amount to overcommit disk and memory resources to assign more memory and disk space to each Diego Cell VM.

Please see [this document](http://docs.pivotal.io/pivotalcf/customizing/cloudform-er-config.html#experimental-features) for more information.

### AWS Cloudformation Script Update

You can now specify whether you would like to enable HTTP traffic to port 80 of your ELB if you are setting up an environment in AWS to deploy PCF.

### App Manager White Labeling
Pivotal Cloud Foundry® operators can now visually brand Apps Manager by changing certain text, colors, and images of the interface. Developers will see the customized interface when logging in, creating an account, resetting a password, or using Apps Manager.

Please see [this document](http://docs.pivotal.io/pivotalcf/opsguide/whitelabeling.html) for more information.

##  Identity (aka UAA Server)

### Coarse and Fine-Grained Authorization for Apps and APIs

check with Kevin Huang if he needs SSO release notes

New feature details

### UAA PW Policy Config in ERT

Operators can now specify some password policies in the UAA section of Elastic Runtime, including password length, specific character type requirements, expiration, and maximum password attempts allowed.

Please see [this document](http://doc.pivotal.io/pivotalcf/opsguide/pw-policy.html) for more information.

### UAA SAML features
Please see [this document](http://docs.pivotal.io/pivotalcf/opsguide/auth-sso.html) for more information.

### UAA Token Lifetime Settings
http://docs-pcf-pre-release.cfapps.io/pivotalcf/customizing/pcf-aws-manual-er-config.html#er-auth-config
 
## Logging and Metrics

ask Jim CF Campbell for details on what changed between CF-225 and CF-232


## Buildpacks

ask Danny Rosen for details on what changed between CF-225 and CF-232

New feature details

# Notes