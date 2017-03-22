<section data-state="no-title-footer">
## Docker  
Build, run, ship,  any app,  anywhere. ![docker-logo](https://raw.githubusercontent.com/Kawohl/presentations/master/docker/reveal.js/presentations/johnspresentation/rsz_1docker-small.png)
---

## Überblick

* Was sind eigentlich Linux Container?

* Linux Container im Vergleich zu VM´s

* Docker vs. LXC 

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

## Warum Container?

* Effiziente Ressourcen Nutzung

* Prozessisolierung


---

## Docker Container im Vergleich zu Virtuellen Maschinen 
![container-vm-comparison](https://cloud.githubusercontent.com/assets/12275313/23125280/3fcb2ab0-f771-11e6-9d13-e2dd6fb55e0f.png)
---

![meme](https://github.com/Kawohl/presentations/blob/master/docker/reveal.js/presentations/johnspresentation/wfmmeme.jpg?raw=true)


---


## Warum Docker
* open Source

* Sehr einfaches interface design  

* Erweitert Linux Container u.a. um Portabilität

* Industriestandard 

* Vielzahl an tools und implementierungen 

* integriert in Google Cloud Platform, Amazon Web Services, azure container-services u.v.m. 


---


#### docker Ökosystem 
![overview](https://raw.githubusercontent.com/Kawohl/presentations/20b535b991dc08c91a03c9b5bed33b43d3ecd4be/docker/reveal.js/presentations/johnspresentation/dockerUsers.png)

---


## Docker in meinem Arbeitsalltag
* pakete testen: z.b. : 
```
docker run -ti centos:7
```

* owncloud Test-Instanz hochfahren: 
```
git clone https://github.com/owncloud-docker/server.git
cd server/
docker-compose up 
```

* container image von Dockerhub ziehen: 
```
docker pull ubuntu:16.04
```


---

## Nutzungsszenarien: 

* Entwicklungsumgebung
 
* Effektive Nutzung von Ressourcen

* Deployment on Demand: Lastspitzen abfangen 

* Portabilität: Migrationen sind einfach

---

# Ausblick:

* Große Verbreitung 
* Immer mehr tools zur Vereinfachung des Setups
* "Enterprise" Container
* Scalierung 
* Deployment on Demand



---

## Zusammenfassung

* relativ "Einfaches" Interface

* "wfm": "Bei mir läuft das aber" ist kein Problem mehr.

* Datenpersistenz durch mountpoints auf dem Dateisystem
 
* Effektive Ressourcennutzung und Verwaltung

* In der cloud quasi unendlich skalierbar  

---

##Nützliches
Diese Präsentation wurde mithilfe von HTML5 in einem docker-container erstellt.

* https://github.com/Kawohl/presentations
* https://www.docker.com/
* https://traefik.io/
* https://kubernetes.io/

---



