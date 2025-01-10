archiso-media-kiosk-profile
---

Using archiso to make a reproducible media centre installation on a flash drive. (This is a `profile` directory.)

Comes up and launches Kodi once display and network exist.

Killing Kodi launches Firefox, and vice versa.

(SSH is also available (with an intentionally stupid root password) in case something goes weird.)


external dependencies
---

An sfdisk script is used after each dd installation to (re)create a partition (a safe distance from the bootable area) mounted as the kodi user's home directory for persistent storage on the same drive.
The Firefox profile also gets stored here.

This is [declared as a systemd mount](./airootfs/etc/systemd/system/var-lib-kodi.mount); it has to exist `Before` Kodi will start.
