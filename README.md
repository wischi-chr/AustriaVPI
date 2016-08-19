# AustriaVPI
Verbraucherpreisindizes Österreichs

## Motivation
Manchmal benötigt Software (aktuelle) Verbraucherpreisindexwerte, doch leider habe ich online keine vollständige, aktuelle, gewartete Liste gefunden. Die Werte bei Statistik Austria stehen zwar in unterschiedlichster Form zur Verfügung (Excel, PDF, HTML), jedoch leider nicht (für Software) in einfach interpretierbarer Form, da die existierenden Formate alle _störende_ Formatierung beeinhalten.

## Lösung
Ein lokaler Dienst auf einem meiner Rechner holt sich online bei Statistik Austria selbstständig die aktuellen VPI Werte, sammelt diese und stellt sie danach in diesem Repository zur Verfügung. Die Werte werden als CSV abgelegt. Alle anderen eventuell benötigten Formate (z.B. XML, JSON, ... ) sind lokal von den CSV Datein abzuleiten und werden hier nicht zur Verfügung gestellt.

### Daten
* `data/codes.csv` beeinhaltet die zur Verfügung stehenden Indizes und deren voller Name aufgelistet.
* `data/termine.csv` beeinhaltet die nächsten Veröffentlichungstermine der VPI Werte durch Statistik Austria.
* `data/werte.csv` beeinhaltet alle für die Indizes zur Verfügung stehenden Werte. Die letzten (aktuellen) Werte der Indizes sind jeweils als vorläufige Werte zu betrachten und können sich unter Umständen ändern.

Die Werte können entweder durch klonen des Repos oder direkt (über GitHub) abgerufen werden.
https://raw.githubusercontent.com/wischi-chr/AustriaVPI/master/data/werte.csv

Es empfiehlt sich, die Daten lokal zu cachen, da sich die Indexwerte (i.d.R.) nur zu den genannten Terminen ändern und GitHub kein FileHoster (im eigentlichen Sinne) ist. Aus technischen Gründen kann es jedoch sein, dass die Indexwerte hier im Repository ein paar Tage nach der Veröffentlichung erscheinen.

### Quelle
Die Werte werden direkt von der Statistik Austria Seite bezogen. Konkret handelt es sich dabei um die HTML Versionen der Indizes, welche downgeloaded und lokal geparst werden. Danach werden diese in einem CSV zusammengetragen:
[http://www.statistik.at/.../zeitreihen_und_verkettungen/](http://www.statistik.at/web_de/statistiken/wirtschaft/preise/verbraucherpreisindex_vpi_hvpi/zeitreihen_und_verkettungen/index.html)

Obwohl ältere Indizes über sogenannte [Verkettungsfaktoren](http://www.statistik.at/web_de/statistiken/wirtschaft/preise/verbraucherpreisindex_vpi_hvpi/zeitreihen_und_verkettungen/022116.html) verbunden sind, werden diese von Statistik Austria bezogen und nicht selbst berechnet, um eventuelle Rundungsfehler vorzubeugen.

## Disclaimer
Obwohl die Zusammenstellung mit großer Sorgfalt passiert kann die Richtigkeit, Aktualität und Vollständigkeit nicht garantiert werden. Sie können die hier zusammengetragenen Daten gerne nutzen, aber Sie tun dies auf eigene Verantwortung.
