Namespace, C-groups (Control Groupss) , Datei-Systeme:


Im Gegensatz zu anderen Systemen realisiert LXC seine Virtualisierung nicht mittels virtueller Maschinen. Stattdessen erzeugt LXC eine virtuelle Umgebung, die zwar ihre eigenen Prozesse besitzt, doch für diese gemeinschaftlich den Kernel des Hostsystems nutzt.

Während die Kernelnamensräume die Prozesse von anderen abschotten (Prozesse außerhalb der Namensräume sind nicht sichtbar) sorgen die cgroups für eine Ressourcenverwaltung. Hierüber kann zum Beispiel die Speichergröße eingeschränkt, der Datendurchsatz im Netzwerk oder auf Festplatten begrenzt oder die Zahl der verfügbaren CPUs bestimmt werden.

Ab Kernelversion 3.12 können Kernel-Namespaces[1] für ipc, uts, mount, pid, network und user verwendet werden. Damit besteht ab LXC-Version 1.0 die Möglichkeit, einen Container unter einer anderen UID als der von root zu starten. Damit sind viele Sicherheitsprobleme behoben, insbesondere kann vom Container aus das Hostsystem nicht mehr verändert werden, wie zum Beispiel über das Schreiben in die Datei /proc/sysrq-trigger.

Ausserdem ist es mittlerweile möglich fremde Kernels zu benutzen also auch komplette Betriebssysteme




