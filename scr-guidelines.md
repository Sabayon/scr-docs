# SCR Guidelines

This page describes the Sabayon Community Repositories (SCR) Guidelines, how to add a package to SCR, which packages are eligible, and the process for adding a package.

## Packaging Workflow

With the creation of SCR Repositories, the internal Sabayon workflow has changed. The Gentoo overlays used to generate Sabayon packages, namely “for-gentoo” and “sabayon-distro”, will now just contain ebuilds that are just pertinent to Gentoo and Sabayon. Packages that are not in portage won’t get a spot in Entropy, and are more suitable for inclusion in the SCR.

The SCR tools leverage Portage Overlays for user contributed ebuilds. This means ebuilds don't need to be forked and constantly maintained by the Sabayon developers for inclusion in Sabayon. New versions can be built and made available automatically.

The SCR uses a specification for what to build, and where the ebuilds come from. Little prior experience is required to build new packages.

## Eligible Packages

Packages that are eligible for the SCR:
* Are not available in the Gentoo Portage tree.
* Are available in layman overlays.
* Require a specific combination of USE flags that cannot be put in the official Entropy repositories.

This flow diagram should help illustrate where a package belongs, and how to get it there:
![SCR Workflow](scr-workflow.png)

## Repositories

### Community Repository

The Community Repository is the main repository made available through the SCR. It is intended to be suitable for all users and contains general packages requested by the community. You can enable this repository with the following commands:

    enman add community
    equo update community

### Special Purpose Repositories

These repositories contain packages to satisfy a particular purpose and that are not suitable for inclusion in the "community" repository. These should be enabled with care, and only if you need the specific functionality they provide.

Example special purpose repositories:
* "devel": Contains live versions of core Sabayon packages, and can be used to develop future Sabayon improvements against upstream projects, such as the Calamares installer, or the Linux Kernel.
* "gaming-live": Contains bleeding edge graphics drivers which may add new features or hardware support but may contain bugs or cause crashes.
* "kde-unstable": Contains the very latest KDE packages, which haven't gone through the same level of QA as you would find for KDE versions made available via Entropy.
* "pentesting": Contains various pentesting packages, mostly from [pentoo overlay](https://github.com/pentoo/pentoo-overlay/)

## Issues and Requests

Requests for new packages, and issues with current packages may be raised in the [SCR Bugzilla](https://bugs.sabayon.org/describecomponents.cgi?product=Community%20Repositories). These requests are handled by the SCR Developers, members of the community with access to the SCR infrastructure.

## Getting Involved

We welcome contributions from the Sabayon community. If you have some changes and would like to make them yourself rather than raising through the bug tracker, please raise a GitHub Pull Request against the relevant repository.

You can test your changes by replicating the state of the infrastructure. This is easy to do using the [community-buildspec](https://github.com/Sabayon/community-buildspec) git repository which defines a Vagrant VM with all the tooling to rebuild repositories. It can also be used for one-off repository builds and more information can be found in the [Contributing to SCR](https://wiki.sabayon.org/index.php?title=HOWTO:_Contributing_to_SCR) wiki article.

