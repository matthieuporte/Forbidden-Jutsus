
`pacman` is the package management utility for Arch Linux and its derivatives. It is used to install, upgrade, and manage software packages in an Arch Linux system.

---

### Update package databases
   This command synchronizes the local package database with the remote repositories. The `-Sy` flags ensure that both the package list and the package databases are updated.
```bash
sudo pacman -Sy
```

Alternatively you can upgrade all installed packages to their latest versions :

```bash
sudo pacman -Syu
```


### Install a program

```shell
sudo pacman -S program name
```


### Search for a package

Search remote repositories for packages:
   ```bash
   pacman -Ss search_term
   ```

Search locally for installed packages.
   ```bash
   pacman -Qs search_term
   ```

### Remove a package
   ```bash
   sudo pacman -R package_name
   ```

To remove a package along with its dependencies run :

   ```bash
   sudo pacman -Rs package_name
   ```

### Clean package cache
This command removes old and uninstalled packages from the package cache, helping to free up disk space.
   ```bash
   sudo pacman -Sc
   ```
   
