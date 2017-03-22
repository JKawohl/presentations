
#Einleitung 
Herzlich Wilkommen zu meiner heutigen Präsentation:

Heute möchte ich Euch gerne Linux Container im allgemeinen und Docker im speziellen vorstellen.

Diese Präsentation soll einen kleinen Einblick in diese Themen geben:
 was sind eigentlich Linux Container, Container im vergleich zu Virtuellen Maschinen, wieso Docker?  Use Cases, und ein kleiner Ausblick. 

#Linux Container

Vereinfacht gesagt: Linux container sind  unabhängige Applikationsumgebungen  mit eigenen isolierten CPU, RAM, block I/O, und Netzwerk ressourcen.  Die sich den Kernel mit dem Host Betriebssystem teilen.

#Control Groups 

Die C-groups sorgen für die Ressourcenverwaltung. Hierüber kann zum Beispiel die Speichergröße eingeschränkt, der Datendurchsatz im Netzwerk oder auf Festplatten begrenzt oder die Zahl der verfügbaren CPUs bestimmt werden.

#Namespaces - Namensräume 

Die Kernelnamensräume  schotten die Prozesse von anderen ab.  (Prozesse außerhalb der Namensräume sind nicht sichtbar). 

Seit der Kernelversion 3.12 können Kernel-Namespaces[1] für ipc, uts, mount, pid, network und user verwendet werden. Damit besteht ab Linux Container Version 1.0 die Möglichkeit, einen Container unter einer anderen UID als der von root zu starten. Damit sind viele Sicherheitsprobleme behoben, insbesondere kann vom Container aus das Hostsystem nicht mehr verändert werden, wie zum Beispiel über das Schreiben in die Datei /proc/sysrq-trigger.

Ausserdem ist es mittlerweile möglich fremde Kernels zu benutzen also auch komplette Betriebssysteme in einem Container laufen zu lassen. (nur bedingt empfohlen, dazu später mehr.......)

#Container im Vergleich zu Virtuellen Maschinen

Weil Container so viel leichtgewichtiger als Virtuelle Maschinen sind, kann ich, wenn man beide vergleicht 6-8 mal so viele von Ihnen auf der gleichen Hardware laufen lassen. 

#Kurze Zwischenzusammenfassung:
Man kann LinuxContainer als Möglichkeit sehen, services und applikationen, komplett zu verpacken und einzusetzen ohne auf die Abhängikeiten und Bibliotheken anderer Applikationen rücksicht zu nehmen. 
Durch die komplette Prozessisolierung und Sichtisolierung kann Sicherheit gewährleistet werden. 

#Wieso eigentlich docker ?

docker ist open source.

Während die einrichtung eines Containers mittels LXC ein vertieftes Wissen rund um den Linux Kernel vorraussetzt und relativ Zeitaufwendig ist, hat docker es geschafft eine vereinfachtes Tooling zu entwickeln und hat sehr schnell eine hohe Verbreitung gefunden. Ein wesentlicher Vorteil ist seine Portabilität. Ein Container der auf einem docker Host läuft, läuft auch auf einem anderen Host. Entweder man zieht sich das image des Containers vom Docker-hub oder baut das image einfach selbst: Dazu reicht das Dockerfile, eine TextDatei die  typischerweise 6 - 45 Zeilen Code bzw. bauanweisung enthält.  

# Hands on: docker Nutzungsszenarios.

Folgendes Szenario: 
Der Entwickler in einem Unternehmen bekommt morgens , den Arbeitsauftrag für Software X ein neues Feature zu entwickeln. Der Server auf dem die Applikation am Schluss laufen soll hat ein komplexes setup und das Feature lässt sich nur mit neuen Abhängigkeiten sowie Frameworks realisieren.

Bisheriger Prozess: 
Der Entwickler bittet den Sysadmin um eine Entwicklungsumgebung. Der Sysadmin lädt sich eine aktuelle Version des Serverbetriebssystems herunter, bootet das System, installiert alle notwendigen Pakete und Abhängigkeiten, erstellt user und Berechtigungen und übergibt die fertige VM an den Entwickler um daran zu arbeiten.

Der Prozess mit Docker: 
Der Entwickler bittet den Sysadmin um eine Entwicklungsumgebung.
Der Sysadmin erstellt ein Dockerfile oder docker-compose file mit den benötigten komponenten und schickt das dem Entwickler. 
Der Entwickler muss nur noch einen Befehl ausführen docker run --parameter
oder besser docker-compose und docker lädt automatisch die benötigten container herunter, installiert die abhängikeiten und baut das benötigte Netzwerk um die Services miteinander zu verbinden.
Je nach komplexität und Datenübertragungsrate reichen wenige Sekunden. Und der Entwickler hat eine komplette Entwicklungsumgebung.


Während meiner Ausbildung habe ich unter anderem Linux Pakete gebaut und getestet. Wenn z.B. ein User probleme mit einem Paket auf einem CentOS7 im Bugtracker gemeldet hat,  reichte mir ein docker run -ti Centos:7 um eine kommandozeile in einem CentOS7 zu haben. 

docker run befiehlt hierbei dem Host Betriebssystem einen container zu starten. -ti  die shell zu öffnen und Centos:7 definiert den Container der vom dockerhub gezogen wird. 

Da docker prozesse voneinander isoliert sind baut docker ein eigenes Netzwerk auf, in dem die Prozesse untereinander kommunizieren.

#Demo 
Ich stelle das einfach mal kurz dar:
Ich starte eine owncloud Instanz mit einer mariadb/mysql datenbank und einem redis filecache und locking mechanismus.

Mit einem docker ps  werden mir alle laufenden container angezeigt. 
Der ownCloud container ist ein komplettes ubuntu mit Apache und PHP, der mysql container ein minimales alpine linux mit mariadb und der redis container ebenso nur eben mit dem redis server.

Mit dem befehl docker-compose up wird das docker-compose.yml gelesen und die entsprechenden container aufgerufen und miteinander verlinkt.

In dem 4. Container der zu sehen ist läuft meine Präsentation.

Ein großer Vorteil von Docker ist, das jeder für seine Zwecke geeignete Container bauen und diese an die Community weitergeben kann. So gibt es Container für alle großen Linux Distributionen,     







