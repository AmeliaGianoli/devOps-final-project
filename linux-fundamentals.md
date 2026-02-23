# Linux Fundamentals
## Basic Commands
### File/Directory Management:
| Command        | Description                                  |
|---------------|----------------------------------------------|
| `ls`          | List files                                   |
| `ls -la`      | Detailed list including hidden files         |
| `cd /path`    | Change directory                             |
| `pwd`         | Show current directory                       |
| `mkdir dir`   | Create directory                             |
| `rm file`     | Remove file                                  |
| `rm -r dir`   | Remove directory recursively                 |
| `cp src dest` | Copy file                                    |
| `mv src dest` | Move/rename file                             |
| `cat file`     | View file contents       |
| `less file`    | Scroll through file      |
| `head file`    | First 10 lines           |
| `tail file`    | Last 10 lines            |
| `tail -f file` | Follow log output        |
| `nano file`    | Edit file                |
| `vim file`     | Edit file (advanced)     |
### Permissions:
| Command         | Description              |
|----------------|--------------------------|
| `chmod 755 file`       | Change permissions |
| `chown user:group file`| Change owner |
### Networking:
| Command            | Description              |
|-------------------|--------------------------|
| `ip addr`         | Show IP addresses        |
| `ip link`         | Show interfaces          |
| `ip route`        | Show routing table       |
| `ping host`       | Test connectivity        |
| `curl url`        | HTTP request             |
| `wget url`        | Download file            |
| `ss -tulpn`       | Show listening ports     |
| `traceroute host` | Trace network path       |
