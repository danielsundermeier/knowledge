# MacOS

- [Lightweight clipboard manager for macOS](https://github.com/p0deje/Maccy)
- [Can select text from middle of link's text by holding down alt while you drag and select with the mouse](https://twitter.com/MBoffin/status/1218668903586394112)
- [Defaults](https://macos-defaults.com/#%F0%9F%99%8B-what-s-a-defaults-command)

## Setup

- [osx_bootstrap.sh](https://gist.github.com/codeinthehole/26b37efa67041e1307db)

## Zsh

- [Zsh](https://github.com/nikitavoloboev/knowledge/blob/5206fcdfa83dcbccc04de33975a23b9d22f82bbe/unix/shell/zsh/zsh.md)

## Homebrew

- Brewfile in $USER/.dotfiles

- [Homebrew's new feature: Brewfiles](https://coderwall.com/p/afmnbq/homebrew-s-new-feature-brewfiles)
- Brewfile von Github installieren?
- [Brewfiles](https://brewfile.info/)

### Update

```
brew upgrade && brew update
```

Fehermeldung 
`Error: Directory not empty @ dir_s_rmdir - /usr/local/Cellar/dnsmasq/2.84`

```
sudo rm -rf /usr/local/Cellar/dnsmasq/2.84
```

### Installierte Programme

```
brew ls
```

### Fehler

```
brew doctor
```

### Services

```
brew services
brew services start [service]
brew services stop [service]
brew services restart [service]
brew services restart --all
```

### MariaDB

Wenn mysql nach
```
brew upgrade
```
nicht mehr geht:

```
mysqld
cd /usr/local/var/mysql
rm ib_logfile0
rm ib_logfile1 
```

### PHP Versionen

```
brew unlink php@7.1
$ brew link php@7.4 --force --overwrite
```

[Switching between PHP versions when using Homebrew](https://localheinz.com/blog/2020/05/05/switching-between-php-versions-when-using-homebrew/)

## Nix

- [How I Start: Nix (2020)](https://christine.website/blog/how-i-start-nix-2020-03-08) ([Lobsters](https://lobste.rs/s/lktf6u/how_i_start_nix))

## Hackintosh

- [How to Build a Hackintosh](https://www.freecodecamp.org/news/build-a-hackintosh/)
