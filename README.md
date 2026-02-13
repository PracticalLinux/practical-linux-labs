# Practical Linux Labs

Hands-on Linux labs that run inside a local Ubuntu virtual machine.

These labs are terminal-first and focus on core Linux fundamentals:

* Filesystem navigation
* Users and permissions
* Logs
* Services
* Shell usage
* System debugging

Each lab is self-contained inside `/lab` and includes:

```
README.txt        # Context
OBJECTIVES.txt    # Completion requirements
HINTS.txt         # Optional guidance
SIDE_QUESTS.txt   # Optional exploration
check.sh          # Grading script
```

---

# Supported Platforms

The labs run inside Ubuntu.
The launch method depends on your host system.

---

## Windows / Linux / Intel Mac

**Method:** VirtualBox + Vagrant

### Install

* VirtualBox
* Vagrant

### Run a Lab

```bash
git clone https://github.com/PracticalLinux/practical-linux-labs.git
cd practical-linux-labs/labs/PL-000
vagrant up
vagrant ssh
```

### Reset

```bash
vagrant destroy -f
vagrant up
```

---

## Apple Silicon (M1 / M2 / M3) Mac

VirtualBox does not reliably support x86 Vagrant boxes on ARM Macs.

**Method:** UTM + Ubuntu ARM64

### Setup

1. Install UTM.
2. Create an Ubuntu ARM64 VM (22.04 or 24.04 recommended).
3. Inside the VM:

```bash
sudo mkdir -p /lab
git clone https://github.com/PracticalLinux/practical-linux-labs.git
sudo cp -r practical-linux-labs/labs/PL-000/lab /lab
sudo chmod +x /lab/check.sh
```

Use UTM snapshots to reset the environment.

---

# Lab Layout

Each lab lives in:

```
labs/PL-XXX/
```

Structure:

```
Vagrantfile
provision.sh
lab/
```

Inside the VM:

```
/lab
├── LAB_INFO.txt
├── README.txt
├── OBJECTIVES.txt
├── HINTS.txt
├── SIDE_QUESTS.txt
├── check.sh
└── assets/
```

The only authoritative completion check is:

```bash
/lab/check.sh
```

---

# System Requirements

Recommended:

* 8 GB RAM
* Hardware virtualization enabled
* 10 GB free disk space

VM defaults:

* 2 GB RAM
* 1–2 CPUs

---

# Resetting a Lab

### VirtualBox + Vagrant

```bash
vagrant destroy -f
vagrant up
```

### UTM

* Revert to a snapshot
* Or re-copy `/lab`

---

# Design Principles

These labs are:

* Terminal-first
* Resettable
* Offline-capable
* Exploration-friendly

These labs are not:

* GUI tutorials
* Multiple-choice quizzes
* Browser sandboxes
* Cloud-dependent

---

# Reporting Issues

If something fails, open an issue and include:

* Host OS
* Virtualization method
* Ubuntu version
* Full terminal output
