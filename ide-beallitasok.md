# IDE beállítások – Windsurf (VSCode)

## Bevezető

A fejlesztői munkához a Windsurf IDE-t használom, amely a népszerű [Visual Studio Code](https://code.visualstudio.com/) (VSCode) alapjaira épül, de számos beépített mesterséges intelligencia (AI) funkcióval bővítve. A Windsurf IDE lehetőséget ad AI-alapú kódolási asszisztensek, automatikus kódgenerálás, hibakeresés és egyéb fejlett funkciók használatára, amelyek jelentősen gyorsítják és támogatják a fejlesztési folyamatot.

Fontos megjegyezni, hogy a Visual Studio Code-ban is elérhető már az Agent mód (beépített AI asszisztens), amely lehetővé teszi AI-alapú kódolási támogatás használatát közvetlenül a VSCode-ban is. Így a dokumentációban ismertetett AI-funkciók egy része natívan elérhető a VSCode-ban is, nem csak a Windsurf IDE-ben.

A dokumentációban ismertetett beállítások és kiegészítők szinte kivétel nélkül használhatóak a hagyományos Visual Studio Code-ban is, így nem szükséges feltétlenül Windsurf IDE-t használni, ha csak a VSCode funkcióira van szükséged.

A Windsurf IDE ingyenesen is használható, de a teljes értékű AI funkciókhoz (pl. prémium modellek, fejlett asszisztensek) előfizetés szükséges. Ingyenes módban is elérhetőek alapvető funkciók, így mindenki kipróbálhatja az IDE-t.

**Alternatíva:**
A fenti IDE-k mellett érdemes megemlíteni a [Cursor IDE](https://www.cursor.com/) nevű fejlesztői környezetet is, amely szintén a VSCode alapjaira épül, és erősen AI-integrált funkciókat kínál. A Cursor IDE-t is érdemes kipróbálni, ha modern, AI-alapú fejlesztői környezetet keresel.

**Letöltési és információs linkek:**
- [Windsurf IDE hivatalos oldal és letöltés](https://windsurf.com/)
- [Visual Studio Code hivatalos oldal és letöltés](https://code.visualstudio.com/)
- [Cursor IDE hivatalos oldal és letöltés](https://www.cursor.com/)

Ebben a részben összegyűjtöm a Windsurf IDE (VSCode alapú) beállításaimat, profilokra bontva.

## Bevezető

A különböző fejlesztési technológiákhoz (pl. PHP, Javascript/Typescript) külön profilokat használok a Windsurf/VSCode-ban. Ez lehetővé teszi, hogy minden projektben a legmegfelelőbb kiegészítők és beállítások legyenek aktívak, így gyorsabban és hatékonyabban tudok dolgozni.

## Tartalomjegyzék
- [Általánosan használt kiegészítők](#altalanosan-hasznalt-kiegeszitok)
- [PHP fejlesztési profil](#php-fejlesztes-profil)
- [Javascript/Typescript fejlesztési profil](#javascripttypescript-fejlesztesi-profil)

---

## Általánosan használt kiegészítők
Ezeket a kiegészítőket mindkét profilban, minden projekthez használom:
- Kanagawa Color Theme (`metaphore.kanagawa-vscode-color-theme`)
- CodeSnap (kódrészlet screenshot) (`adpyke.codesnap`)
- Color Highlight (színek kiemelése kódban) (`naumovs.color-highlight`)
- Material Icon Theme (fájl ikonok) (`pkief.material-icon-theme`)
- Material Product Icons (fájl ikonok) (`pkief.material-product-icons`)
- Gitmoji Commit (emojik commit üzenetekhez) (`seatonjiang.gitmoji-vscode`)
- Docker (Docker támogatás) (`ms-azuretools.vscode-docker`)
- Thunder Client (REST API tesztelés) (`rangav.vscode-thunder-client`)
- Bookmarks (kódbeli könyvjelzők) (`alefragnani.bookmarks`)
- Mermaid Editor (diagram szerkesztő) (`tomoyukim.vscode-mermaid-editor`)
- Snippets Manager (snippetek kezelése) (`zjffun.snippetsmanager`)
- TODO Tree (TODO-k vizuális kezelése) (`gruntfuggly.todo-tree`)
- WakaTime (kódolási statisztika) (`wakatime.vscode-wakatime`)
- Custom Background (egyéni háttér) (`shalldie.background`)
- WhichKey (billentyűparancs súgó) (`vspacecode.whichkey`)
- Database Client JDBC (`cweijan.dbclient-jdbc`)
- Database Client 2 (adatbázis kliens) (`cweijan.vscode-database-client2`)
---

## Profilok

### PHP fejlesztés profil
- **Leírás:**
  Ez a profil minden olyan projekthez használatos, ahol PHP fejlesztés, Laravel vagy WordPress alapú munka, illetve általános webes backend fejlesztés a feladat. A környezet célja a gyors, kényelmes kódolás, hibakeresés és tesztelés.

- **Használt kiegészítők (az általánosan használt kiegészítők mellett):**
  - PHP Composer (Composer integráció) (`devsense.composer-php-vscode`)
  - PHP Tools for VSCode (haladó PHP támogatás, intellisense, debug) (`devsense.phptools-vscode`)
  - PHP Resolver (import resolver, autocompletion) (`stoildobreff.php-resolver`)
  - SFTP (távoli fájlok kezelése) (`natizyskunk.sftp`)

- **Fontosabb beállítások, külső programok telepítése:**
  - A fejlesztői környezetben lokálisan telepíteni kell a PHP-t és a Composer-t.
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



### Javascript/Typescript fejlesztés profil
- **Leírás:** Mikor és mire használom ezt a profilt.
- **Használt kiegészítők:**
  - CodeSnap (kódrészlet screenshot) (`adpyke.codesnap`)
  - PHPStorm Theme (`ericgomez.phpstorm-theme`)
  - Color Highlight (színek kiemelése kódban) (`naumovs.color-highlight`)
  - Material Product Icons (fájl ikonok) (`pkief.material-product-icons`)
  - Gitmoji Commit (emojik commit üzenetekhez) (`seatonjiang.gitmoji-vscode`)
  - Docker (Docker támogatás) (`ms-azuretools.vscode-docker`)
  - Material Icon Theme (fájl ikonok) (`pkief.material-icon-theme`)
  - Thunder Client (REST API tesztelés) (`rangav.vscode-thunder-client`)
  - PHP Composer (Composer integráció) (`devsense.composer-php-vscode`)
  - PHP Tools for VSCode (haladó PHP támogatás, intellisense, debug) (`devsense.phptools-vscode`)
  - Kanagawa Color Theme (`metaphore.kanagawa-vscode-color-theme`)
  - PHP Resolver (import resolver, autocompletion) (`stoildobreff.php-resolver`)
  - Custom Background (`shalldie.background`)
  - HTML CSS Support (`ecmel.vscode-html-css`)
  - SFTP (távoli fájlok kezelése) (`natizyskunk.sftp`)
  - WhichKey (billentyűparancs súgó) (`vspacecode.whichkey`)
  - Bookmarks (kódbeli könyvjelzők) (`alefragnani.bookmarks`)
  - Database Client JDBC (`cweijan.dbclient-jdbc`)
  - Database Client 2 (adatbázis kliens) (`cweijan.vscode-database-client2`)
  - Mermaid Editor (diagram szerkesztő) (`tomoyukim.vscode-mermaid-editor`)
  - Snippets Manager (snippetek kezelése) (`zjffun.snippetsmanager`)
  - TODO Tree (TODO-k vizuális kezelése) (`gruntfuggly.todo-tree`)
  - WakaTime (kódolási statisztika) (`wakatime.vscode-wakatime`)

- **Fontosabb beállítások:**
  - (Speciális settings, snippets, workspace settings)

## Általános beállítások

- **Globális Windsurf/VSCode beállítások:**
  - (Ami mindkét profilban közös)
- **Hasznos billentyűparancsok:**
  - (Saját shortcutok)
- **Téma, kinézet:**
  - (Színséma, ikonok)
