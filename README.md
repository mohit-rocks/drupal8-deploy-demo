# Installation
Pre-configured Drupal 8 setup with deploy, relaxed and related module configuration
Demo consists of two independant sites.

Hub site works as source of information and Satellite site consumes content from the hub site.

Currently, both the sites are having their own config directory and independant setup.

## Setup Hub
- Goto "hub" directory
- lando setup
- lando composer install
- Install drupal with existing configuration
- Create new users with the "Replicator" role.

## Setup Satellite
- Goto "satellite" directory
- lando setup
- lando composer install
- Install drupal with existing configuration
- Create new users with the "Replicator" role.

## Configuration
- Once users are created for both the site, we need to add satellite site on the Hub site.
- Satellite site will consume content from the hub site.
- Goto http://hub.lndo.site/admin/config/services/relaxed
- Add new remote. Provide full URL as "http://satellite.lndo.site/relaxed" and replicate username and passwords created on the satellite site.
- After creating remote, run cron so it will get the satellite site's workspaces.
- Update workspace (http://hub.lndo.site/admin/structure/workspace/1/edit) to point to satellite site's workspace.
- Enable "recipe" module to get the paragraph type and content types to evalute paragraphs support for the deploy.

## Video
- https://www.youtube.com/watch?v=ibBX2cHdhu8
