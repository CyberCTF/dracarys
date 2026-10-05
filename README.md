# DRACARYS (Game of Active Directory)

The DRACARYS lab by [Orange Cyberdefense](https://github.com/Orange-Cyberdefense/GOAD): one domain on two Windows Server 2025 machines, and an Ubuntu machine.
This repository runs it with [Isoloom](https://www.isoloom.com): [`isoloom.yml`](isoloom.yml)
describes the machines (on GOAD's own boxes), and GOAD's own Ansible playbooks build the lab from
a controller.

## Run it

```bash
isoloom generate
cd .isoloom/vagrant && vagrant up
```

About 7.8 GB of memory (`isoloom resources`) plus 1 GB for the controller. Lab guide: the
[GOAD documentation](https://orange-cyberdefense.github.io/GOAD/).

**Tested:** built end to end on VirtualBox (two Windows Server 2025 servers and an Ubuntu 24.04
member, plus the controller), 0 failed tasks: the domain, the member server, the Linux realm
join, and GOAD's vulnerabilities. The Windows Server 2025 box answers WinRM over HTTPS
(`winrm: ssl` in the spec).

## Licence

GPL-3.0, as GOAD ([LICENSE](LICENSE)). This lab is deliberately vulnerable: keep it isolated.
