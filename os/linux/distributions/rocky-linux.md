# Rocky Linux Cheat Sheet

## System Commands

| Command | Description |
|---------|-------------|
| sudo dnf update | Update package lists and upgrade packages |
| sudo dnf install [package] | Install a package |
| sudo dnf remove [package] | Remove a package |
| sudo reboot | Reboot the system |
| sudo shutdown -h now | Shutdown the system |
| systemctl [start/stop/restart] [service] | Manage system services |

## File Management

| Command | Description |
|---------|-------------|
| ls | List directory contents |
| cd [directory] | Change directory |
| mkdir [directory] | Create a directory |
| rm [file] | Remove a file |
| rm -r [directory] | Remove a directory |
| cp [source] [destination] | Copy files/directories |
| mv [source] [destination] | Move/rename files/directories |

## User Management

| Command | Description |
|---------|-------------|
| sudo useradd [username] | Add a new user |
| sudo userdel [username] | Delete a user |
| sudo passwd [username] | Change user password |
| groups [username] | Show user's groups |
| sudo usermod -aG [group] [username] | Add user to a group |

## System Information

| Command | Description |
|---------|-------------|
| uname -a | Display system information |
| cat /etc/rocky-release | Display Rocky Linux version |
| df -h | Show disk space usage |
| free -h | Display memory usage |
| top | Show running processes |

## Network

| Command | Description |
|---------|-------------|
| ip addr | Display network interfaces |
| ping [host] | Send ICMP echo request |
| ss -tuln | List open ports |
| firewall-cmd --list-all | Check firewall status |
| firewall-cmd --add-port=[port]/[protocol] | Open a port in firewall |

## Package Management

| Command | Description |
|---------|-------------|
| dnf search [package] | Search for a package |
| dnf info [package] | Show package details |
| rpm -qa | List installed packages |
| dnf clean all | Clean DNF caches |

## SELinux

| Command | Description |
|---------|-------------|
| getenforce | Get SELinux mode |
| setenforce [0/1] | Set SELinux mode (permissive/enforcing) |
| sestatus | Get SELinux status |

## Tips
- Use Tab for command auto-completion
- Use Ctrl+R to search command history
- Use `dnf history` to view and undo package operations

## Additional Resources
- [Rocky Linux Documentation](https://docs.rockylinux.org/)
- [Rocky Linux Forums](https://forums.rockylinux.org/)
