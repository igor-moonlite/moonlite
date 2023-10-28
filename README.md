# MoonLite

[AfterLogic WebMail Lite](https://afterlogic.org/webmail-lite) is a free webmail application.

MoonLite is a fat-free fork of AfterLogic WebMail Lite:
- removed modules I personally do not require
- removed all the languages except for Russian and English
- removed minified JavaScript code
- enabled a number of advanced features
- added Google Calendar integration via adapted [IFrame App](https://github.com/afterlogic/aurora-module-webclient-iframe-app)
- added widgets for time, weather and radio player
- custom theme with own background and icons
- installer automatically adds mail server entry for the use with [Jino email hosting](https://jino.ru/).
  
**NB:** you can modify the widgets themselves as they're preserved upon version upgrades. They're stored in `content` subdirectory and served via `/mlite/content` alias - which works whether you have MoonLite installed to domain root or to subdirectory.

While MoonLite can be installed manually from repository or ZIP, its primary purpose is to be installed from MoonLite APT repository. It's designed to work with Apache, PHP 8 and MySQL and will install the components as dependencies if necessary.

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

## TODO
* improve widgets structure, with some added on login screen
* improve Russian translations and push them to upstream
* Files feature, either original from Afterlogic or custom, ownCloud-compatible one
