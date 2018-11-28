# pt-ui-mods

## How to ensure that updates are received by users

* Update master copies of config files (/etc/....)
* Update postinstall script with version number and 'changed files'- if there is a new version installed by the package, this will back up the old version in ~/oldconfig annd delete the copies in the user directory.

The startlxde-pt script which runs on desktop start, which is also included as part of the ui-mods package, checks to see if a config file in the user directory is missing, and if it is, it copies a clean version from the masters in /etc/

## Mysterious files

As far as Simon at RPi was able to explain, `60desktop-policy` gives the pi user admin privileges. `75source-profile` 'looks as if it makes sure that both system-wide and user profile settings are read, with user profile settings being read after system-wide ones so they will override them if necessary. (I've not fiddled with those files myself, so I might be wrong, but that's what they look like to me...)'