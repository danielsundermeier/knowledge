# Bash

## Links

- [Bash scripting cheatsheet](https://devhints.io/bash)
- [DevOps Bash Tools](https://github.com/HariSekhon/DevOps-Bash-tools)
- [Bash script tutorial](https://www.devopsroles.com/bash-script/)
- [critic.sh](https://github.com/Checksum/critic.sh) - Dead simple testing framework for Bash with coverage.
- [The Linux Command Handbook](https://www.freecodecamp.org/news/the-linux-commands-handbook/)
- [Advanced Bash-Scripting Guide](https://tldp.org/LDP/abs/html/)
- [How to Use Bash Alias](https://www.shell-tips.com/bash/alias/)
- [The Complete How To Guide of Bash Functions](https://www.shell-tips.com/bash/functions/)
- [Learning Modern Linux](https://modern-linux.info/) - Handbook for the Cloud Native Practitioner.
- [The 50 Most Popular Linux & Terminal Commands](https://www.youtube.com/watch?v=ZtqBQ68cfJc)
- [The Arch Linux Handbook](https://www.freecodecamp.org/news/how-to-install-arch-linux/)
- [How to Search for Files from the Linux Command Line](https://www.freecodecamp.org/news/how-to-search-for-files-from-the-linux-command-line/)

## Snippets

### Dateien älter als X Tage

Alle .json Dateien, die älter als 7 Tage sind finden

```
find /var/www/share/default/htdocs/agrirouter/mqtt/backup -name "*.json" -type f -mtime +7
```

und löschen

```
find /var/www/share/default/htdocs/agrirouter/mqtt/backup -name "*.json" -type f -mtime +7 -delete
```

[How to Delete Files Older than 30 days in Linux](https://tecadmin.net/delete-files-older-x-days/)

### Symlink

```
ln -s /path/to/file /path/to/symlink
```

```
ln -sf /path/to/file /path/to/symlink
```

### Print Working directory

```
pwd
```

### Change Driectory

```
cd - // Zum letzen Ordner
```

### Rechte

#### Dateien

- r: lesen
- w: schreiben
- x: ausführen

#### Ordner

- r: lesen
- w: Dateien löschen, erstellen
- x: Ordner öffnen (cd dir)

