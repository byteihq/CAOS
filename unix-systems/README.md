# UNIX-systems
## UNIX Philosophy
- Usage of plain text for data storage.
- Hierarchical file system.
- Handling devices and some specific kinds of inter-process communication (IPC) as files.
- Employing a huge number of software tools.
- Multiple small, simple and modular programs which can be threaded together via a command-line interpreter using pipes, contrasting to use a single monolithic program which comprises of all the same functionality.
## Operating System Components
1. The Kernel - the only program that can interact to hardware
2. Core Libraries
3. Supplementary Services
4. User Interaction Environment
**Process** - any program instance running in the system
```sh
pstree
```

## The boot process
- Boot loader - privileged
- The Kernel - privileged 
- Init / systemd - first non-privileged process 
  - /usr/lib/systemd/system/ (packets)
  - /run/systemd/system/ (runtime created units)
  - /etc/systemd/system/ (admin created units)


## Services
**Most systems minimum set**
1. **dhclient** - provides a means for configuring one or more network interfaces using the Dynamic Host Configuration Protocol, BOOTP protocol, or if
   these protocols fail, by statically assigning an address.
2. **getty** - controls terminals (try Ctrl+Alt+F1/2/3/4)
3. **sshd** - ssh connection
4. **crond** - execute scheduled commands
5. **ntpd (chronyd)** - synchronise time 
6. **syslogd** - write system logs