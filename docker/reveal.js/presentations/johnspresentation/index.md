<section data-state="no-title-footer">
## Docker  
Build, run, ship,  any app,  anywhere. ![docker-logo](https://raw.githubusercontent.com/Kawohl/presentations/master/docker/reveal.js/presentations/johnspresentation/rsz_1docker-small.png)
---

## Überblick

* Was sind eigentlich Linux Container?

* Linux Container im Vergleich zu VM´s

* Anwendungsszenarien 

* Die Zukunft? 
---

## Linux Container 

* Virtualisierung mit einem Kernel

* Prozesse durch Namespaces getrennt

* Komplette isolation vom Host möglich

* Beispiele für Linux Container: docker, LXC, LXD, rkt

* Alle Libs und Abhängikeiten in einem "Paket" 
---

## Control Groups (Cgroups)

Verwaltung und Überwachung von Ressourcen:

**Beispiele:**
* Ram

* CPU

* Netzwerk

* I/O Festplatte 
---
## Namespace 

**Beispiele:**

* Verwaltung der Sichtbarkeit von Prozessen:

* pid

* net

* mnt

* user                     
---

## Linux Container im Vergleich zu Virtuellen Maschinen 
![container-vm-comparison](https://cloud.githubusercontent.com/assets/12275313/23125280/3fcb2ab0-f771-11e6-9d13-e2dd6fb55e0f.png)
---

## Warum Container?

* Effiziente Ressourcen Nutzung

* Schnell verfügbar (dazu später mehr....)

* Prozessisolierung

---

## Warum Docker

* Industriestandard 

* Fertige container auf dockerhub

* Sehr einfaches interface design

* Orchestrierungs Tools: Kubernetes, Swarm, docker-compose

* integriert in Google Cloud Platform, Amazon Web Services, azure container-services u.v.m. 
---

## Unvollständiger Überblick über das docker Ökosystem 


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
Diese Präsentation wurde mithilfe von HTML5 in einem docker-container erstellt.

* https://github.com/Kawohl/presentations
* https://www.docker.com/
* https://traefik.io/
* https://kubernetes.io/