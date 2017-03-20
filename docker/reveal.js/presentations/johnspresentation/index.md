<section data-state="no-title-footer">
## Docker  
Build, run, ship,  any app,  anywhere. ![docker-logo](https://raw.githubusercontent.com/Kawohl/presentations/master/docker/reveal.js/presentations/johnspresentation/rsz_1docker-small.png)
---

## Überblick

* Was sind eigentlich Linux Container?
* Linux Container im Vergleich zu VM´s
* Docker architektur
* Wie Docker meinen Arbeitsalltag erleichtert
* Deployment der Zukunft ?
---

## Linux Container 

* Virtualisierung mit einem Kernel
* Trennung der Prozesse durch Kernel-Namensräume (Namespaces) 
* Trotz Nutzung des Host-Kernels, komplette Trennung möglich (außerhalb des Namespaces, kein Mount, etc.)
* Gemeinsame Nutzung der Ressourcen (RAM, CPU) aber Verwaltung durch C-Groups.
* Beispiele für Linux Container: docker, LXC, rkt 
---

## Control Groups (Cgroups)

Verwaltung und Überwachung von Ressourcen:

**Beispiele:**
* Ram
* CPU
* Netzwerk
* Device Node: Access Control
---

## Namespace
Verschafft jedem Prozess einen eigenen Blick auf das System
Während die **Cgroup** verwaltet, **wieviel** der container vom System benutzen kann, verwaltet der **Namespace** **__was__** der Prozess vom System sehen kann.

**Beispiele:**
* pid 
* net
* mnt
* user 

---

## Linux Container im Vergleich zu Virtuellen Maschinen 
![container-vm-comparison](https://cloud.githubusercontent.com/assets/12275313/23125280/3fcb2ab0-f771-11e6-9d13-e2dd6fb55e0f.png)
---

## Werkzeug der Zukunft?
* Portabel
* Wenig Overhead
* Voll automatisierbar
* Breites einsatzgebiet
* Orchestrierungs Tools: Kubernetes, Swarm, Compose, 
---

## Warum Docker
* Industriestandard 
* Fertige container auf dockerhub
* Sehr einfaches interface design
* Orchestrierungs Tools: Kubernetes, Swarm, Compose
---

## Docker in meinem Arbeitsalltag

* owncloud Test-Instanz hochfahren: 
```
git clone https://github.com/owncloud-docker/server.git
cd server/
docker-compose up 
```

* pakete testen: z.b. : 
```
docker run -ti ubuntu:16.04
```
* testsysteme aufsetzen (andere produkte testen ...)
```
docker pull/run/build/compose/........
```

---

## Zusammenfassung

* Portabel: Jede app läuft auf jedem Docker-Host
* Datenpersistenz durch mountpoints auf dem Dateisystem
* Keine zerschossenen Betriebssysteme mehr. Image neu bauen reicht. 
* Kernel-update des Hostsystems aktualisiert alle docker-images.

---

##Nützliches
Diese Präsentation wurde mithilfe von html in einem docker-container erstellt.
 
* https://github.com/Kawohl/presentations
* https://www.docker.com/
* 