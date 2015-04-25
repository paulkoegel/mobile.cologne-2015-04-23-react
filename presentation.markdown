class: title
background-image: url(images/sunshine.jpg)

.titles[
# Einführung in React

.author[
  Paul Wittmann &mdash; [@wakkahari](https://twitter.com/wakkahari) &mdash; <paul@railslove.com>
]

.title--note[
  'p' drücken, um Präsentationsnotizen ein-/auszublenden]
]

???
'p' drücken, um Präsentationsnotizen ein-/auszublenden]

---

class: background-black
background-image: url(images/paul_wittmann_wakkahari.jpg)

.full-page-link[
[](https://twitter.com/wakkahari)
]

???
+ Entwickler bei **Railslove**: Webfrontends
+ vor anderthalb Jahren React entdeckt, keine Erfahrung mit nativer Entwicklung
+ React vorstellen, v.a. **Ideen** dahinter & **Neugier** wecken
+ **kein Tutorial**

---

background-image: url(images/react-logo-1000-transparent.png)

.full-page-link[
[](https://facebook.github.io/react/)
]

???
+ 2013: hatte React zunächst verworfen - wg. JSX, Markup in den Komponenten und Facebooks schlechtem Ruf als PHP-Klitsche.
+ Dezember 2013: Blogpost ["The Future of JavaScript MVC Frameworks"](https://swannodette.github.io/2013/12/17/the-future-of-javascript-mvcs/) von [David Nolen](https://twitter.com/swannodette) machte mich erst richtig neugierig auf React.

---

background-image: url(images/omingard-post.png)
class: background-cover

.full-page-link[
[](http://www.railslove.com/stories/my-way-into-clojure-building-a-card-game-with-om-part-1)
]

???
+ FYI: Hintergrundartikel wie ich über [Clojure](http://clojure.org) und [Om](https://github.com/omcljs/om) zu React kam.
+ Teil 2 steht noch aus.

---

class: vertical-center
.wrapper[
# Übersicht
1. Einführung
2. .blue[**Virtueller DOM**]
3. .green[**Komponentenarchitektur**]
4. React Native + Demos
]

---

class: background-cover where-we-stand
background-image: url(images/hieronymus-bosch-the-garden-of-earthly-delights.jpg)

.wrapper[
.full-page-link[
[](https://en.wikipedia.org/wiki/The_Garden_of_Earthly_Delights)
]

.headline_overlay[
  # JavaScript UI Landschaft
]]

???
+ Landschaft von Libraries ist chaotisch - manchmal auch der UI Code den wir schreiben
+ HTML wurde nicht für **Webanwendungen** geschaffen
+ User Interfaces sind schwer: Frameworks **sprießen aus dem Boden**
+ viel Bewegung und Raum für Innovation
+ React hat hier eine ziemliche Bresche geschlagen, viele andere Frameworks übernehmen gerade Ideen

---

class: vertical-center

.wrapper[
# Reacts Anfänge
+ Mitte 2013: von Facebook veröffentlicht
+ erste Reaktionen verhalten bis skeptisch
+ selbst erst durch Om & ["Rethinking best practices"](https://www.youtube.com/watch?v=x7cQ3mrcKaY) überzeugt
]

---

class: vertical-center vertical-center-large

.wrapper.no-margin-top-p[
  A JavaScript library for<br> building user interfaces.

  .vertical-source[
    \- React website.]
]

---

class: vertical-center

.wrapper[
# React
+ BSD Lizenz, "Patent"-Datei ([AKTUALISIERT](https://code.facebook.com/posts/1639473982937255/updating-our-open-source-patent-grant/))
+ Facebook, Instagram, Whatsapp, Yahoo, AirBnB, Khan Academy, Netflix, Atom editor, HipChat, Flipboard, BBC, Github, KISSmetrics, Pivotaltracker, Reddit, Uber, Sberbank... [mehr](https://github.com/facebook/react/wiki/Sites-Using-React)
]

???
---

class: vertical-center vertical-center-large

.wrapper.no-margin-top-p[
  A JavaScript **_library_** for<br> building user interfaces.

  .vertical-source[
    \- React website.]
]

???
<br>
### Library

+ viele stellten falsche Erwartungen an React - betrat die "JS MVC" Arena
+ ist kein **Framework** - und will auch keines werden
+ vulgo "the 'V' in MVC" - React folgt aber nicht MVC
+ **Virtual DOM** -> klasse Performanz und das war's - es geht aber um mehr (Komponentenarchitektur). [You're missing the point of React](https://medium.com/@dan_abramov/youre-missing-the-point-of-react-a20e34a51e1a).
+ flexibles Werkzeug, schränkt mich nicht ein wie ein Framework ("A product with the business logic removed, but all of the assumptions left in." (Devil’s Dictionary of Programming))
+ lässt sich leicht in bestehende Lösungen **integrieren**

---

class: vertical-center vertical-center-left

.vertical-title[Bibliothek]

+ nicht **Sprache des Frameworks** lernen
+ kämpfen gegen das Framework
+ **vielseitiges Werkzeug**, das es erlaubt die Business-Logik in der Sprache der Problemdomäne zu modellieren
+ ["Architecture - The Lost Years"](https://www.youtube.com/watch?v=WpkDN78P884) (2011)<br> &ndash; "Uncle Bob" Robert Martin

???
+ Uncle Bob: Ordnerstruktur einer Rails Anwendung sagt mir, dass es eine Railsanwendung ist; nicht, dass es ein Onlineshop ist. Bei Gebäuden hingegen (z.B. Kirchen) ist am Grundriss direkt erkennbar welche Funktion sie haben.

---

class: vertical-center
.wrapper[
# Reacts Bauteile
+ .blue[**Virtueller DOM**]
+ .green[**Komponentenarchitektur**]
+ Browserkompatibilität
]

???
+ Kompatibilität: synthetische Events ("a cross-browser wrapper around the browser's native event")

---

class: vertical-center vertical-center-large

.center[
_alien technology_

.alman[![](images/alman-rethink-best-practices.png)]]

???
+ erste **Reaktionen** (2013) waren verhalten
+ _alien_: [vom **anderen Stern**](http://lispers.org) -vs- **fremd**
+ Alien Technology: JSX, templates und view in gleicher Datei
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

.large-list.large-list-center[
+ **einfach**: keine Verschränkung, handelt von _einer_ Sache, objektiv
+ **leicht**: vertraut, naheliegend, relativ
+ Sprache: leicht für Muttersprachler, aber nicht einfach
+ ["Simplicity matters"](https://www.youtube.com/watch?v=rI8tNMsozo0) &ndash; Rich Hickey
]

???
+ simple (einfach) -vs- easy (leicht); einfach ist das Gegenteil von komplex
+ leicht: Plugin installieren - kann jede Menge Komplexität mit sich bringen
+ wir meinen oft, dass leichte Sachen auch einfach sind
+ einfache Lösungen zu finden ist viel schwerer als leichte zu finden


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
+ React Entwickler modifizieren nicht direkt den DOM -> React Native / React Canvas möglich gemacht.

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
+ [http://jsbin.com/lizutucimo/1/edit?html,js,output](http://jsbin.com/lizutucimo/1/edit?html,js,output)

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
  <div className="someClass">
    Hello
  </div>
```

```javascript
  React.dom.div(
    {className: "someClass"},
    "Hello");
```
]

???
Implikationen:
+ nur 1 Rückgabewert - ggf. in `<div>` wrappen
+ ggf. mit { ' ' } Spaces hinzufügen
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
+ -> [Immutable.js](https://facebook.github.io/immutable-js), [ClojureScript](https://github.com/clojure/clojurescript)

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

+ ["React: CSS in your JS"](https://vimeo.com/116209150)
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
+ Rootkomponente aggregiert alle Anforderungen und schickt GraphQL-Anfrage an Server

---

class: vertical-center vertical-center-large background-blue

# React Native

---

class: vertical-center background-blue

+ möglich gemacht durch Wegabstrahieren des DOMs (ähnlich: [React Canvas](https://github.com/Flipboard/react-canvas))
+ Januar 2015 angekündigt, im März veröffentlicht
+ **Facebook Messenger** und Ad Manager bereits damit in Betrieb
+ bisher nur iOS unterstützt, Android kommt bald
+ [Dokumentation](https://facebook.github.io/react-native) &ndash; [Repository](https://github.com/facebook/react-native)

???
+ [React Native – When the Mobile Web Isn’t Enough](http://red-badger.com/blog/2015/04/23/react-native-when-the-mobile-web-isnt-enough)
+ [React Native – The Killer Feature that Nobody Talks About](http://red-badger.com/blog/2015/03/04/react-native-the-killer-feature-that-nobody-talks-about)
+ [First Impressions using React Native](http://jlongster.com/First-Impressions-using-React-Native)
+ [Fresh on our Radar: React Native](http://www.railslove.com/stories/fresh-on-our-radar-react-native)

---

class: vertical-center background-blue

.wrapper[
+ JS Runtime --**asynchron**-> nativer Thread
+ "**learn once**, write anywhere"
+ Neuladen wie im Browser, ohne Kompilierungsschritt
+ [Flexbox nachimplementiert](https://github.com/facebook/css-layout)
+ keine Ajax-Requests, kein CORS, aber z.B. `fetch` als API für iOS Netzwerk APIs. [mehr](https://facebook.github.io/react-native/docs/network.html)
]

---

class: large-code background-blue

## Plattformspezifische Templates

```html
<View>
  <Text numberOfLines={2}>
    {this.props.movie.title}
  </Text>
  <DatePickerIOS ... />
</View>
```

???
+ `View` und `Text` gleich zwischen iOS und Android, `DatepickerIOS` nicht.
+ `View` entspricht einem `div`, `Text` einem `span`
+ native Views sind einfach unterschiedlich -> plattformspezifische Templates schreiben mit gleicher Technologie (JS & React)
+ **"write once run anywhere"** ist ein Wunschtraum

---

class: vertical-center no-padding-top

# React Native Demo:<br> WeatherApp<br>(3MB)

[![WeatherApp screenshot](images/weather-app.png)](https://github.com/jsphkhan/ReactNativeExamples/tree/master/ios/WeatherApp)

???
Quelle: [https://github.com/jsphkhan/ReactNativeExamples/tree/master/ios/WeatherApp](https://github.com/jsphkhan/ReactNativeExamples/tree/master/ios/WeatherApp)

---

background-image: url(images/react-native-alert.png)

.full-page-link[
  [](https://github.com/jsphkhan/ReactNativeExamples/tree/master/ios/WeatherApp)
]

???
+ im iOS-Simulator CMD-D drücken, um Chrome Debugger zu starten
+ Ctrl-CMD-Z drücken, um Debugging Optionen einzublenden
+ [https://facebook.github.io/react-native/docs/alertios.html](https://facebook.github.io/react-native/docs/alertios.html)

---

class: vertical-center no-padding-top

# TouchstoneJS Demo

---

class: vertical-center

.wrapper[## Probleme mit React Native<br>1 Woche nach Veröffentlichung
+ fehlende Videounterstützung - kam 3 Tage später
+ Flexbox Bugs im Zusammenspiel mit `border-sizing: border-box`
+ für kleine Demo erstmal [TouchstoneJS](http://touchstonejs.io/) benutzt - hybrides Framework in React
]

???
Alternative zu Touchstone: [Reapp](http://reapp.io).

---

class: vertical-center vertical-center-large background-grey

**Resümee**

---

class: vertical-center vertical-center-small

.wrapper[
# These
+ macht einfach Spaß - schnelle Ergebnisse
+ Facebook treibt React voran und nutzt es selbst ausgiebig
+ viele Entwickler, da JS-Bibliothek
+ server-seitiges Rendern
+ Bibliothek
+ Beiträge aus Clojure Community
]

---

class: vertical-center vertical-center-small

.wrapper[
# Antithese
+ Abhängigkeit von Facebook
+ Komponenten nur mit React verwendbar
+ nicht rein reaktiv ([staltz.com/dont-react](http://staltz.com/dont-react))
+ JavaScript ist kaputt
+ Flux: fehlende Best Practices
+ kein Framework
]

???
+ ["Reactive MVC and the Virtual DOM"](http://futurice.com/blog/reactive-mvc-and-the-virtual-dom)

---

class: vertical-center vertical-center-small

.wrapper[
# Synthese
+ extrem spannende Technologie und Ideen -> ausprobieren!
+ Leben von Frontendentwicklern vereinfacht
+ React ist ein Pionier, liegt sicher nicht in allen Belangen richtig
+ auf die Ideen kommt es an und davon werden uns einige noch länger beschäftigen und begegnen
+ nicht bei React haltmachen: [Immutable.js](https://facebook.github.io/immutable-js), [Flow](http://flowtype.org), [Cycle](https://github.com/staltz/cycle), [Baobab](https://github.com/Yomguithereal/baobab), [ClojureScript](https://github.com/clojure/clojurescript), [Om](https://github.com/omcljs/om), [CSP](https://en.wikipedia.org/wiki/Communicating_sequential_processes) z.B. mit [core.async](http://go.cognitect.com/core_async_webinar_recording), [Elm](http://elm-lang.org).
]

---

class: vertical-center vertical-center-large background-grey

**Coda**

---

class: no-padding-top

https://brumm.github.io/react-flexbox-playground

[**React Flexbox Playground**](https://railslove.github.io/react-flexbox-playground) von [Philipp Brumm](http://railslove.com/philipp)

.width-100[
[![https://brumm.github.io/react-flexbox-playground](images/flexbox-playground.png)](https://railslove.github.io/react-flexbox-playground)]

---

class: vertical-center vertical-center-large no-padding-top

.wrapper-center[
Wir suchen **JS Entwickler**!
<br>
.railslove-heart[![heart](images/railslove-heart.svg)]

.kontakt[
<kontakt@railslove.com>]

.smaller[React JS/Native &ndash; Ember.js<br>
in Anstellung oder selbstständig
]]

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
2.-3. Juli 2015 in Paris

[react-europe.org](http://www.react-europe.org)
]

---

.vertical-center.large[
Fragen?
]

---

## Links: Artikel & Demos
+ [The Future of JavaScript MVC Frameworks](https://swannodette.github.io/2013/12/17/the-future-of-javascript-mvcs)
+ [Removing User Interface Complexity, or Why React is Awesome](http://jlongster.com/Removing-User-Interface-Complexity,-or-Why-React-is-Awesome)
+ [React’s diff algorithm](http://calendar.perfplanet.com/2013/diff)
+ [My Way into Clojure: Building a Card Game with Om](http://www.railslove.com/stories/my-way-into-clojure-building-a-card-game-with-om-part-1)
+ [React Hot Loader Demo](https://www.youtube.com/watch?v=pw4fKkyPPg8)
+ [Circle CI demo](https://www.youtube.com/watch?v=5yHFTN-_mOo)
+ [Elm Debugger: Mario double jumps](https://www.youtube.com/watch?v=RUeLd7T7Xi4)

---

class: no-padding-top

## Links: Vorträge
+ [React.js Conf 2015 Keynote - Introducing React Native](https://www.youtube.com/watch?v=KVZ-P-ZI6W4)
+ [React.js Conf 2015 Keynote 2 - A Deep Dive into React Native](https://www.youtube.com/watch?v=7rDsRXj9-cU)
+ [Introduction to React Native](https://www.youtube.com/watch?v=n5RhAYhTxCk)
+ [Why does React Scale?](https://www.youtube.com/watch?v=D-ioDiacTm8)
+ [React: CSS in your JS](https://vimeo.com/116209150)
+ [The ReactJS Landscape](https://www.youtube.com/watch?v=oRmj3IUkRVk)
+ [The challenges and benefits of a functional reactive frontend](https://www.youtube.com/watch?v=TihhFQjtiZU)
+ [Simplicity matters](https://www.youtube.com/watch?v=rI8tNMsozo0) &ndash; Rich Hickey
+ [Clojure: Programming with Hand Tools](https://www.youtube.com/watch?v=ShEez0JkOFw)

---

class: vertical-center vertical-center-large

.wrapper.center[
**Danke!**<br><br>
.smaller[[@wakkahari](https://twitter.com/wakkahari)]
]
