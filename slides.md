<!--- .slide data-background="images/clojure-logo.png" -->

<h1> Clojure <span class="fragment">(script)</span></h1>
<img src="images/clojure-logo.png" class="no-style"/>

-----
# Kezako?

-----
## un Lisp

<p class="big-parens">
  <span class="fragment">(</span>
![Mccarthy](http://wwwcache.wraltechwire.com/asset/news/2011/10/26/10299584/JOHN_MCCARTHY-512x324.jpg)
  <span class="fragment">)</span>
</p>

compilation pour la JVM, et JS (Clojurescript!)

-----
## f(x) => (f x)

Pour appeler une fonction, on la met en première position entre parenthèses

```
(+ 1 2)
;; => 3

(+ 1 2 3)
;; => 6

(conj [1 2 3] 4)
;; => [1 2 3 4]

(= true 1)
;; => false
(= false nil)
;; => false
```

-----
## Langage fonctionnel

```
(reduce + [1 2 3 4])
;; => 10

(apply + [1 2 3 4])
;; => 10

(def sum-list
  (partial apply +))

(sum-list [1 2 3 4]
;; => 10

```

-----
## Des structures de données un peu exotiques

- set : `#{1 2 3}` => unicité!
Union, intersection, difference...

- sorted-set (comme dans Redis!)
- sorted-map

-----
## ... et immutable
<!--
Utilise des structures de données persistentes par défaut
 ![SDP](http://eclipsesource.com/blogs/wp-content/uploads/2009/12/clojure-trees.png) -->

```clojure

(def a {:surname "Dylan" :name "Bob"})

```

<img src="images/persistent.png" class="no-style">

-----
## Structural Sharing

```clojure

(def a {:surname "Dylan" :name "Bob"})
(def b (assoc a :surname "l'éponge"))
```

<img src="images/persistent2.png" class="no-style">

-----
## Immutabilité: Pour quoi faire?

Réponse : Comparer des objets!!!

```js
var a = { name: "Bob", surname: "Dylan" };
var b = _.clone(a);

b.surname = "l'éponge";

// en javascript, on ne peut malheureusement pas faire ça :
if (objet1 == objet2) ...
```

-----
## exemple : un article

-----
## rien de nouveau sous le soleil

![git-logo](http://git-scm.com/images/logos/downloads/Git-Logo-1788C.png)

C'est ce que git utilise pour calculer les delta entre ses objets!

-----
## Bonne inter-opérabilité

Accès aux libs Java et JS

-----
## Google closure compiler
 - enlève le code "mort"

Mais... annotations pas très sympa à écrire.

-----
# Show time!

-----
