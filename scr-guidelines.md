# SCR Guidelines

This page will describe Sabayon Community Repositories (SCR) Guidelines, how to add a package to SCR, what packages are eligible, and what's the iter of adding a package.

## Packages workflow

With the creation of SCR Repositories, the internal Sabayon workflow did change.
The Gentoo overlays used to generate Sabayon packages, namely “for-gentoo” and “sabayon-distro”, will now just contain ebuilds that are just pertinent to Gentoo and Sabayon. Packages that are not in portage won’t get a spot in
Entropy, but suits better inside SCR.

The SCR mechanisms, leveraging Gentoo Overlays contributed by the users, allows to track packages which definitions are in third-party overlays. The benefit is that the Sabayon Developers don’t have to maintain new packages that
already have a place, avoiding to fork even more definitions that already exist in the wild and are already maintained.

## Testing

You can test your build changes or definitions by replicating the state of the infrastructure. [The Github repository community-buildspec](https://github.com/Sabayon/community-buildspec) contains the specifications of the Build
Server that tracks and compile packages nightly.
More informations can be found [in the wiki article](https://wiki.sabayon.org/index.php?title=HOWTO:_Contributing_to_SCR).

## Eligible Packages

Packages that:

* Are not available in Portage (includes handing crafted ones too)
* A specific combination of USE flags that cannot be put in the official Entropy repositories (but needs to handled carefully, and preferibly not in the "community" repository  
* Are available in laymans overlay **BUT NOT** in Portage

Are eligible to be in the SCR Repositories.

## Community Repository

The Community Repository is the main repository available thru SCR:

    enman add community

Here you can find general packages requested by the community itself. The SCR is a collection of repositories, always remember that repository are user-contributed and feedbacks and issues have to be reported in the [Github issue
system ](https://github.com/Sabayon/community-repositories/issues).
