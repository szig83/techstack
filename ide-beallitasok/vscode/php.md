# PHP fejlesztés profil

## Leírás
Ez a profil minden olyan projekthez használatos, ahol PHP fejlesztés, Laravel vagy WordPress alapú munka, illetve általános webes backend fejlesztés a feladat. A környezet célja a gyors, kényelmes kódolás, hibakeresés és tesztelés.

## Használt kiegészítők (az általánosan használt kiegészítők mellett):

- PHP Composer (Composer integráció) (`devsense.composer-php-vscode`)
- PHP Tools for VSCode (haladó PHP támogatás, intellisense, debug) (`devsense.phptools-vscode`)
- PHP Resolver (import resolver, autocompletion) (`stoildobreff.php-resolver`)
- SFTP (távoli fájlok kezelése) (`natizyskunk.sftp`)

## Fontosabb beállítások, külső programok telepítése

A fejlesztői környezetben lokálisan telepítettem a PHP-t és a Composer-t.

- A Composer működéséhez szükséges, hogy a PHP is telepítve legyen a gépen.
- A Composer többek között olyan kódstandard ellenőrző eszközök (pl. phpcs, php-cs-fixer) telepítését könnyíti meg + a projecteken belüli csomagok telepítését is.
- A Composer-t én macOS rendszeren, a Homebrew csomagkezelő segítségével telepítettem globálisan, így bármelyik projektben elérhető.
- A telepítéshez a következő parancsot használtam:
```sh
brew install composer
```
- A globális telepítés lépései és részletes leírása megtalálható a hivatalos dokumentációban: [Composer globális telepítése](https://getcomposer.org/doc/00-intro.md#globally)
- Windows rendszerre vonatkozó telepítési információk itt találhatók: [Composer telepítése Windowsra](https://getcomposer.org/doc/00-intro.md#using-the-installer)
- A "PHP Resolver" kiegészítő alapértelmezett működéséhez ezeket globálisan telepítem Composerrel:
```sh
composer global require "squizlabs/php_codesniffer=*"
composer global require "friendsofphp/php-cs-fixer"
```

> **Megjegyzés:**
  > Ahhoz, hogy ezek a parancsok és a globálisan telepített csomagok mindenhol elérhetők legyenek, hozzá kell adni a Composer telepítési útvonalát és a Composer által globálisan telepített csomagok `bin` mappáját a rendszer PATH környezeti változójához.
  >
  > **macOS:**
  > - A Composer globális bin mappája általában: `$HOME/.composer/vendor/bin` (régi), illetve újabb verzióknál: `$HOME/.config/composer/vendor/bin`.
  > - Ezt hozzáadhatod a PATH-hoz például a következő sorral a `~/.zshrc` vagy `~/.bash_profile` fájlban:
  >   ```sh
  >   export PATH="$HOME/.config/composer/vendor/bin:$PATH"
  >   ```
  > - Mentsd el a fájlt, majd futtasd: `source ~/.zshrc` vagy nyiss új terminált.
  >
  > **Windows:**
  > - A Composer globális bin mappája általában: `%USERPROFILE%\AppData\Roaming\Composer\vendor\bin`
  > - Ezt a mappát hozzá kell adni a rendszer PATH környezeti változójához a Gépház → Rendszer → Névjegy → Speciális rendszerbeállítások → Környezeti változók menüpontban.
  > - Újraindítás vagy új terminál megnyitása után a parancsok már elérhetők lesznek mindenhol.

### Settings file a PHP fejlesztési profilhoz

A PHP fejlesztési profilhoz tartozó egyéni VSCode/Windsurf profilbeállításokat ebben a fájlban találod: [`configs/Php.code-profile`](configs/Php.code-profile). Ez a profil file tartalmaz minden speciális beállítást és workspace konfigurációt, amelyet a PHP-s projektekhez használok.

## Profilok

- [Általános beállítások (minden profilban közös)](altalanos.md)
- [Javascript/Typescript fejlesztési profil](js-ts.md)