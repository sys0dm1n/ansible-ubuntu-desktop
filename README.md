# Ansible Ubuntu setup
Ansible roles to setup Ubuntu desktop. This playbook is focused on quickly deploying a "ready to use" Ubuntu Desktop.


## Requirements
- Git
- Ansible 2+ (automatically installed from [Ansible offical PPA](https://launchpad.net/~ansible/+archive/ubuntu/ansible) with the provided install.sh script)


## Installation
First, you need to install Git and Ansible :
```
sudo apt-get install git
git clone https://github.com/sys0dm1n/ansible-ubuntu-desktop.git
cd ansible-ubuntu
./install.sh
```

Then you need to customize the playbook `ansible-desktop.yml` (or create a new one) to suit your needs. All roles are disabled by default.

Run `ansible-playbook ansible-desktop.yml --ask-become-pass` and enter your sudo password to run the playbook

## Roles included

| Role                     | Description|
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                                   |**General**|
| common                   | Install a lot of usefull packages (curl, htop, less, zip ... see [corresponding task file](https://github.com/sys0dm1n/ansible-ubuntu-desktop/blob/master/roles/common/tasks/main.yml)) |
| locales                  | Configure system locales and timezone |
| java-openjdk             | Install Default Java JDK|
|                               | **Desktop tools** |
| atom                     | Install [Atom](https://atom.io/) from [WebUpd8 PPA](https://launchpad.net/~webupd8team/+archive/ubuntu/atom) and [Sync Settings](https://atom.io/packages/sync-settings) plugin  |
| chromium                 | Install [Chromium](https://www.chromium.org/). May also install plugins and set policies       |
| dbeaver                  | Install [DBeaver](http://dbeaver.jkiss.org/) from online deb file |
| desktop                  | Install a lot of usefull packages (meld, tilda, vlc, xclip)|
| filezilla                | Install [Filezilla](https://filezilla-project.org/) (no particular settings, basic installation) | 
| firefox                  | Install [Firefox](https://www.mozilla.org/firefox/) (no particular settings, basic installation) | 
| gimp                     | Install [Gimp](https://www.gimp.org/) and some minor settings |
| indicator-sysmonitor     | Install [indicator-sysmonitor](https://github.com/fossfreedom/indicator-sysmonitor) from [FOSSFreedom PPA](https://launchpad.net/~fossfreedom/+archive/ubuntu/indicator-sysmonitor)                                                                                                                                                   |
| libreoffice     | Install [LibreOffice](https://www.libreoffice.org/) using [LibreOffice 5.1 PPA](https://launchpad.net/~libreoffice/+archive/ubuntu/libreoffice-5-1) |
| mysql-workbench          | Install [MySQL WorkBench](https://www.mysql.fr/products/workbench/) from online deb file| 
| nautilus-plugins         | Install Nautilus plugins|
| remarkable               | Install [Remarkable](https://remarkableapp.github.io/linux.html) from online deb file|
| remmina                  | Install [Remmina](http://www.remmina.org/) |
| shutter                  | Install [Shutter](http://shutter-project.org/) screenshot tool |
| skype                    | Install [Skype](https://www.skype.com/)    |
| sublime3                 | Install [Sublime Text 3](https://www.sublimetext.com/3) from [WebUpd8 PPA](https://launchpad.net/~webupd8team/+archive/ubuntu/sublime-text-3) and the [Package Control](https://packagecontrol.io/) plugin   |
| sunflower                | Install [SunFlower](http://sunflower-fm.org/download)fom online dev|
| teamviewer               | Install [TeamViewer](https://www.teamviewer.com/) from online deb file|
| thunderbird              | Install [Thunderbird](https://www.mozilla.org/thunderbird/) (no particular settings, basic installation) |
| vagrant                  | Install [Vagrant](https://www.vagrantup.com/) from online deb file|
| virtualbox               | Install [VirtualBox](https://www.virtualbox.org/) from VirtualBox APT repositories | 
| vokoscreen               | Install [Vokoscreen](http://www.kohaupt-online.de/hp/) screencast tool|
|                               | **Services & server tools** |
| docker                   | Install [Docker](https://www.docker.com/) and Docker compose from Docker deb repository|
| kubectl| Install [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl)  |
| minikube                   | Install [minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/)  |
| python                   | Install [Python](https://www.python.org/)  |
| ssh                      | Install [OpenSSH Server](http://www.openssh.com/)      | 
|ufw                   | Install [ufw](https://help.ubuntu.com/community/UFW) |
