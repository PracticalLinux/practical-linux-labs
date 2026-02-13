# Practical Linux Labs

Hands-on Linux labs designed to run inside a local Ubuntu virtual machine.

These labs are terminal-first and focus on real Linux fundamentals:

Filesystem navigation

Users and permissions

Logs

Services

Shell usage

System debugging

Each lab is self-contained inside /lab and includes:

README.txt – context

OBJECTIVES.txt – completion requirements

HINTS.txt – optional guidance

check.sh – grading script

Supported Platforms

The labs run inside Ubuntu. The method used to launch Ubuntu depends on your host system.

Windows / Linux / Intel Mac

Recommended method: VirtualBox + Vagrant

Install:

VirtualBox

Vagrant

Then:

git clone https://github.com/PracticalLinux/practical-linux-labs.git
cd practical-linux-labs/labs/PL-000
vagrant up
vagrant ssh


To reset a lab:

vagrant destroy -f
vagrant up

Apple Silicon (M1 / M2 / M3) Mac

VirtualBox does not reliably support x86 Vagrant boxes on ARM Macs.

Recommended method: UTM + Ubuntu ARM64

Install UTM.

Create an Ubuntu ARM64 VM (22.04 or 24.04 recommended).

Inside the VM:

sudo mkdir -p /lab
git clone https://github.com/PracticalLinux/practical-linux-labs.git
sudo cp -r practical-linux-labs/labs/PL-000/lab /lab
sudo chmod +x /lab/check.sh


Use UTM snapshots to reset the environment when needed.

Lab Structure

Each lab lives in:

labs/PL-XXX/


Inside each lab:

Vagrantfile
provision.sh
lab/


Inside /lab (in the VM):

LAB_INFO.txt
README.txt
OBJECTIVES.txt
HINTS.txt
SIDE_QUESTS.txt
check.sh
assets/


The only authoritative completion check is:

/lab/check.sh

Requirements

Minimum host requirements:

8 GB RAM recommended

Hardware virtualization enabled

~10 GB free disk space

The VM itself typically uses:

2 GB RAM

1–2 CPUs

What These Labs Are

Terminal-first

Resettable

Designed for repetition

Built to encourage exploration

Offline-capable

What These Labs Are Not

GUI tutorials

Multiple-choice quizzes

Browser-based sandboxes

Cloud-dependent

Resetting a Lab

VirtualBox + Vagrant:

vagrant destroy -f
vagrant up


UTM:

Revert to a snapshot

Or re-copy /lab

Notes

The grading script checks system state. It does not track time or activity.

Hidden files and side quests are optional.

Labs are provider-agnostic; the transport method does not change lab behavior.

If you encounter issues specific to a virtualization provider, open an issue and include:

Host OS

Virtualization method

Ubuntu version

Full terminal output
