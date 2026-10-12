### Erklärung

Auf der Seite `index.php` wurde eine Eingabe zur Anzahl der Noten erstellt, damit auf der nächsten Seite die richtige Anzahl der Eingabefelder angezeigt werden kann. Dazu wurde ein Formular genutzt mit einem Zahlen-Eingabe-Feld und einem Submit-Button.   
Wenn der Submit-Button gedrückt wird, wird die Seite `noten.php` aufgerufen (siehe `action="noten.php"`).    

Auf der Seite `noten.php` wurde eine Eingabe für die Noten aller Schüler (nach Matrikelnummer) erstellt.   
Die Anzahl der Noten ist im Superglobal-Array `$_POST` gespeichert, da wir das Formular der vorherigen Seite per POST übermittelt haben. Es wird gefiltert, ob die Anzahl ein gültiger Ganzwert ist.   
Das Hidden-Feld am Anfang des Formulars wird benötigt, damit die Anzahl der Noten an die nächste Seite mit übergeben wird.   
Danach folgen Eingabefelder für alle Noten mittels eine Schleife. Beim Klick auf dem Submit-Button wird die Seite `auswertung.php` aufgerufen.   

In `auswertung.php` wird am Anfang die Fehlerbehandlung durchgeführt und das Noten-Array aus der Super-global-Variable geholt. Dabei wird überprüft, ob die Anzahl ein gültiger Ganzwert ist, die Noten zwischen 1 und 5 liegen und alle Noten eingegeben wurden. Danach werden alle Noten im Array `$noten` gespeichert.   
Als nächstes werden die Werte für die Statistik ermittelt, also Durchschnitt, beste Note, schlechteste Note, etc.   
Die Notenübersicht wurde in Tabellenform dargestellt, wobei `$note` und `$index` als Laufvariablen in der foreach-Schleife dienen. Für jeden Schleifendurchlauf wird also eine neue Tabellenzeile mit Matrikelnummer des Schülers und seiner Note erstellt.   
Nach der Tabelle wird die Statistik ausgegeben. Der Durchschnitt wurde mittels `number_format()` auf 2 Nachkommastellen begrenzt und als Trennzeichen wurde "," gewählt.   
Zum Schluss erfolgt eine Verlinkung auf die erste Seite, also `index.php`, für eine neue Eingabe.
