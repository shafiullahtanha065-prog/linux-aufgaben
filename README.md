# linux-aufgaben
Aufgaben

[Linux_Aufgaben.html](https://github.com/user-attachments/files/22740632/Linux_Aufgaben.html)
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PuTTY Linux Shell-Aufgaben - Komplette Anleitung</title>
    <style>
        @page {
            size: A4;
            margin: 2cm;
        }
        body {
            font-family: 'Calibri', 'Arial', sans-serif;
            line-height: 1.6;
            max-width: 21cm;
            margin: 0 auto;
            padding: 20px;
            background: white;
            color: #333;
        }
        h1 {
            color: #2c3e50;
            border-bottom: 3px solid #3498db;
            padding-bottom: 10px;
            font-size: 28px;
            text-align: center;
        }
        h2 {
            color: #2980b9;
            margin-top: 30px;
            font-size: 22px;
            border-left: 4px solid #3498db;
            padding-left: 10px;
            background: #ecf0f1;
            padding: 10px 10px 10px 15px;
        }
        h3 {
            color: #16a085;
            font-size: 18px;
            margin-top: 20px;
        }
        .aufgabe {
            background: #ffe6e6;
            padding: 15px;
            margin: 20px 0;
            border-left: 5px solid #e74c3c;
            border-radius: 5px;
        }
        .befehl {
            background: #2c3e50;
            color: #2ecc71;
            padding: 12px;
            border-radius: 5px;
            font-family: 'Courier New', monospace;
            margin: 10px 0;
            font-size: 14px;
        }
        .erklaerung {
            background: #d5f4e6;
            padding: 15px;
            margin: 15px 0;
            border-left: 5px solid #27ae60;
            border-radius: 5px;
        }
        .wichtig {
            background: #fff3cd;
            padding: 15px;
            margin: 15px 0;
            border-left: 5px solid #ffc107;
            border-radius: 5px;
            font-weight: bold;
        }
        .tipp {
            background: #e3f2fd;
            padding: 15px;
            margin: 15px 0;
            border-left: 5px solid #2196f3;
            border-radius: 5px;
        }
        .schritt {
            background: #f8f9fa;
            padding: 10px;
            margin: 10px 0;
            border-left: 3px solid #6c757d;
        }
        ul, ol {
            margin-left: 20px;
        }
        li {
            margin: 8px 0;
        }
        table {
            border-collapse: collapse;
            width: 100%;
            margin: 20px 0;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 12px;
            text-align: left;
        }
        th {
            background: #3498db;
            color: white;
        }
        .vi-befehle {
            background: #f0f0f0;
            padding: 10px;
            border: 2px solid #888;
            margin: 10px 0;
        }
        .print-button {
            position: fixed;
            top: 20px;
            right: 20px;
            background: #3498db;
            color: white;
            border: none;
            padding: 12px 24px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
            z-index: 1000;
        }
        .print-button:hover {
            background: #2980b9;
        }
        @media print {
            .print-button {
                display: none;
            }
            body {
                padding: 0;
            }
        }
    </style>
</head>
<body>
    <button class="print-button" onclick="window.print()">📄 Als PDF speichern / Drucken</button>

    <h1>🖥️ PuTTY Linux Shell-Aufgaben</h1>
    <p style="text-align: center;"><strong>Komplette Schritt-für-Schritt Anleitung</strong></p>
    <p style="text-align: center;"><em>Alle Befehle und Erklärungen in einfachem Deutsch</em></p>

    <hr>

    <h2>📚 Wichtige vi-Editor Befehle (für alle Aufgaben)</h2>
    <div class="vi-befehle">
        <table>
            <tr>
                <th>Befehl</th>
                <th>Bedeutung</th>
            </tr>
            <tr>
                <td><strong>i</strong></td>
                <td>In den Eingabemodus wechseln (INSERT)</td>
            </tr>
            <tr>
                <td><strong>ESC</strong></td>
                <td>Eingabemodus verlassen</td>
            </tr>
            <tr>
                <td><strong>:wq</strong></td>
                <td>Speichern und beenden (write + quit)</td>
            </tr>
            <tr>
                <td><strong>:q!</strong></td>
                <td>Beenden ohne speichern</td>
            </tr>
            <tr>
                <td><strong>G</strong></td>
                <td>Ans Ende der Datei springen</td>
            </tr>
            <tr>
                <td><strong>gg</strong></td>
                <td>An den Anfang der Datei springen</td>
            </tr>
            <tr>
                <td><strong>dd</strong></td>
                <td>Aktuelle Zeile löschen</td>
            </tr>
            <tr>
                <td><strong>o</strong></td>
                <td>Neue Zeile einfügen und in INSERT-Modus wechseln</td>
            </tr>
        </table>
    </div>

    <hr>

    <h2>Aufgabe 1: Verzeichnis ~/bin erstellen und cls-Befehl</h2>

    <div class="aufgabe">
        <strong>📝 Aufgabenstellung:</strong>
        <ol>
            <li>Erzeugen Sie das Verzeichnis ~/bin</li>
            <li>Erstellen Sie mit vi die Datei cls mit dem Inhalt: <code>tput clear</code></li>
            <li>Vergeben Sie Ausführungsrecht (execute)</li>
            <li>Wechseln Sie ins HOME-Verzeichnis - Was passiert bei Eingabe von cls?</li>
            <li>Erweitern Sie PATH in .profile um ~/bin</li>
            <li>Melden Sie sich neu an</li>
            <li>Testen Sie cls erneut</li>
        </ol>
    </div>

    <h3>Schritt 1: Verzeichnis ~/bin erstellen</h3>
    <div class="befehl">mkdir ~/bin</div>
    <div class="erklaerung">
        <strong>Was macht dieser Befehl?</strong><br>
        • <code>mkdir</code> = "make directory" = Verzeichnis erstellen<br>
        • <code>~/bin</code> = im HOME-Verzeichnis ein Unterverzeichnis namens "bin"<br>
        • <code>~</code> ist eine Abkürzung für Ihr HOME-Verzeichnis (z.B. /home/v16)
    </div>
    <div class="wichtig">
        ⚠️ Falls die Meldung "File exists" erscheint: Das ist OK! Das Verzeichnis existiert bereits.
    </div>

    <h3>Schritt 2: Datei cls mit vi erstellen</h3>
    <div class="befehl">vi ~/bin/cls</div>
    <div class="schritt">
        <strong>Im vi-Editor:</strong><br>
        1. Drücken Sie: <strong>i</strong> (unten links erscheint -- INSERT --)<br>
        2. Tippen Sie: <strong>tput clear</strong><br>
        3. Drücken Sie: <strong>ESC</strong><br>
        4. Tippen Sie: <strong>:wq</strong> und drücken Sie <strong>Enter</strong>
    </div>
    <div class="erklaerung">
        <strong>Was macht tput clear?</strong><br>
        Dieser Befehl löscht den gesamten Bildschirminhalt im Terminal - wie "cls" unter Windows.
    </div>

    <h3>Schritt 3: Ausführungsrecht vergeben</h3>
    <div class="befehl">chmod +x ~/bin/cls</div>
    <div class="erklaerung">
        <strong>Was macht dieser Befehl?</strong><br>
        • <code>chmod</code> = "change mode" = Rechte ändern<br>
        • <code>+x</code> = "execute" = Ausführungsrecht hinzufügen<br>
        • Macht die Datei zu einem ausführbaren Programm
    </div>

    <h3>Schritt 4: Ins HOME-Verzeichnis wechseln und testen</h3>
    <div class="befehl">cd ~<br>cls</div>
    <div class="erklaerung">
        <strong>Was passiert?</strong><br>
        Sie erhalten eine Fehlermeldung: <code>cls: command not found</code>
    </div>
    <div class="wichtig">
        <strong>Warum funktioniert cls nicht?</strong><br>
        Das Verzeichnis ~/bin ist noch nicht im PATH. Die Shell findet das Programm deshalb nicht.
    </div>

    <h3>Schritt 5: PATH in .profile erweitern</h3>
    <div class="befehl">vi ~/.profile</div>
    <div class="schritt">
        <strong>Im vi-Editor:</strong><br>
        1. Drücken Sie: <strong>G</strong> (springt ans Ende der Datei)<br>
        2. Drücken Sie: <strong>o</strong> (öffnet neue Zeile und startet INSERT-Modus)<br>
        3. Tippen Sie: <strong>PATH=$PATH:~/bin</strong><br>
        4. Drücken Sie: <strong>ESC</strong><br>
        5. Tippen Sie: <strong>:wq</strong> und drücken Sie <strong>Enter</strong>
    </div>
    <div class="erklaerung">
        <strong>Was macht PATH=$PATH:~/bin?</strong><br>
        • PATH ist eine Variable, die alle Verzeichnisse enthält, in denen die Shell nach Programmen sucht<br>
        • $PATH:~/bin bedeutet: "Füge ~/bin zur Liste hinzu"<br>
        • Jetzt kann die Shell Programme in ~/bin finden
    </div>

    <h3>Schritt 6: Sitzung beenden und neu anmelden</h3>
    <div class="befehl">exit</div>
    <div class="erklaerung">
        Loggen Sie sich neu in PuTTY ein, damit die Änderungen in .profile wirksam werden.
    </div>
    <div class="tipp">
        <strong>💡 Alternativ:</strong> Sie können die .profile auch neu laden ohne Abmeldung:<br>
        <code>source ~/.profile</code>
    </div>

    <h3>Schritt 7: cls erneut testen</h3>
    <div class="befehl">cd ~<br>cls</div>
    <div class="erklaerung">
        <strong>✅ Jetzt sollte der Bildschirm gelöscht werden!</strong><br>
        Der Befehl cls funktioniert, weil ~/bin jetzt im PATH ist.
    </div>

    <hr>

    <h2>Aufgabe 2: Datei pass_sort erstellen</h2>

    <div class="aufgabe">
        <strong>📝 Aufgabenstellung:</strong><br>
        Erzeugen Sie in ~/daten eine Datei pass_sort mit dem Inhalt der Datei /etc/passwd, sortiert nach der Gruppennummer.
    </div>

    <h3>Lösung:</h3>
    <div class="befehl">sort -t: -k4 -n /etc/passwd > ~/daten/pass_sort</div>

    <div class="erklaerung">
        <strong>Befehl erklärt:</strong><br>
        • <code>sort</code> = Sortierbefehl<br>
        • <code>-t:</code> = Trennzeichen ist Doppelpunkt (in /etc/passwd sind Felder durch : getrennt)<br>
        • <code>-k4</code> = sortiere nach dem 4. Feld (Gruppennummer steht an 4. Stelle)<br>
        • <code>-n</code> = numerische Sortierung (nicht alphabetisch)<br>
        • <code>/etc/passwd</code> = Quelldatei (enthält alle Benutzer)<br>
        • <code>></code> = leite Ausgabe in Datei um<br>
        • <code>~/daten/pass_sort</code> = Zieldatei
    </div>

    <div class="tipp">
        <strong>💡 Was steht in /etc/passwd?</strong><br>
        Jede Zeile enthält Informationen über einen Benutzer, getrennt durch Doppelpunkte:<br>
        <code>benutzername:x:UID:GID:vollername:home:shell</code><br>
        Das 4. Feld (GID) ist die Gruppennummer.
    </div>

    <hr>

    <h2>Aufgabe 3: Verzeichnisse sortieren</h2>

    <div class="aufgabe">
        <strong>📝 Aufgabenstellung:</strong>
        <ol>
            <li>Zeigen Sie ~/daten nach Größe aufsteigend sortiert an</li>
            <li>Zeigen Sie ~/daten nach Größe absteigend sortiert an</li>
        </ol>
    </div>

    <h3>Lösung 1: Aufsteigend sortiert (kleine Dateien zuerst)</h3>
    <div class="befehl">ls -lSr ~/daten</div>
    <div class="erklaerung">
        • <code>ls</code> = "list" = Verzeichnisinhalt anzeigen<br>
        • <code>-l</code> = lange Ausgabe mit Details (Rechte, Größe, Datum, usw.)<br>
        • <code>-S</code> = sortiere nach Größe (Size)<br>
        • <code>-r</code> = reverse = umgekehrt (macht aufsteigend statt absteigend)
    </div>

    <h3>Lösung 2: Absteigend sortiert (große Dateien zuerst)</h3>
    <div class="befehl">ls -lS ~/daten</div>
    <div class="erklaerung">
        • <code>ls -lS</code> = sortiert automatisch absteigend (größte Dateien zuerst)<br>
        • Das <code>-r</code> fehlt hier, deshalb ist es absteigend
    </div>

    <hr>

    <h2>Aufgabe 4: Angemeldete Benutzer nach IP sortieren</h2>

    <div class="aufgabe">
        <strong>📝 Aufgabenstellung:</strong><br>
        Lassen Sie sich mit dem Kommando who alle angemeldeten Benutzer sortiert nach deren IP-Adresse anzeigen.
    </div>

    <h3>Lösung:</h3>
    <div class="befehl">who | sort -k5</div>

    <div class="erklaerung">
        <strong>Befehl erklärt:</strong><br>
        • <code>who</code> = zeigt alle aktuell angemeldeten Benutzer<br>
        • <code>|</code> = Pipe = leitet Ausgabe von einem Befehl zum nächsten<br>
        • <code>sort -k5</code> = sortiere nach dem 5. Feld (meist die IP-Adresse)
    </div>

    <div class="tipp">
        <strong>💡 Was zeigt who?</strong><br>
        Typische Ausgabe:<br>
        <code>v16  pts/0  2025-10-07 14:30 (192.168.1.100)</code><br>
        Felder: Benutzername, Terminal, Datum, Zeit, IP-Adresse
    </div>

    <h3>Alternative (falls IP nicht im 5. Feld):</h3>
    <div class="befehl">who | sort -t'(' -k2</div>
    <div class="erklaerung">
        Sortiert nach dem Text nach der öffnenden Klammer ( - dort steht oft die IP
    </div>

    <hr>

    <h2>Aufgabe 5: Shellprozedur 'argtest'</h2>

    <div class="aufgabe">
        <strong>📝 Aufgabenstellung:</strong><br>
        Schreiben Sie eine Shellprozedur 'argtest', die alle übergebenen Parameter in folgender Form ausgibt:<br>
        <code>v05@linux-wob6:~bin> argtest a b 1 3</code><br>
        Die Variablen $0, $1, $2, $3, $4, $5, $6, $7, $8, $9, $*, $@, $#, $?, $$ sollen auf dem Bildschirm angezeigt werden.
    </div>

    <h3>Schritt 1: Datei erstellen</h3>
    <div class="befehl">vi ~/bin/argtest</div>

    <h3>Schritt 2: Skript eingeben</h3>
    <div class="schritt">
        Im vi-Editor (drücken Sie <strong>i</strong> für INSERT-Modus):
    </div>
    <div class="befehl">#!/bin/bash<br># Shellprozedur argtest - zeigt übergebene Parameter<br><br>echo "Die Variablen haben folgenden Inhalt:"<br>echo ""<br>echo "\$0  : $0"<br>echo "\$1  : $1"<br>echo "\$2  : $2"<br>echo "\$3  : $3"<br>echo "\$4  : $4"<br>echo "\$5  : $5"<br>echo "\$6  : $6"<br>echo "\$7  : $7"<br>echo "\$8  : $8"<br>echo "\$9  : $9"<br>echo "\$*  : $*"<br>echo "\$@  : $@"<br>echo "\$#  : $#"<br>echo "\$?  : $?"<br>echo "\$$  : $$"</div>

    <h3>Schritt 3: Speichern</h3>
    <div class="schritt">
        Drücken Sie <strong>ESC</strong>, dann <strong>:wq</strong> und <strong>Enter</strong>
    </div>

    <h3>Schritt 4: Ausführungsrecht vergeben</h3>
    <div class="befehl">chmod +x ~/bin/argtest</div>

    <h3>Schritt 5: Testen</h3>
    <div class="befehl">argtest a b 1 3</div>
    <div class="erklaerung">
        <strong>Oder mit vollständigem Pfad (falls PATH nicht gesetzt):</strong><br>
        <code>~/bin/argtest a b 1 3</code>
    </div>

    <h3>Erklärung der Variablen:</h3>
    <table>
        <tr>
            <th>Variable</th>
            <th>Bedeutung</th>
            <th>Beispiel bei: argtest a b 1 3</th>
        </tr>
        <tr>
            <td><strong>$0</strong></td>
            <td>Name des Skripts selbst</td>
            <td>/home/v16/bin/argtest</td>
        </tr>
        <tr>
            <td><strong>$1</strong></td>
            <td>1. Parameter</td>
            <td>a</td>
        </tr>
        <tr>
            <td><strong>$2</strong></td>
            <td>2. Parameter</td>
            <td>b</td>
        </tr>
        <tr>
            <td><strong>$3</strong></td>
            <td>3. Parameter</td>
            <td>1</td>
        </tr>
        <tr>
            <td><strong>$4</strong></td>
            <td>4. Parameter</td>
            <td>3</td>
        </tr>
        <tr>
            <td><strong>$5 bis $9</strong></td>
            <td>Weitere Parameter (wenn vorhanden)</td>
            <td>(leer, da nicht übergeben)</td>
        </tr>
        <tr>
            <td><strong>$*</strong></td>
            <td>Alle Parameter als ein String</td>
            <td>a b 1 3</td>
        </tr>
        <tr>
            <td><strong>$@</strong></td>
            <td>Alle Parameter als separate Strings</td>
            <td>a b 1 3</td>
        </tr>
        <tr>
            <td><strong>$#</strong></td>
            <td>Anzahl der Parameter</td>
            <td>4</td>
        </tr>
        <tr>
            <td><strong>$?</strong></td>
            <td>Exit-Status des letzten Befehls (0 = OK)</td>
            <td>0</td>
        </tr>
        <tr>
            <td><strong>$$</strong></td>
            <td>Prozess-ID des laufenden Skripts</td>
            <td>339257</td>
        </tr>
    </table>

    <hr>

    <h2>Aufgabe 6: Shellprozedur 'cx'</h2>

    <div class="aufgabe">
        <strong>📝 Aufgabenstellung:</strong><br>
        Schreiben Sie eine Shellprozedur 'cx', die als Übergabeparameter einen Dateinamen erhält. Nach dem Aufruf soll die angegebene Datei ausführbar sein.
    </div>

    <h3>Schritt 1: Datei erstellen</h3>
    <div class="befehl">vi ~/bin/cx</div>

    <h3>Schritt 2: Skript eingeben</h3>
    <div class="befehl">#!/bin/bash<br># Shellprozedur cx - macht Datei ausführbar und führt sie aus<br><br>chmod +x $1<br>$1</div>

    <h3>Schritt 3: Speichern und Ausführungsrecht vergeben</h3>
    <div class="befehl">chmod +x ~/bin/cx</div>

    <h3>Schritt 4: Testen</h3>
    <div class="schritt">
        <strong>Test-Skript erstellen:</strong>
    </div>
    <div class="befehl">vi ~/testskript</div>
    <div class="schritt">
        Inhalt:
    </div>
    <div class="befehl">#!/bin/bash<br>echo "Hallo, das Skript läuft!"</div>
    <div class="schritt">
        Speichern und dann aufrufen:
    </div>
    <div class="befehl">cx ~/testskript</div>

    <div class="erklaerung">
        <strong>Was macht das Skript?</strong><br>
        1. <code>chmod +x $1</code> macht die Datei ausführbar ($1 = 1. Parameter = Dateiname)<br>
        2. <code>$1</code> führt die Datei dann sofort aus<br>
        <br>
        <strong>In einfachen Worten:</strong> "Mach die Datei ausführbar und starte sie"
    </div>

    <hr>

    <h2>Aufgabe 7: Shellprozedur 'tel' (Telefonbuch)</h2>

    <div class="aufgabe">
        <strong>📝 Aufgabenstellung:</strong>
        <ol>
            <li>Erzeugen Sie in ~/daten eine Datei 'telefon' mit Testdaten</li>
            <li>Schreiben Sie eine Shellprozedur 'tel', die ein Suchmuster als Parameter erhält und alle Zeilen mit diesem Muster anzeigt</li>
            <li>Erweitern Sie die Prozedur so, dass die Überschrift "Das Suchmuster 'XXX' wurde in Y Zeile(n) gefunden:" ausgegeben wird</li>
        </ol>
    </div>

    <h3>Teil 1: Datei 'telefon' erstellen</h3>
    <div class="befehl">cd ~/daten<br>vi telefon</div>
    <div class="schritt">
        Inhalt eingeben (Beispiel):
    </div>
    <div class="befehl">Tester................Thilo.......................Fussballverein ..................02357 - 335372<br>Rhasos....................Rudi........................IBM ...................................0251 - 14273<br>Fraaching .................Berta ........................Frauenbewegung.................0211 - 0815</div>

    <h3>Teil 2: Einfache Suchprozedur erstellen</h3>
    <div class="befehl">vi ~/bin/tel</div>
    <div class="schritt">
        Inhalt:
    </div>
    <div class="befehl">#!/bin/bash<br># Shellprozedur tel - Telefonbuch-Suche<br><br>echo "AUFRUF:        tel Muster"<br>echo ""<br>grep "$1" $HOME/daten/telefon</div>
    <div class="befehl">chmod +x ~/bin/tel</div>
    <div class="schritt">
        Testen:
    </div>
    <div class="befehl">tel Thilo</div>

    <div class="erklaerung">
        <strong>Was macht das Skript?</strong><br>
        • <code>grep "$1"</code> sucht nach dem 1. Parameter (z.B. "Thilo")<br>
        • <code>$HOME/daten/telefon</code> ist die Datei, in der gesucht wird<br>
        • Alle Zeilen, die das Suchwort enthalten, werden angezeigt
    </div>

    <h3>Teil 3: Erweiterte Version mit Zähler</h3>
    <div class="befehl">vi ~/bin/tel</div>
    <div class="schritt">
        Neuer Inhalt:
    </div>
    <div class="befehl">#!/bin/bash<br># Shellprozedur tel - erweiterte Telefonbuch-Suche<br><br>echo "AUFRUF:        tel Muster"<br>echo ""<br><br># Anzahl der gefundenen Zeilen zählen<br>anzahl=$(grep -c "$1" $HOME/daten/telefon)<br><br>echo "Das Suchmuster '$1' wurde in $anzahl Zeile(n) gefunden:"<br>grep "$1" $HOME/daten/telefon<br>echo "ENDE"</div>
    <div class="schritt">
        Testen:
    </div>
    <div class="befehl">tel Thilo</div>

    <div class="erklaerung">
        <strong>Neue Funktionen erklärt:</strong><br>
        • <code>anzahl=$(grep -c "$1" ...)</code> zählt, wie viele Zeilen gefunden wurden<br>
        • <code>$(...))</code> führt den Befehl aus und speichert das Ergebnis in der Variable "anzahl"<br>
        • <code>grep -c</code> = "count" = nur zählen, nicht anzeigen<br>
        • <code>echo "... $anzahl ..."</code> zeigt die Anzahl an<br>
        • Danach wird <code>grep</code> nochmal ohne -c aufgerufen, um die Zeilen anzuzeigen
    </div>

    <hr>

    <h2>📖 Wichtige Linux-Befehle - Übersicht</h2>

    <h3>Datei- und Verzeichnisverwaltung</h3>
    <table>
        <tr>
            <th>Befehl</th>
            <th>Bedeutung</th>
            <th>Beispiel</th>
        </tr>
        <tr>
            <td><code>pwd</code></td>
            <td>Aktuelles Verzeichnis anzeigen</td>
            <td><code>pwd</code></td>
        </tr>
        <tr>
            <td><code>cd</code></td>
            <td>Verzeichnis wechseln</td>
            <td><code>cd ~/daten</code></td>
        </tr>
        <tr>
            <td><code>ls</code></td>
            <td>Verzeichnisinhalt anzeigen</td>
            <td><code>ls -la</code></td>
        </tr>
        <tr>
            <td><code>mkdir</code></td>
            <td>Verzeichnis erstellen</td>
            <td><code>mkdir neuordner</code></td>
        </tr>
        <tr>
            <td><code>rm</code></td>
            <td>Datei löschen</td>
            <td><code>rm datei.txt</code></td>
        </tr>
        <tr>
            <td><code>cp</code></td>
            <td>Datei kopieren</td>
            <td><code>cp quelle.txt ziel.txt</code></td>
        </tr>
        <tr>
            <td><code>mv</code></td>
            <td>Datei verschieben/umbenennen</td>
            <td><code>mv alt.txt neu.txt</code></td>
        </tr>
        <tr>
            <td><code>cat</code></td>
            <td>Dateiinhalt anzeigen</td>
            <td><code>cat datei.txt</code></td>
        </tr>
    </table>

    <h3>Rechte und Benutzer</h3>
    <table>
        <tr>
            <th>Befehl</th>
            <th>Bedeutung</th>
            <th>Beispiel</th>
        </tr>
        <tr>
            <td><code>chmod</code></td>
            <td>Dateirechte ändern</td>
            <td><code>chmod +x skript.sh</code></td>
        </tr>
        <tr>
            <td><code>chown</code></td>
            <td>Besitzer ändern</td>
            <td><code>chown user datei.txt</code></td>
        </tr>
        <tr>
            <td><code>who</code></td>
            <td>Angemeldete Benutzer anzeigen</td>
            <td><code>who</code></td>
        </tr>
        <tr>
            <td><code>whoami</code></td>
            <td>Eigenen Benutzernamen anzeigen</td>
            <td><code>whoami</code></td>
        </tr>
        <tr>
            <td><code>ps</code></td>
            <td>Laufende Prozesse anzeigen</td>
            <td><code>ps -fu v16</code></td>
        </tr>
    </table>

    <h3>Suchen und Filtern</h3>
    <table>
        <tr>
            <th>Befehl</th>
            <th>Bedeutung</th>
            <th>Beispiel</th>
        </tr>
        <tr>
            <td><code>grep</code></td>
            <td>Text in Dateien suchen</td>
            <td><code>grep "Thilo" telefon</code></td>
        </tr>
        <tr>
            <td><code>grep -c</code></td>
            <td>Anzahl der Treffer zählen</td>
            <td><code>grep -c "Thilo" telefon</code></td>
        </tr>
        <tr>
            <td><code>find</code></td>
            <td>Dateien finden</td>
            <td><code>find ~ -name "*.txt"</code></td>
        </tr>
        <tr>
            <td><code>sort</code></td>
            <td>Zeilen sortieren</td>
            <td><code>sort datei.txt</code></td>
        </tr>
        <tr>
            <td><code>uniq</code></td>
            <td>Doppelte Zeilen entfernen</td>
            <td><code>sort datei.txt | uniq</code></td>
        </tr>
    </table>

    <h3>Pipes und Umleitungen</h3>
    <table>
        <tr>
            <th>Symbol</th>
            <th>Bedeutung</th>
            <th>Beispiel</th>
        </tr>
        <tr>
            <td><code>|</code></td>
            <td>Pipe: Ausgabe an nächsten Befehl weiterleiten</td>
            <td><code>who | sort</code></td>
        </tr>
        <tr>
            <td><code>></code></td>
            <td>Ausgabe in Datei umleiten (überschreibt)</td>
            <td><code>ls > liste.txt</code></td>
        </tr>
        <tr>
            <td><code>>></code></td>
            <td>Ausgabe an Datei anhängen</td>
            <td><code>echo "neu" >> datei.txt</code></td>
        </tr>
        <tr>
            <td><code><</code></td>
            <td>Eingabe aus Datei lesen</td>
            <td><code>sort < datei.txt</code></td>
        </tr>
    </table>

    <h3>Weitere nützliche Befehle</h3>
    <table>
        <tr>
            <th>Befehl</th>
            <th>Bedeutung</th>
            <th>Beispiel</th>
        </tr>
        <tr>
            <td><code>echo</code></td>
            <td>Text ausgeben</td>
            <td><code>echo "Hallo"</code></td>
        </tr>
        <tr>
            <td><code>clear</code></td>
            <td>Bildschirm löschen</td>
            <td><code>clear</code></td>
        </tr>
        <tr>
            <td><code>exit</code></td>
            <td>Sitzung beenden</td>
            <td><code>exit</code></td>
        </tr>
        <tr>
            <td><code>source</code></td>
            <td>Datei in aktueller Shell ausführen</td>
            <td><code>source ~/.profile</code></td>
        </tr>
        <tr>
            <td><code>man</code></td>
            <td>Handbuch zu Befehl anzeigen</td>
            <td><code>man ls</code></td>
        </tr>
        <tr>
            <td><code>history</code></td>
            <td>Befehlshistorie anzeigen</td>
            <td><code>history</code></td>
        </tr>
    </table>

    <hr>

    <h2>🔧 Häufige Probleme und Lösungen</h2>

    <h3>Problem 1: "command not found"</h3>
    <div class="wichtig">
        <strong>Ursache:</strong> Das Programm/Skript ist nicht im PATH oder nicht ausführbar.<br>
        <strong>Lösungen:</strong><br>
        1. Vollständigen Pfad verwenden: <code>~/bin/skript</code><br>
        2. PATH erweitern in ~/.profile: <code>PATH=$PATH:~/bin</code><br>
        3. Ausführungsrecht prüfen: <code>chmod +x skript</code>
    </div>

    <h3>Problem 2: "Permission denied"</h3>
    <div class="wichtig">
        <strong>Ursache:</strong> Keine Ausführungsrechte für die Datei.<br>
        <strong>Lösung:</strong><br>
        <code>chmod +x dateiname</code>
    </div>

    <h3>Problem 3: vi-Editor - komme nicht raus</h3>
    <div class="wichtig">
        <strong>Lösungen:</strong><br>
        1. <strong>ESC</strong> drücken (verlässt Insert-Modus)<br>
        2. <strong>:q!</strong> eingeben (beenden ohne speichern)<br>
        3. <strong>:wq</strong> eingeben (speichern und beenden)
    </div>

    <h3>Problem 4: Datei existiert bereits</h3>
    <div class="wichtig">
        <strong>Bei mkdir:</strong> Einfach mit nächstem Schritt fortfahren.<br>
        <strong>Bei >:</strong> Datei wird überschrieben. Zum Anhängen >> verwenden.
    </div>

    <h3>Problem 5: Variablen löschen</h3>
    <div class="wichtig">
        <strong>Einzelne Variable löschen:</strong><br>
        <code>unset VARIABLENNAME</code><br>
        <br>
        <strong>Alle lokalen Variablen zurücksetzen:</strong><br>
        Shell neu starten mit <code>exit</code> und neu einloggen
    </div>

    <hr>

    <h2>💡 Tipps und Tricks</h2>

    <div class="tipp">
        <h3>Tipp 1: Tab-Vervollständigung</h3>
        Drücken Sie <strong>Tab</strong> beim Tippen von Datei- oder Verzeichnisnamen.<br>
        Die Shell vervollständigt automatisch oder zeigt mögliche Optionen.
    </div>

    <div class="tipp">
        <h3>Tipp 2: Befehlshistorie nutzen</h3>
        • <strong>Pfeil hoch/runter:</strong> Vorherige Befehle durchblättern<br>
        • <strong>Ctrl+R:</strong> Rückwärtssuche in der Historie<br>
        • <strong>!!</strong> = Letzten Befehl wiederholen<br>
        • <strong>!n</strong> = Befehl Nummer n aus der Historie ausführen
    </div>

    <div class="tipp">
        <h3>Tipp 3: Mehrere Befehle kombinieren</h3>
        • <strong>&&</strong> = Nächsten Befehl nur ausführen, wenn vorheriger erfolgreich war<br>
        <code>mkdir test && cd test</code><br>
        <br>
        • <strong>;</strong> = Befehle nacheinander ausführen (unabhängig vom Erfolg)<br>
        <code>mkdir test ; cd test</code>
    </div>

    <div class="tipp">
        <h3>Tipp 4: Abkürzungen</h3>
        • <strong>~</strong> = HOME-Verzeichnis<br>
        • <strong>.</strong> = Aktuelles Verzeichnis<br>
        • <strong>..</strong> = Übergeordnetes Verzeichnis<br>
        • <strong>-</strong> = Vorheriges Verzeichnis<br>
        <br>
        Beispiele:<br>
        <code>cd ..</code> (eine Ebene höher)<br>
        <code>cd -</code> (zum letzten Verzeichnis zurück)
    </div>

    <div class="tipp">
        <h3>Tipp 5: Wildcards (Platzhalter)</h3>
        • <strong>*</strong> = beliebig viele Zeichen<br>
        • <strong>?</strong> = genau ein Zeichen<br>
        <br>
        Beispiele:<br>
        <code>ls *.txt</code> (alle .txt Dateien)<br>
        <code>rm test?.log</code> (test1.log, test2.log, etc.)
    </div>

    <hr>

    <h2>📝 Zusammenfassung aller Aufgaben</h2>

    <table>
        <tr>
            <th>Aufgabe</th>
            <th>Hauptbefehl</th>
            <th>Was wird gelernt</th>
        </tr>
        <tr>
            <td>1. ~/bin und cls</td>
            <td><code>mkdir ~/bin</code><br><code>vi ~/bin/cls</code><br><code>chmod +x</code></td>
            <td>Verzeichnisse erstellen, vi-Editor, Ausführungsrechte, PATH</td>
        </tr>
        <tr>
            <td>2. pass_sort</td>
            <td><code>sort -t: -k4 -n /etc/passwd > ~/daten/pass_sort</code></td>
            <td>Sortieren, Umleitungen, /etc/passwd verstehen</td>
        </tr>
        <tr>
            <td>3. Verzeichnisse sortieren</td>
            <td><code>ls -lSr</code><br><code>ls -lS</code></td>
            <td>ls-Optionen, Sortierung nach Größe</td>
        </tr>
        <tr>
            <td>4. Benutzer nach IP</td>
            <td><code>who | sort -k5</code></td>
            <td>Pipes, who-Befehl, Sortierung</td>
        </tr>
        <tr>
            <td>5. argtest</td>
            <td>Shellskript mit Variablen $0-$9, $*, $@, $#, $?, $</td>
            <td>Shell-Variablen, Parameterübergabe</td>
        </tr>
        <tr>
            <td>6. cx</td>
            <td>Shellskript: <code>chmod +x $1</code> und <code>$1</code></td>
            <td>Einfache Shellprogrammierung, chmod</td>
        </tr>
        <tr>
            <td>7. tel</td>
            <td>Shellskript mit grep, grep -c, Variablen</td>
            <td>grep, Variablen zuweisen, Textsuche</td>
        </tr>
    </table>

    <hr>

    <h2>🎓 Prüfungsvorbereitung - Wichtige Konzepte</h2>

    <div class="erklaerung">
        <h3>Was Sie verstehen sollten:</h3>
        <ul>
            <li><strong>PATH-Variable:</strong> Liste von Verzeichnissen, in denen nach Programmen gesucht wird</li>
            <li><strong>Ausführungsrechte:</strong> Eine Datei braucht +x um als Programm gestartet zu werden</li>
            <li><strong>Shell-Variablen:</strong> $1, $2, ... sind Parameter; $# ist die Anzahl; $0 ist der Skriptname</li>
            <li><strong>Pipes (|):</strong> Verbinden Befehle - Ausgabe von links wird Eingabe für rechts</li>
            <li><strong>Umleitungen (>, >>):</strong> Ausgabe in Datei schreiben statt auf Bildschirm</li>
            <li><strong>grep:</strong> Sucht nach Textmustern in Dateien</li>
            <li><strong>sort:</strong> Sortiert Zeilen (mit -t und -k für spezielle Felder)</li>
            <li><strong>vi-Editor:</strong> i = insert, ESC = command mode, :wq = save and quit</li>
        </ul>
    </div>

    <hr>

    <h2>📞 Weitere Hilfe und Ressourcen</h2>

    <div class="tipp">
        <strong>Wenn Sie nicht weiterkommen:</strong><br>
        <br>
        1. <strong>Handbuchseiten lesen:</strong><br>
        <code>man befehlsname</code><br>
        Beispiel: <code>man grep</code><br>
        <br>
        2. <strong>Hilfe zu Befehlen:</strong><br>
        <code>befehlsname --help</code><br>
        Beispiel: <code>ls --help</code><br>
        <br>
        3. <strong>Kommilitonen oder Dozenten fragen</strong><br>
        <br>
        4. <strong>Online-Ressourcen:</strong><br>
        • linux-praxis.de<br>
        • wiki.ubuntuusers.de<br>
        • stackoverflow.com
    </div>

    <hr>

    <div style="text-align: center; margin-top: 50px; padding: 20px; background: #ecf0f1; border-radius: 10px;">
        <h2>✅ Ende der Anleitung</h2>
        <p>Klicken Sie auf "Als PDF speichern / Drucken" oben rechts, um diese Anleitung zu speichern.</p>
    </div>

</body>
</html>
