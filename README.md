# Ansible Ubuntu setup
Ansible roles to setup Ubuntu desktop. This playbook is focused on quickly deploying a "ready to use" Ubuntu Desktop.


## Requirements
- Git
- Ansible 2+ (automatically installed from [Ansible offical PPA](https://launchpad.net/~ansible/+archive/ubuntu/ansible) with the provided install.sh script)


## Installation
First, you need to install Git and Ansible :
```
$ sudo apt-get install git
$ git clone https://github.com/sys0dm1n/ansible-ubuntu-desktop.git
$ cd ansible-ubuntu-desktop
$ bash ./install.sh
```

Then you need to copy the `group_vars/all.yml` to `group_vars/local.yml` and customize which roles suit your needs. All roles except `locales`,`common`, and `desktop` are disabled by default.

Run `ansible-playbook ansible-desktop.yml --ask-become-pass` and enter your sudo password to run the playbook

Optionaly you can run just some of the tags like:
`ansible-playbook ansible-desktop.yml --ask-become-pass --tags=common,locales`

Tags are named the same as role dirs. If a role is in a sub dir then the tag for that specific role is sepparated with a colon like: `aws:cli`. But you can also use `aws` and that should install all the roles under the `aws` dir.

## Roles included

| Role                     | Description|
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                         |**General**|
| common                  | Install a lot of usefull packages (curl, htop, less, zip ... see [corresponding task file](https://github.com/sys0dm1n/ansible-ubuntu-desktop/blob/master/roles/common/tasks/main.yml)) |
| locales                 | Configure system locales and timezone |
| golang                  | Install go language |
| java-openjdk            | Install Default Java JDK |
| python                  | Install python language |
| ruby                    | Install ruby language |
|                         | **Desktop tools** |
| atom                    | Install [Atom](https://atom.io/) from [WebUpd8 PPA](https://launchpad.net/~webupd8team/+archive/ubuntu/atom) and [Sync Settings](https://atom.io/packages/sync-settings) plugin  |
| chromium                | Install [Chromium](https://www.chromium.org/). May also install plugins and set policies       |
| dbeaver                 | Install [DBeaver](http://dbeaver.jkiss.org/) from snap |
| desktop                 | Install a lot of usefull packages (meld, tilda, vlc, xclip)|
| filezilla               | Install [Filezilla](https://filezilla-project.org/) (no particular settings, basic installation) | 
| firefox                 | Install [Firefox](https://www.mozilla.org/firefox/) (no particular settings, basic installation) | 
| gimp                    | Install [Gimp](https://www.gimp.org/) and some minor settings |
| indicator-sysmonitor    | Install [indicator-sysmonitor](https://github.com/fossfreedom/indicator-sysmonitor) from [FOSSFreedom PPA](https://launchpad.net/~fossfreedom/+archive/ubuntu/indicator-sysmonitor)                                                                                                                                                   |
| lens                    | Install [Lens](https://k8slens.dev/) The Kubernetes IDE |
| kazan                   | Install [kazan](https://launchpad.net/kazam) screencast and screencast tool|
| libreoffice             | Install [LibreOffice](https://www.libreoffice.org/) using [LibreOffice 5.1 PPA](https://launchpad.net/~libreoffice/+archive/ubuntu/libreoffice-5-1) |
| mysql-workbench         | Install [MySQL WorkBench](https://www.mysql.fr/products/workbench/) from online deb file| 
| nautilus-plugins        | Install Nautilus plugins|
| Pop!_OS Shell           | Install Pop!_OS Shell Gnome Shell Extension from [Pop!_OS/Shell github repository](https://github.com/pop-os/shell) |
| remmina                 | Install [Remmina](http://www.remmina.org/) |
| skype                   | Install [Skype](https://www.skype.com/)    |
| slack                   | Install [Slack](https://slack.com/) set of proprietary team collaboration tools and services.   |
| sublime3                | Install [Sublime Text 3](https://www.sublimetext.com/3) from [WebUpd8 PPA](https://launchpad.net/~webupd8team/+archive/ubuntu/sublime-text-3) and the [Package Control](https://packagecontrol.io/) plugin   |
| sunflower               | Install [SunFlower](http://sunflower-fm.org/download)fom online dev|
| teamviewer              | Install [TeamViewer](https://www.teamviewer.com/) from online deb file|
| thunderbird             | Install [Thunderbird](https://www.mozilla.org/thunderbird/) (no particular settings, basic installation) |
| timeshift               | Install [TimeShift](https://github.com/teejee2008/timeshift) |
| tmux                    | Install [tmux](https://github.com/tmux/tmux/wiki) tmux is a terminal multiplexer. It lets you switch easily between several programs in one terminal, detach them (they keep running in the background) and reattach them to a different terminal. And do a lot more. |
| vagrant                 | Install [Vagrant](https://www.vagrantup.com/) from online deb file|
| virtualbox              | Install [VirtualBox](https://www.virtualbox.org/) from VirtualBox APT repositories | 
|                         | **Services & server tools** |
| assh                    | Install [assh](https://github.com/moul/assh) A transparent ssh wrapper that adds yaml configuration and more to SSH |
| awscli                  | Install [aws](https://docs.aws.amazon.com/cli/latest/userguide/installing.html) the Amazon command line interface |
| awsebcli                | Install [eb](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install-linux.html) the Amazon Elastic Beanstalk command line interface |
| awsecscli               | Install [ecs](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ECS_CLI_installation.html) the Amazon Elastic Container Service |
| dots                    | Install [dots](https://github.com/EvanPurkhiser/dots) a dotfile Management Tool |
| docker                  | Install [Docker](https://www.docker.com/) and Docker compose from Docker deb repository |
| kubectl                 | Install [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl) |
| terraform_landscape     | Install [landscape](https://github.com/coinbase/terraform-landscape) a output reformatting tool for `terraform plan` thats easier to read |
| tfenv                   | Install [tfenv](https://github.com/tfutils/tfenv) terraform version manager inspired by rbenv |
| tgenv                   | Install [tgenv](https://github.com/cunymatthieu/tgenv) terragrunt version manager inspired by tfenv |
| minikube                | Install [minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/)  |
| snapd                   | Install [snapd](https://snapcraft.io/snapd) a service that manages installed snaps (app packages for Linux) |
| ssh                     | Install [OpenSSH Server](http://www.openssh.com/) |
| ufw                     | Install [ufw](https://help.ubuntu.com/community/UFW) |
| zsh                     | Install [zsh](https://www.zsh.org/) shell and [oh-my-zsh](https://ohmyz.sh/) framework for managing your Zsh configuration |

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
