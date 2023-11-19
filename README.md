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
- installer automatically adds a local mail server entry.
  
**NB:** you can modify the widgets themselves as they're preserved upon version upgrades. They're stored in `content` subdirectory and served via `/mlite/content` alias - which works whether you have MoonLite installed to domain root or to subdirectory.

While MoonLite can be installed manually, its primary purpose is to be installed from MoonLite APT repository. It's designed to work with Apache, PHP 8 and MySQL and will install the components as dependencies if necessary.

## Installing MoonLite from APT repository

1. Add this to your `/etc/apt/sources.list` file:
```
deb http://apt.mooncats.ru /
```

2. Install a public key:
```
curl -s http://apt.mooncats.ru/moonlite.asc | sudo gpg --no-default-keyring --keyring gnupg-ring:/etc/apt/trusted.gpg.d/moonlite.gpg --import
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

The package and repository are built with [this tool here](https://github.com/igor-moonlite/apt-build).

## Installing MoonLite from ZIP package

1. Download the package at https://mooncats.ru/download/moonlite.zip

2. For fresh installation, extract the package to web directory. Make sure webserver is able to write in data subdirectory.

3. For upgrade, backup `data` subdirectory; if you made any changes to `content` you may wish to backup as well. Delete the installation, extract the package and restore from backup.

4. In web browser, navigate to `/adminpanel/`, default login is superadmin, with an empty password.

## CHANGELOG
### 19 Nov 2023
* TruckersMP clock is now fully autonomous, no longer requires web requests

### 18 Nov 2023
* Builder of packages and repository substantially revised due to MoonFile release

### 17 Nov 2023
* Header icon location & size revised
* .htaccess file restored

### 16 Nov 2023
* Desktop notification icon update
* Adminpanel favicon update
* Mailserver is now added with Sieve features enabled
* Repository signing key reissued

### 6 Nov 2023
* Primary domain changed

### 4 Nov 2023
* Fixed issue with locking package versions in composer.json
* Russian translation update, pushed to upstream
* Wallpaper update
* Moved away from Jino mail, localhost mailserver is now added

### 29 Oct 2023
* Added widgets on login screen
* TruckersMP clock improved
* Enabled address book management

## TODO
* Autoreload of weather widget (say, once every 30 min)
* Make widgets more configurable
* Radio with station switcher
* Configure password change, probably reset too
* Mailserver-bundled package
* Simpler Calendar module, without authentication, but with user-defined URL
* Research "upcoming events" for Calendar
