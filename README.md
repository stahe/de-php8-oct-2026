# Einführung in PHP 8 anhand von Beispielen

📖 **Das Tutorial lesen: [https://stahe.github.io/de-php8-oct-2026/](https://stahe.github.io/de-php8-oct-2026/)**

Dieser Kurs vermittelt die Sprache [PHP](https://www.php.net) 8.5 **anhand von Beispielen**: über 300 PHP-Dateien, zeilenweise kommentiert und mit ihren Ausführungsergebnissen. Er beginnt mit den Grundlagen der Sprache und führt bis zu Webservices und einer MVC-Webanwendung.

Es ist die Neufassung des Kurses [Einführung in PHP 7 anhand von Beispielen](https://stahe.github.io/de-php7-juillet-2019/) (2019) für PHP 8: derselbe Aufbau, dieselben Beispiele, derselbe rote Faden, aber mit aktuellem Code. Zwischen PHP 7 und PHP 8.5 sind viele Funktionen **veraltet** (deprecated): Der Code dieses Kurses verwendet **keine** davon. Alle Skripte wurden mit PHP 8.5 ausgeführt, das so konfiguriert ist, dass es alles meldet (`error_reporting = E_ALL`): In ihren Ausgaben erscheinen keine `Deprecated`-Meldungen.

| PHP-7-Kurs (2019) | PHP-8-Kurs (2026) |
|---|---|
| PHP 7.3 | PHP 8.5 |
| NetBeans | VS Code + PHP Intelephense |
| Codeception | PHPUnit 12 |
| Postman | curl |
| SwiftMailer, hMailServer | Symfony Mailer, Mailpit |
| `imap_*`-Funktionen (in 8.4 aus dem PHP-Kern entfernt) | mit Sockets geschriebene POP3-/IMAP-Clients |
| dynamische Eigenschaften, Getter/Setter | typisierte Eigenschaften, `readonly`, Constructor Property Promotion |
| `switch`, Klassenkonstanten | `match`, Enumerationen (`enum`) |
| `PDO::MYSQL_ATTR_*` (in 8.5 veraltet) | `PDO::connect()`, `Pdo\Mysql`, `Pdo\Pgsql` |
| `deny from all` (Apache 2.2) | ein Verzeichnis `public/` und `Require all denied` (Apache 2.4) |

## Kursgliederung

| Kapitel | Inhalt |
|---|---|
| Installation | Laragon 8 (PHP 8.5, Apache, MySQL, PostgreSQL, Redis), VS Code, Composer |
| PHP-Grundlagen | Variablen, strikte Typisierung, Arrays, Zeichenketten, Funktionen (benannte Argumente, `match`, Arrow Functions, Pipe-Operator `\|>` aus PHP 8.5), Textdateien, JSON |
| Klassen, Schnittstellen | typisierte Attribute, Constructor Promotion, `readonly`, Property Hooks und asymmetrische Sichtbarkeit (PHP 8.4), Enumerationen, `#[\Override]`, `clone` mit Änderungen (PHP 8.5), Intersection Types |
| Ausnahmen und Fehler | die `Throwable`-Hierarchie in PHP 8, in Ausnahmen umgewandelte Warnungen von PHP 7 |
| Traits, Schichtenanwendungen | Code-Wiederverwendung; Architektur [DAO] / [Geschäftslogik] / [Konsole] |
| Tests | PHPUnit 12: Data Provider über Attribute, erwartete Ausnahmen |
| Datenbanken | PDO mit MySQL 8 und PostgreSQL: Prepared Statements, Transaktionen |
| Netzwerkfunktionen | TCP, HTTP, SMTP, POP3, IMAP, zunächst mit Sockets und dann mit Bibliotheken umgesetzt |
| Webservices | dynamische Seiten, JSON, GET-/POST-Parameter, Sitzungen, Authentifizierung, HTTPS |
| XML | SimpleXML und die neue API `Dom\XMLDocument` in PHP 8.4 |

## Der rote Faden: ein Einkommensteuerrechner in 13 Versionen

Im Verlauf des Kurses bauen wir Version für Version einen **Einkommensteuerrechner** auf:

- **Versionen 1 und 2**: ein Skript, Funktionen, Textdateien und JSON;
- **Version 3**: Klassen; **Version 4**: eine Schichtenarchitektur, getestet mit PHPUnit;
- **Versionen 5 bis 7**: Steuerdaten in einer MySQL-Datenbank, dann in PostgreSQL, dann in einer von beiden;
- **Versionen 8 bis 11**: ein Webservice und sein Konsolenclient: Authentifizierung, Sitzungen, Logging, E-Mail-Benachrichtigungen an den Administrator bei Fehlern, Redis-Cache, Antworten in JSON und dann in XML;
- **Version 12**: eine **MVC**-Webanwendung, die Antworten in JSON, XML oder HTML (Bootstrap 5) liefert, mit einem Konsolenclient für den JSON-Dienst;
- **Version 13**: Sicherheit der Anwendungsdateien (nur der Ordner `public/` ist aus dem Web sichtbar).

## Technologien

PHP 8.5 · Apache 2.4 · MySQL 8.4 · PostgreSQL · Redis · Composer · PHPUnit 12 · Symfony HttpFoundation 8 · Symfony HttpClient 8 · Symfony Mailer 8 · Predis 3 · zbateson/mail-mime-parser 3 · Mailpit · Bootstrap 5 · Laragon 8 · VS Code

## Voraussetzungen

- Vorherige Programmiererfahrung in einer beliebigen Sprache.
- Windows und [Laragon](https://laragon.org) 8 (enthält PHP 8.5, Apache, MySQL, PostgreSQL, Redis und Composer), [VS Code](https://code.visualstudio.com) und seine PHP-IntelliSense-Erweiterung. Installationsanleitungen finden sich am Anfang des Kurses.

## Autor

Dieser Kurs und sein Code wurden von **Claude**, der KI von [Anthropic](https://www.anthropic.com) (Oktober 2026), im Auftrag von Serge Tahé geschrieben, auf der Grundlage seines PHP-7-Kurses von 2019.
