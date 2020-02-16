# What this overlay is about

This overlay does not provide ebuilds but profiles optimized for creation of container images.

# How to use this overlay

[Local overlays](https://wiki.gentoo.org/wiki/Overlay/Local_overlay) should be managed via `/etc/portage/repos.conf/`.
To enable this overlay make sure you are using a recent Portage version (at least `2.2.14`), and create a `/etc/portage/repos.conf/container-profiles.conf` file containing precisely:

```
[container-profiles]
location = /usr/local/portage/container-profiles
sync-type = git
sync-uri = https://github.com/stefan-langenmaier/container-profiles.git
priority=9999
```

Or read the instructions on the [Gentoo Wiki](http://wiki.gentoo.org/wiki/Layman#Adding_custom_repositories).

# Configuration

After performing those steps, the following should work (or any other package from this overlay):

	PORTAGE_CONFIGROOT=/var/my-portage-configroot eselect profile list
	PORTAGE_CONFIGROOT=/var/my-portage-configroot eselect profile set container/amd64
