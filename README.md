# rCommander packages for apt and dnf

The signed apt and dnf repositories of [rCommander](https://rcommander.net), a two-panel file
manager with terminals, SSH and SFTP, for x86-64 and arm64. Served at <https://degoya.github.io/rcommander-packages>.

Debian and Ubuntu:

```bash
sudo install -d -m 0755 /etc/apt/keyrings
curl -fsSL https://degoya.github.io/rcommander-packages/rcommander-packages.asc | sudo tee /etc/apt/keyrings/rcommander-packages.asc > /dev/null
curl -fsSL https://degoya.github.io/rcommander-packages/rcommander.sources | sudo tee /etc/apt/sources.list.d/rcommander.sources > /dev/null
sudo apt update
sudo apt install rcommander
```

Fedora:

```bash
sudo curl -fsSL -o /etc/yum.repos.d/rcommander.repo https://degoya.github.io/rcommander-packages/rcommander.repo
sudo dnf install rcommander
```

`apt upgrade` and `dnf upgrade` then install every new release; rCommander installed this way does
not replace itself, and its update window shows that command. The repository indexes and the rpm
packages are signed with the key `56CCFFDA649CC1654735885048F16D81F44CB87E`; compare it with the fingerprint dnf shows on
the first install, or with `gpg --show-keys /etc/apt/keyrings/rcommander-packages.asc`. The last
3 versions of each package stay here for a downgrade (`apt install rcommander=<version>`,
`dnf downgrade rcommander`).

The files are written by the release workflow of
[degoya/rCommander](https://github.com/degoya/rCommander) with every release - issues and changes go
there, not here. The handbook's installation page:
<https://github.com/degoya/rCommander/wiki/installation>.
