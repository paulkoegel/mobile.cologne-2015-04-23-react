class: title
background-image: url(images/tarkovsky3.jpg)

.titles[
# Einführung in React

.author[
  Paul Wittmann &mdash; [@wakkahari](https://twitter.com/wakkahari) &mdash; <paul@railslove.com>
]

.title--note[
  'p' drücken um Präsentationsnotizen einzublenden]
]

---

class: background-black
background-image: url(images/paul_wittmann_wakkahari.jpg)

???
+ Entwickler bei **Railslove**: Webfrontends
+ vor anderthalb Jahren React entdeckt, keine Erfahrung mit nativer Entwicklung
+ React vorstellen, v.a. **Ideen** dahinter & **Neugier** wecken
+ **kein Tutorial**

---

background-image: url(images/react-logo-1000-transparent.png)

???
+ 2013: erst verworfen
+ vor anderthalb Jahren über Clojure Community gefunden
+ Dezember 2013: ["The Future of JavaScript MVC Frameworks"](https://swannodette.github.io/2013/12/17/the-future-of-javascript-mvcs/) (David Nolen)

---

background-image: url(images/omingard-post.png)
class: background-cover

---

class: vertical-center
.wrapper[
# Übersicht
1. Einführung
2. .blue[**Virtueller DOM**]
3. .green[**Komponentenarchitektur**]
4. (React Native -vs- Touchstone.js)
5. Jenseits von React
]

---

class: background-cover where-we-stand
background-image: url(images/hieronymus-bosch-the-garden-of-earthly-delights.jpg)

.headline_overlay[
  # JavaScript UI Landschaft
]

???
+ Landschaft von Libraries - manchmal auch der UI code
+ User Interfaces sind schwer: Frameworks **sprießen aus dem Boden**
+ HTML wurde nicht für **Webapps** gebaut
+ viel Bewegung und Raum für Innovation

---

class: vertical-center vertical-center-large

.wrapper.no-margin-top-p[
  A JavaScript _library_ for<br> building user interfaces.

  .vertical-source[
    \- React website.]
]

???
### Geschichte
+ Mitte 2013, Facebook
+ erste Reaktionen skeptisch - selbst erst durch Om & Pete Hunt überzeugt.
+ Facebook, Instagram, Atom editor, Airbnb, Hipchat

<br>
### Library
+ **Erwartungshaltung**: kein **Framework**
+ the "V" in MVC - kein MVC, aber mehr als nur "V", da andere Ideen
+ **Virtual DOM** -> great performance; und das war's - es geht um mehr.

<br>
+ flexibles Werkzeug, schränkt mich nicht ein wie ein Framework ("A product with the business logic removed, but all of the assumptions left in." (Devil’s Dictionary of Programming))
+ lässt sich leicht in bestehende Lösungen **integrieren**

---

class: vertical-center vertical-center-left

.vertical-title[Bibliothek]

+ nicht **Sprache des Frameworks** lernen
+ **vielseitiges Werkzeug**, das es erlaubt die Business-Logik in der Sprache der Problemdomäne zu modellieren

---

class: vertical-center
.wrapper[
# React
+ .blue[**Virtueller DOM**]
+ .green[**Komponentenarchitektur**]
+ Browserkompatibilität
]

???
+ Komp.: synthetische Events ("a cross-browser wrapper around the browser's native event")

---

class: vertical-center vertical-center-large

.wrapper[
_alien technology_

.alman[![](images/alman-rethink-best-practices.png)]]

???
+ erste **Reaktionen** (2013) waren verhalten
+ _alien_: vom **anderen Stern** -vs- **fremd**
+ Alien Technology; JSX, templates und view in gleicher Datei
+ Wir sind immer noch dabei zu entdecken was dank React alles möglich ist.
+ Input und **Erweiterungen** der **Clojure community**.

---

class: vertical-center vertical-center-medium

.vertical-title[Motivation]

.wrapper[
Leichter zu verstehender &<br> besser wartbarer Code

-> _einfacherer_ Code
]

???
+ Facebook: vor allem Zeit um Code zu verstehen und Bugs zu fixen minimieren

---

class: vertical-center

.vertical-title[Rich Hickey]

.large-list.large-list-center[
+ **einfach**: keine Verschränkung, handelt von _einer_ Sache, objektiv
+ **leicht**: vertraut, naheliegend, relativ
+ Sprache: leicht für Muttersprachler, aber nicht einfach
]

???
+ simple -vs- easy
+ leicht: Plugin installieren - kann jede Menge Komplexität mit sich bringen
+ Deutsch sprechen fällt uns allen leicht. Das heißt aber nicht, dass es eine einfache Sprache ist.

---

class: vertical-center vertical-center-large background-blue

**Virtueller DOM**

---

background-image: url(images/davis-prismatic-example-01-before-cropped.png)

???
+ **Prismatic** Screenshot
+ wenn ich "Urban Exploration" **followe** passiert...

---

background-image: url(images/davis-prismatic-example-02-after-cropped.png)

???
Probleme:
+ **synchron halten** = aufwändig
+ mehrere DOM-Updates oft nicht **performant**

---

class: vertical-center background-blue

.vertical-title[Ziel]

1. **kein Nachdenken** über DOM Updates
2. bei guter Performanz

???
+ in öffentlicher Wahrnehmung: Performanz!
+ Performanz ist in Wahrheit netter Nebeneffekt
+ Ziel ist Einfachheit, nicht bestmögliche Performanz
+ **bessere Performanz durch Einfachheit**

---

class: vertical-center vertical-center-large background-blue

was wäre am _allereinfachsten_?

???
+ Ausgangsfrage für FB
+ Grenzen ignoriert und erstmal gebaut

---

class: vertical-center vertical-center-large background-blue

.vertical-title[Reacts Lösung]

bei jeder Änderung<br> _alles_ neurendern

???

+ **einfachste** Lösung
+ nie im Leben **performant**

---

class: vertical-center vertical-center-large background-blue

.vertical-title[Hauptproblem]

DOM-Updates sind langsam

---

background-image: url(images/neo-virtual-dom.png)

---

class: vertical-center vertical-center-medium background-blue

.vertical-title[Virtueller DOM]

.height-150[Daten → _render_ Funktion → VDOM<sub>n</sub> →
]

---

class: vertical-center vertical-center-medium background-blue

.vertical-title[Virtueller DOM]

.height-150[Daten → _render_ Funktion → VDOM<sub>n</sub> →<br>
diff(VDOM<sub>n</sub>, VDOM<sub>n-1</sub>) → DOM Updates]

???
+ VDOM = **JS objekt**
+ **minimale Änderungen** gehen an echten DOM

---

class: background-black

background-image: url(images/doom3-react.png)

???
+ schwarz-weiß: Doom 3 Rendering Engine
+ Blau-weiß: React-Entsprechungen

---

class: vertical-center vertical-center-medium vertical-center background-blue

+ als würden wir ständig den DOM neurendern
+ performant durch präzise DOM-Updates
+ DOM wegabstrahiert

???
+ React Entwickler modifizieren nicht direkt den DOM -> React Native / React Canvas.

---

class: vertical-center vertical-center-medium background-blue

React = Shim für reaktiven DOM

---

background-image: url(images/monkeys-slow.gif)

???
+ Textbox mit mathematischen Formeln
+ links React, rechts Backbone

---

class: vertical-center vertical-center-large background-green

**Komponentenarchitektur**

???
React hat nur _einen_ Baustein: Komponenten

---

class: vertical-center

<div id='example'></div>

<script type='text/jsx'>
  
  var ButtonCounter = React.createClass({

    buttonStyle: {
      width: 200,
      height: 80,
      fontSize: 25
    },

    getInitialState: function() {
      return { count: 0 };
    },

    addOne: function() {
      this.setState({ count: this.state.count + 1 });
    },

    render: function() {
      return <div>
          <div>{ this.state.count }</div>
          <button style={ this.buttonStyle } onClick={ this.addOne }> +1 </button>
        </div>
    }
  });

React.render(<ButtonCounter />,
             document.getElementById('example'));
</script>

???
+ http://jsbin.com/lizutucimo/1/edit?html,js,output

---

class: code-fullscreen component-example

```html
<script src='react.js'></script>
<script src='JSXTransformer.js'></script>

<div id='example'></div>

<script type='text/jsx'>
  var ButtonCounter = React.createClass({
    getInitialState: function() {
      return { count: 0 };
    },

    addOne: function() {
      this.setState({ count: this.state.count + 1 });
    },

    render: function() {
      return <div>
          <div>{ this.state.count }</div>
          <button onClick={ this.addOne }> +1 </button>
        </div>
    }
  });

React.render(<ButtonCounter />,
             document.getElementById('example'));
```

???
auffällig:
+ Markup in der Komponente (JS und "HTML" gemischt)
+ **onclick**
+ JS als Templatingsprache: users.map(...)

---

class: background-green

# JSX

.large-code[
```html
  <div class="someClass">
    Hello
  </div>
```

```javascript
  React.dom.div(
    {class: "someClass"}, "Hello");
```
]

???
Implikationen:
+ nur 1 Rückgabewert - ggf. in `<div>` wrappen
+ ggf. mit {{ ' ' }} Spaces hinzufügen
+ [https://facebook.github.io/react/docs/jsx-in-depth.html](https://facebook.github.io/react/docs/jsx-in-depth.html)

---

class: vertical-center vertical-center-medium background-green

.vertical-title[Motivation für Komponenten]
+ an _einer Stelle_ ablesbar was ein UI Element macht
+ einfacher Datenfluss

???
+ Einfachheit
+ Beispiel war einfach - kein Nesting

---

class: code-fullscreen component-example

```javascript
var ButtonCounter = React.createClass({
  getInitialState: function() {
    return { count: 0 };
  },

  addOne: function() {
    this.setState({ count: this.state.count + 1 });
  },

  render: function() {
    return <div>
        <div>{ this.state.count }</div>
        <button onClick={ this.addOne }> +1 </button>
      </div>
  }
});
```
---

class: vertical-center vertical-center-large background-green

_state_ -vs- _props_

???
+ sehr wichtiges Merkmal von Komponenten, wodurch leichter nachzuvollziehen ist was in ihnen passiert:

???

---

class: background-green

# Props

.large-code[
```html
<FriendListInfo name="Darth Vader"
       mutual_friends_count=100 />
```
]

???
von außen gesetzte Attribute

---

class: vertical-center vertical-center-large background-green

_state_ -vs- _props_

???
### Unterscheidung
+ **state** ist veränderbar, aber wird nur von dieser Komponente verändert
+ **props** sind _für diese Komponente_ unveränderbar
+ zähmt das **Mutable State Monster**
+ macht Code viel besser nachvollziehbar wenn ich weiß, dass etwas nicht verändert werden kann

---

class: background-stretch-vertical mutable-state-is-bad
background-image: url(images/davis-mutable-state-is-bad.png)

???
+ -> **Immutable.js**

---

class: vertical-center vertical-center-medium background-green

.vertical-title[alles fließt stromabwärts]

_unidirektionaler_ Datenfluss zwischen Komponenten

???
+ immer von Parent zu Child.

---

class: vertical-center vertical-center-large background-green

.vertical-title[und wenn's doch mal stromaufwärts sein muss]
**Flux**

???
+ child -> parent
+ viele Forks und Abarten: Reflux, Flummox, ...
+ in Flux kommt man nicht so schnell rein wie in React

---

background-image: url(images/flux-diagram.png)

---

class: vertical-center vertical-center-medium background-green

.wrapper[
# Ausblick Komponentenarchitektur

+ CSS in JavaScript
+ Datenanforderungen in der Komponente (GraphQL & Relay)]

???

+ CSS: wozu SASS etc. wenn ich JavaScript benutzen kann?
+ alles was für eine Komponente wichtig ist in einer Datei - keine Trennung von Technologien

---

background-image: url(images/components-example.png)

???
+ **verschachtelt**
+ **Daten**:
  - Array von Freunden
  - Avatar, Freundschaftsstatus
  - Name, # gemeinsame Freunde

---

background-image: url(images/relay-01.png)

???
auf **Server** muss das gleiche Wissen stecken damit wir nicht zu viele API Requests machen müssen

---

background-image: url(images/relay-06.png)

???
+ das ist **GraphQL**
+ Datenanforderungen steigen zum Wurzelelement auf und werden dort aggregiert an den Server geschickt
+ hat **serverseitige** Komponente

---

class: vertical-center vertical-center-large background-green

**Relay**

???
+ GraphQL in React
+ Komponenten spezifizieren ihre Datenanforderungen
+ Eltern verweisen auf die Anforderungen ihrer Kinder
+ Rootkomponente aggregiert alle Anforderungen und schickt GraphQL Anfrage an Server

---

class: vertical-center vertical-center-large background-blue

.wrapper[
# React Native

build **native apps** with React
]

???
Virtual DOM - doesn't matter where you're actually rendering - can easily be exchanged

---

class: vertical-center background-blue

.wrapper[
+ JS runtime --**asynchronously**-> native thread
+ "**learn once**, write anywhere"
+ web development experience 
+ Flexbox nachimplementiert
+ React Canvas
]

???
1. write JS & React, runs on a **JS runtime** renders to **native views**
2. **the platforms are different** - not the same code but the same stack - **the platforms are different**
3. no compilation step

---

class: large-code background-blue

```html
<View>
  <Text numberOfLines={2}>
    {this.props.movie.title}
  </Text>
</View>
```

???
+ instead of **div** and **span**
+ native views are simply **different**
+ write once run anywhere is a **pipe dream**

---

class: vertical-center

.wrapper[
# Resümee: Vorteile
+ macht einfach Spaß - schnelle Ergebnisse
+ Facebook nutzt und treibt React voran
+ viele Entwickler, da JS-Bibliothek
+ server-seitiges Rendern
+ Bibliothek
+ Beiträge aus Clojure Community
]

---

class: vertical-center

.wrapper[
# Resümee: Nachteile
+ Abhängigkeit von Facebook
+ Komponenten nur mit React verwendbar
+ nicht rein reaktiv ([staltz.com/dont-react](http://staltz.com/dont-react))
+ JavaScript ist kaputt
+ Flux: fehlende Best Practices
+ kein Framework
]

---

[https://brumm.github.io/react-flexbox-playground](https://brumm.github.io/react-flexbox-playground)

---

class: vertical-center vertical-center-large

.wrapper-center[
Wir suchen JS Entwickler!
<br>
.railslove-heart[![heart](images/railslove-heart.svg)]

kontakt@railslove.com
]

???
+ Virtuelle DOM erleichtert das bauen von "reaktiven" UIs erheblich
+ Reacts Komponentenarchitectur macht es leicht nachzuvollziehen was der Code macht
+ Zukunft: Relay, Flux, ClojureScript
+ **Virtual DOM**: kopiert, **standalone**

# 
---

class: vertical-center background-blue

.wrapper[
# React Europe
2.-3. Juli in Paris

[react-europe.org](http://www.react-europe.org)
]

---

.vertical-center.large[
Fragen?
]

---

# Links
+ [React.js Conf 2015 Videos](https://www.youtube.com/playlist?list=PLb0IAmt7-GS1cbw4qonlQztYV1TAW0sCr)
+ [The Future of JavaScript MVC Frameworks](https://swannodette.github.io/2013/12/17/the-future-of-javascript-mvcs)
+ [Removing User Interface Complexity, or Why React is Awesome](http://jlongster.com/Removing-User-Interface-Complexity,-or-Why-React-is-Awesome)
+ [React’s diff algorithm](http://calendar.perfplanet.com/2013/diff)
+ [Coming to React from Angular](http://www.stridenyc.com/blog/2015/3/4/coming-to-react-from-angular)
+ [Hotloader](https://www.youtube.com/watch?v=pw4fKkyPPg8)
+ [React & Om](https://paulwittmann.github.io/cgnjs-om)
+ [My Way into Clojure: Building a Card Game with Om](http://www.railslove.com/stories/my-way-into-clojure-building-a-card-game-with-om-part-1)

---

.vertical-center.large[
Danke!
]
