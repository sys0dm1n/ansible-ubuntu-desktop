#  Ansible Ubuntu setup
- Ansible roles to setup Ubuntu desktop. 
- This playbook is focused on quickly deploying a "ready to use" Ubuntu Desktop.

## Requirements
- Git
- Ansible 2+ (automatically installed from [Ansible offical PPA](https://launchpad.net/~ansible/+archive/ubuntu/ansible) with the provided install.sh script)

---

## Installation

### 1. Install Git and Ansible
First, you need to install Git and Ansible :
```
$ sudo apt-get install git
$ git clone https://github.com/sys0dm1n/ansible-ubuntu-desktop.git
$ cd ansible-ubuntu-desktop
$ bash ./install.sh
```

### 2. Create group_vars/local.yml
Then you need to copy the `group_vars/all.yml` to `group_vars/local.yml` and customize which roles suit your needs. All roles except `locales`,`common`, and `desktop` are disabled by default.

### 3. Run the Playbook "ansible-desktop.yml"
Run `ansible-playbook ansible-desktop.yml --ask-become-pass` 

### 4. Enter the Sudo-Password
xxxxxx

### 5. Optional: User Tags
Optionaly you can run just some of the tags like:
`ansible-playbook ansible-desktop.yml --ask-become-pass --tags=common,locales`

Tags are named the same as role dirs. If a role is in a sub dir then the tag for that specific role is sepparated with a colon like: `aws:cli`. But you can also use `aws` and that should install all the roles under the `aws` dir.


## Roles included

| Role                     | Description|
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                         |**General**|
| common                  | Install a lot of usefull packages (curl, htop, less, zip ... see [corresponding task file](https://github.com/sys0dm1n/ansible-ubuntu-desktop/blob/master/roles/common/tasks/main.yml)) |
| locales                 | Configure system locales and timezone |
| snapd                   | Install [snapd](https://snapcraft.io/about) |
| tlp                     | Install [tlp](https://linrunner.de/tlp/introduction.html) |
| ufw                     | Install [ufw](https://help.ubuntu.com/community/UFW) |
|                         | **Desktop tools** |
| angryipscanner          | Install [AngryIPScanner](https://angryip.org/about/) from [angryip/ipscan Github Repository](https://github.com/angryip/ipscan/releases) |
| atom                    | Install [Atom](https://atom.io/) from [WebUpd8 PPA](https://launchpad.net/~webupd8team/+archive/ubuntu/atom) and [Sync Settings](https://atom.io/packages/sync-settings) plugin  |
| barrier                 | Install [barrier](https://github.com/debauchee/barrier). Use single keyboard and mouse with multiple computers. |
| bitwarden               | Install [bitwarden](https://snapcraft.io/bitwarden) password manager desktop client. |
| chromium                | Install [Chromium](https://www.chromium.org/). May also install plugins and set policies |
| desktop                 | Install a lot of usefull packages (meld, tilda, vlc, xclip) |
| discord                 | Install [Discord](https://discord.com/download) chat app.|
| filezilla               | Install [Filezilla](https://filezilla-project.org/) (no particular settings, basic installation) | 
| firefox                 | Install [Firefox](https://www.mozilla.org/firefox/) (no particular settings, basic installation) | 
| gimp                    | Install [Gimp](https://www.gimp.org/) and some minor settings |
| gitg                    | Install [Gitg](https://wiki.gnome.org/Apps/Gitg) a graphical user interface for git. |
| gnome-encfs-manager     | Install [gnome-encfs-manager](https://moritzmolch.com/apps/gencfsm.html) an easy to use manager and mounter for encfs stashes. |
| gparted                 | Install [Gparted](https://gparted.org/) a free partition editor for graphically managing your disk partitions. |
| guake                   | Install [guake](http://guake-project.org/) a customizable dropdown terminal. |
| indicator-sysmonitor    | Install [indicator-sysmonitor](https://github.com/fossfreedom/indicator-sysmonitor) from [FOSSFreedom PPA](https://launchpad.net/~fossfreedom/+archive/ubuntu/indicator-sysmonitor)                                                                                                                                                   |
| handbrake               | Install [handbrake](https://handbrake.fr/) a video converting tool from nearly any format to a selection of modern, widely supported codecs. |
| kazan                   | Install [kazan](https://launchpad.net/kazam) screencast and screencast tool |
| ledger-live-desktop     | Install [ledger-live-desktop](https://www.ledger.com/ledger-live/download) Ledgers Cryptocurrency Hardware Wallet Desktop application. |
| libreoffice             | Install [LibreOffice](https://www.libreoffice.org/) using [LibreOffice 5.1 PPA](https://launchpad.net/~libreoffice/+archive/ubuntu/libreoffice-5-1) |
| losslesscut             | Install [losslesscut](https://mifi.no/losslesscut/) the Swiss Army Knife of Lossless Video/Audio Editing. |
| nautilus-plugins        | Install Nautilus plugins|
| nextcloud               | Install [nextcloud](https://nextcloud.com/install) Desktop Sync application. |
| noisetorch              | Install [noisetorch](https://github.com/lawl/NoiseTorch) Real-time microphone noise suppression on Linux. |
| Pop!_OS Shell           | Install Pop!_OS Shell Gnome Shell Extension from [Pop!_OS/Shell Github Repository](https://github.com/pop-os/shell) |
| remmina                 | Install [Remmina](http://www.remmina.org/) |
| signal                  | Install [Signal](https://signal.org/) chat application. |
| skype                   | Install [Skype](https://www.skype.com/) |
| slack                   | Install [Slack](https://slack.com/) set of proprietary team collaboration tools and services. |
| solaar                  | Install [Solaar](https://slack.com/) a manager for many Logitech keyboards, mice, and trackpads. |
| sublime3                | Install [Sublime Text 3](https://www.sublimetext.com/3) from [WebUpd8 PPA](https://launchpad.net/~webupd8team/+archive/ubuntu/sublime-text-3) and the [Package Control](https://packagecontrol.io/) plugin   |
| sunflower               | Install [SunFlower](http://sunflower-fm.org/download)fom online dev |
| syncthing               | Install [Syncthing-GTK](https://github.com/kozec/syncthing-gtk) a GUI and notification area icon for Syncthing. |
| teamviewer              | Install [TeamViewer](https://www.teamviewer.com/) from online deb file |
| thunderbird             | Install [Thunderbird](https://www.mozilla.org/thunderbird/) (no particular settings, basic installation) |
| timeshift               | Install [TimeShift](https://github.com/teejee2008/timeshift) |
| winbox                  | Install [Winbox](https://wiki.mikrotik.com/wiki/Manual:Winbox), a small utility that allows administration of MikroTik RouterOS. |
|                         | **Development tools** |
| assh                    | Install [assh](https://github.com/moul/assh) A transparent ssh wrapper that adds yaml configuration and more to SSH |
| awscli                  | Install [aws](https://docs.aws.amazon.com/cli/latest/userguide/installing.html) the Amazon command line interface |
| awsebcli                | Install [eb](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install-linux.html) the Amazon Elastic Beanstalk command line interface |
| awsecscli               | Install [ecs](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ECS_CLI_installation.html) the Amazon Elastic Container Service |
| dbeaver                 | Install [DBeaver](https://dbeaver.io) universal database tool from snap |
| docker                  | Install [Docker](https://www.docker.com/) and Docker compose from Docker deb repository |
| dots                    | Install [dots](https://github.com/EvanPurkhiser/dots) a dotfile Management Tool |
| java/openjdk            | Install Default Java JDK |
| java/openjre            | Install Default Java JRE |
| golang                  | Install go language |
| lens                    | Install [Lens](https://k8slens.dev/) The Kubernetes IDE |
| python                  | Install python language |
| ruby                    | Install ruby language |
| kubectl                 | Install [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl) |
| mysql-workbench         | Install [MySQL WorkBench](https://www.mysql.fr/products/workbench/) from online deb file| 
| minikube                | Install [minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/)  |
| snapd                   | Install [snapd](https://snapcraft.io/snapd) a service that manages installed snaps (app packages for Linux) |
| ssh                     | Install [OpenSSH Server](http://www.openssh.com/) |
| terraform_landscape     | Install [landscape](https://github.com/coinbase/terraform-landscape) a output reformatting tool for `terraform plan` thats easier to read |
| tfenv                   | Install [tfenv](https://github.com/tfutils/tfenv) terraform version manager inspired by rbenv |
| tgenv                   | Install [tgenv](https://github.com/cunymatthieu/tgenv) terragrunt version manager inspired by tfenv |
| tmux                    | Install [tmux](https://github.com/tmux/tmux/wiki) tmux is a terminal multiplexer. It lets you switch easily between several programs in one terminal, detach them (they keep running in the background) and reattach them to a different terminal. And do a lot more. |
| vagrant                 | Install [Vagrant](https://www.vagrantup.com/) from online deb file|
| virtualbox              | Install [VirtualBox](https://www.virtualbox.org/) from VirtualBox APT repositories | 
| zsh                     | Install [zsh](https://www.zsh.org/) shell and [oh-my-zsh](https://ohmyz.sh/) framework for managing your Zsh configuration |

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
