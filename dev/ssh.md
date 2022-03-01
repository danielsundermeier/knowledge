# SSH

## Erstellen

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

### Legacy

```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

## Kopieren

```
cat ~/.ssh/id_rsa.pub | pbcopy
cat ~/.ssh/id_ed25519.pub | pbcopy
```

- [How to view your SSH keys in Linux, macOS, and Windows](https://www.techrepublic.com/article/how-to-view-your-ssh-keys-in-linux-macos-and-windows/)

## PATH

anzeigen
```
echo $PATH
```

erweitern
```
export PATH=/usr/local/sbin:$PATH >> ~/.zshrc
```

## Links

- [How to ssh properly](https://gravitational.com/blog/how-to-ssh-properly/)
- [How to properly manage ssh keys for server access](https://www.paepper.com/blog/posts/how-to-properly-manage-ssh-keys-for-server-access/)