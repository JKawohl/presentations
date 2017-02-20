<section data-state="no-title-footer">

# Docker  
Build, run, ship,  any app,  anywhere. 


by Jonathan Kawohl

---

## Überblick

* Was sind eigentlich Linux Container?
* Linux Container im Vergleich zu VM´s
* Deployment der Zukunft ?
* Wie Docker meinen Arbeitsalltag erleichtert


---

## Linux Container 

* Virtualisierung mit einem Kernel
* Trennung der Prozesse durch Kernel-Namensräume (Namespaces) 
* Trotz Nutzung des Host-Kernels, komplette Trennung möglich (außerhalb des Namespaces, kein Mount, etc.)
* Gemeinsame Nutzung der Ressourcen (RAM, CPU) aber Verwaltung durch C-Groups.
* Benutzung fremder Kernel trotzdem möglich (komplette Betriebssysteme)


---

## Linux Container im Vergleich zu Virtuellen Maschinen 
![container-vm-comparison](https://cloud.githubusercontent.com/assets/12275313/23125280/3fcb2ab0-f771-11e6-9d13-e2dd6fb55e0f.png)
---

## Unordered Lists

* bla
* blubb <!-- .element: class="fragment" data-fragment-index="2" -->
* bla blubb <!-- .element: class="fragment" data-fragment-index="3" -->

---

## Ordered List

1. Bla
1. Bubber

---

## Stiling in Markdown

Make things **bold** or *italic*

---

## Code

```
function linkify( selector ) {
  if( supports3DTransforms ) {

    var nodes = document.querySelectorAll( selector );

    for( var i = 0, len = nodes.length; i &lt; len; i++ ) {
      var node = nodes[i];

      if( !node.className ) {
        node.className += ' roll';
      }
    }
  }
}
```

---

## Tables

| this  | is    | a       |
|-------|-------|---------|
| nice  | table | with    |
| some  | weird | content |

---

## Mathjax

$$ \sqrt{\frac{\Pi}{\Gamma}} \LaTeX $$

---

## Graphs

<iframe style="overflow:hidden;margin:5px 5px auto auto;" class="stretch" scrolling="no" id="chart-frame-1" data-chart></iframe>

---

## More Graphs

<div id="mynetwork"></div>
<div id="blubber" class="fragment"></div>

---

### Even More Graphs

<div id="tree_network"></div>
<div id="tree_add_node" class="fragment"></div>
<div id="tree_add_label" class="fragment"></div>

