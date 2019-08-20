# Anleitung Umzug / Migration einer Contao 4.x Installation

1. Datenbank exportieren
2. exportierte Datenbank auf Zielserver importieren
3. Frische `contao-manager.phar.php` herunterladen und in das `/web` - Verzeichnis des Servers legen
4. `parameters.yml`,`config.yml` hochladen `[root]/app/config` und anpassen
5. `localconfig.php`, `langconfig.php`, `dcaconfig.php`auf den Server übertragen bei `[root]/system/config` hochladen
6. Evtl. Contao Erweiterungen 3.x Erweiterungen in das `[root]/system/modules` übertragen
7. `files`, `templates`-Verzeichnis auf den Server übertragen
8. Frische `composer.phar` per ssh herunterladen: `curl -sS https://getcomposer.org/installer | php`
9. `composer.lock`, `composer.json` der lokalen Installation auf den Server ins `[root]`-Verzeichnis laden
10. falls Fehler auftritt: `php composer.phar install --ignore-platform-reqs`
11. `rm -rf var/cache/*`
12. ggf. Cache neu erstellen: `vendor/bin/contao-console cache:clear --no-warmup`
