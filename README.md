# MoonLite fork of AfterLogic WebMail Lite

AfterLogic WebMail Lite is a free webmail application.

MoonLite is a fat-free fork with cosmetic changes, few presets and various widgets.

While it can be installed manually from repository or ZIP, its primary purpose is to be installed from MoonLite APT repository.

## Installing MoonLite from APT repository

1. Add this to your `/etc/apt/sources.list` file:
```
deb http://apt.moonlyta.com /
```

2. Install a public key:
```
curl -s http://apt.moonlyta.com/moonlite.asc | sudo gpg --no-default-keyring --keyring gnupg-ring:/etc/apt/trusted.gpg.d/moonlite.gpg --import
chmod 644 /etc/apt/trusted.gpg.d/moonlite.gpg
```

3. Update APT cache:
```
apt update
```

4. Install MoonLite:
```
apt install moonlite
```
