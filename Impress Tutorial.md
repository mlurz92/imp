# impress.js Tutorial für nicht-lineare ZUI-Präsentationen
## Inhaltsverzeichnis

1.  **[Teil 1: Einführung in impress.js](#teil-1-einfuehrung-in-impressjs)**
    * Was ist `impress.js`? Philosophie und Kernkonzept (ZUI - Zooming User Interface)
    * Vorteile für nicht-lineare Präsentationen
    * Grundlegendes Setup
        * Einbinden der Bibliothek (CDN-Links)
        * Minimale HTML-Struktur
    * Lizenz und Community

2.  **[Teil 2: Erste Schritte mit impress.js](#teil-2-erste-schritte-mit-impressjs)**
    * Die grundlegende HTML-Struktur einer `impress.js`-Präsentation im Detail
        * Dokumenttyp und Wurzelelement (`<!doctype html>`, `<html>`)
        * Der `<head>`-Bereich (Metadaten, CSS-Verknüpfungen)
        * Der `<body>`-Tag (`class="impress-not-supported"`, Fallback-Nachricht)
        * Der Hauptcontainer `<div id="impress">`
    * Der "Step" im Detail
        * Struktur (`<div class="step">`)
        * Obligatorische Klasse `step`
        * Optionale, empfohlene `id`
        * Inhalt eines Steps
        * Minimale Datenattribute für den Anfang (`data-x`, `data-y`)
    * Erstellen der ersten einfachen Präsentation (Beispiel mit 2-3 Steps)
    * Initialisierung von `impress.js` mittels `impress().init();`
        * Platzierung der Skripte
        * Der Aufruf `impress().init();`
        * Was passiert bei `init()`?
        * Konfiguration bei der Initialisierung (Ausblick)
        * Verwendung einer benutzerdefinierten Root-ID
    * Verständnis des Hauptcontainers und der einzelnen Steps (Zusammenfassung)

3.  **[Teil 3: Positionierung von Steps im 2D- und 3D-Raum](#teil-3-positionierung-von-steps-im-2d--und-3d-raum)**
    * Das Koordinatensystem von `impress.js` im Detail
        * Die Leinwand (`<div id="impress">`)
        * Der Ursprungspunkt (0,0,0)
        * Die Achsen (X, Y, Z)
        * Einheiten (Pixel)
        * Visualisierung
    * Datenattribute zur Positionierung im Detail
        * `data-x` (Horizontale Position)
        * `data-y` (Vertikale Position)
        * `data-z` (Position in der Tiefe und Einfluss der Perspektive)
    * Erstellen von 2D-Layouts
        * Lineare Anordnungen (horizontal, vertikal)
        * Nicht-lineare 2D-Anordnungen (Grid, freie Formen)
        * Abstände und Überlappungen
        * Wichtigkeit der Step-Dimensionen (CSS)
    * Einführung in 3D-Layouts: Nutzung der Z-Achse für Tiefeneffekte
        * Kombination von `data-x`, `data-y`, `data-z`
        * Steps vor und hinter der Hauptebene
        * Staffelungseffekte und "Durchflug"-Effekte
    * Beispielcode für verschiedene Positionierungsszenarien (2D und 3D)

4.  **[Teil 4: Rotation und Skalierung von Steps](#teil-4-rotation-und-skalierung-von-steps)**
    * Grundlagen der Transformationen in `impress.js`
        * Transformationsursprung (`transform-origin`)
        * Reihenfolge der Transformationen
    * Rotation von Steps im Detail
        * `data-rotate-x` (Rotation um die X-Achse)
        * `data-rotate-y` (Rotation um die Y-Achse)
        * `data-rotate-z` (Rotation um die Z-Achse, Alias: `data-rotate`)
        * Kombination von Rotationen
    * Skalierung von Steps im Detail (`data-scale`)
        * Unterschied zur Skalierung durch `data-z` (Perspektive vs. direkte Skalierung)
        * Kombination von `data-scale` und `data-z`
    * Kombination von Positionierung, Rotation und Skalierung für komplexe ZUI-Effekte
    * Auswirkungen auf Inhalt und Lesbarkeit
    * Beispielcode zur Demonstration der Transformationsmöglichkeiten

5.  **[Teil 5: Präsentationssteuerung und Navigation](#teil-5-praesentationssteuerung-und-navigation)**
    * Grundlagen der Navigation in `impress.js` (aktiver Step, Übergänge)
    * Standardmäßige Tastaturnavigation im Detail (Leertaste, Pfeiltasten, Pos1, Ende etc.)
    * Maus-Klick-Navigation im Detail
    * Die "Overview"-Ansicht (Übersichtsmodus) im Detail
        * Konzept und Aktivierung (ESC-Taste)
        * Manuell erstellter "Overview"-Step
        * Navigation im Overview-Modus
        * Zweck und Vorteile
    * Verständnis des Präsentationsflusses in nicht-linearen Strukturen
        * DOM-Reihenfolge als Basis
        * Planung nicht-linearer Pfade (Mindmap-Ansatz, Zoom-Ebenen, visuelle Metaphern)
    * Verwendung von IDs für Steps zur direkten Navigation und Verlinkung (URL-Hash, interne Links)
    * Anpassen des Navigationsverhaltens (Ausblick auf Konfiguration und API)

6.  **[Teil 6: Styling von impress.js-Präsentationen mit CSS](#teil-6-styling-von-impressjs-praesentationen-mit-css)**
    * Die Rolle von CSS in `impress.js`-Präsentationen (Erscheinungsbild, Übergänge, Zustände)
    * Grundlegendes CSS-Setup und empfohlene Basis-Stylesheets
        * `impress-common.css`
        * `impress-demo.css` (als Inspirationsquelle)
        * Eigene CSS-Datei
    * Wichtige CSS-Klassen, die von `impress.js` dynamisch verwaltet werden
        * Auf dem `<body>`: `impress-not-supported`, `impress-supported`, `impress-enabled`, `impress-overview`
        * Auf dem `#impress`-Container (oder Canvas)
        * Auf den `.step`-Elementen: `active`, `past`, `future`
    * Grundlegende CSS-Anpassungen
        * Globaler Hintergrund
        * Standard-Styling für `.step`-Elemente (Dimensionen, Abstände, Farben, Typografie)
        * Styling für spezifische Steps über ihre ID
    * Styling der Übergänge (CSS Transitions auf `transform`)
        * `transition-property`, `transition-duration`, `transition-timing-function`
    * Fortgeschrittenes Styling für individuelle Looks und Animationen
        * Styling basierend auf `active`, `past`, `future` Klassen
        * Styling für den Overview-Modus
        * CSS-Keyframe-Animationen (`@keyframes`) innerhalb von Steps
        * Verwendung von Pseudo-Elementen
        * Responsive Gestaltung von Steps (Herausforderungen und Ansätze)

7.  **[Teil 7: Die impress.js API und Ereignisbehandlung](#teil-7-die-impressjs-api-und-ereignisbehandlung)**
    * Einführung in die impress.js JavaScript-API (Zugriff auf das API-Objekt)
    * Die `init()` Methode im Detail
        * Das Konfigurationsobjekt (`width`, `height`, `maxScale`, `minScale`, `perspective`, `transitionDuration`)
        * Technische Details des Initialisierungsprozesses
    * Navigationsmethoden der API im Detail
        * `api.next()`
        * `api.prev()`
        * `api.goto(el, duration?)` (DOM-Element, ID-String, numerischer Index, optionale Dauer)
        * `api.getActiveStep()`
    * Ereignisbehandlung (`EventListeners`) im Detail
        * Registrierung von Event-Listenern (auf dem Root-Element)
        * Das `event.detail`-Objekt
        * Wichtige Core-Events: `impress:init`, `impress:stepenter`, `impress:stepleave`, `impress:steprefresh`
        * Mögliche Events für den Overview-Modus (`impress:overview:enter`, `impress:overview:leave`)
        * Reihenfolge der Events
    * Beispiele für die dynamische Manipulation der Präsentation zur Laufzeit
        * Benutzerdefinierte Navigationsbuttons
        * Dynamische Inhaltsänderung beim Betreten eines Steps
        * Aktualisierung einer Fortschrittsanzeige
    * Die `impress().tear()` Methode (Aufräumen – Diskussion der Verfügbarkeit und Notwendigkeit)

8.  **[Teil 8: Offizielle Plugins – Teil 1](#teil-8-offizielle-plugins---teil-1)**
    * Einführung in die Plugin-Architektur (Zweck, Funktionsweise, Integration, Konfiguration)
    * Detaillierte Vorstellung, Integration und Anwendung von:
        * **`autoplay` Plugin**: Zweck, `data-autoplay`, JS-Konfiguration (`interval`, `direction`), Steuerung, Beispiel
        * **`blackout` Plugin**: Zweck, Tastenkürzel (`.` oder `B`), CSS-Klasse `impress-blackout`, Styling, Beispiel
        * **`bookmarks` Plugin**: Zweck, `data-bookmark-id`, URL-Hash-Nutzung (`#bookmarkName`), Unterschied zu Step-IDs, Beispiel
        * **`extras` Plugin** (und verwandte Funktionen):
            * `skip`-Funktionalität (CSS-Klasse `.skip`, Verhalten)
            * `substep`-Funktionalität (CSS-Klasse `.substep`, Verhalten, zugehörige CSS-Klassen wie `.substep-active`, `.substep-visible`)
            * `goto`-Tastenkürzel (`G`)
            * `help`-Tastenkürzel (`H` oder `?`)
            * Konfigurationsmöglichkeiten für `extras`

9.  **[Teil 9: Offizielle Plugins – Teil 2](#teil-9-offizielle-plugins---teil-2)**
    * Detaillierte Vorstellung, Integration und Anwendung von:
        * **`navigation` / `navigation-ui` Plugins**: Zweck, API-Erweiterungen (`goto` mit Keywords), UI-Elemente (Pfeile), HTML-Struktur, CSS-Klassen, Konfiguration (`showNextPrev` etc.), Beispiel
        * **`progress` Plugin**: Zweck, HTML-Struktur (`impress-progressbar`), CSS-Styling, Funktionsweise, Konfiguration, Beispiel
        * **`rel` Plugin**: Zweck, relative Positionierung (`data-rel-x/y/z/rotate/scale`), Funktionsweise (Kettenreaktion), Beispiel
        * **`resize` Plugin**: Zweck, Anpassung an Fenstergröße, Funktionsweise, Konfiguration
        * **`stop` Plugin**: Zweck, CSS-Klasse `stop`, Funktionsweise für Präsentationsende
        * **`toolbar` Plugin**: Zweck, dynamische HTML-Toolbar, Inhalte (Navigation, Progress, Menü), CSS-Styling, Abhängigkeiten, Konfiguration (`bar`, `style`), Beispiel
        * **`touch` Plugin / `mobile` Plugin**: Zweck, Touch-Gesten (Swipe, Pinch), Viewport-Optimierung, Konfiguration (`swipeThreshold`), Wichtigkeit für mobile Geräte

10. **[Teil 10: Best Practices, nicht-lineares ZUI-Design & weiterführende Tipps](#teil-10-best-practices-nicht-lineares-zui-design--weiterfuehrende-tipps)**
    * Design-Prinzipien für effektive nicht-lineare ZUI-Präsentationen
        * Klarheit vor Spektakel (Content First)
        * Struktur und Storytelling in nicht-linearen Räumen (Mindmap, Pfade, Anker)
        * Lesbarkeit und Zugänglichkeit (Kontraste, Schrift, Animationen, Motion Sickness)
        * Konsistenz im Design
        * Nutzung des Raumes (2D und 3D) mit Bedacht
    * Performance-Überlegungen bei komplexen Präsentationen
        * Anzahl der Steps, Optimierung von Inhalten (Bilder, Videos)
        * Komplexe CSS-Effekte, viele DOM-Elemente
        * JavaScript-Interaktionen und Hardwarebeschleunigung
        * Testen auf Zielgeräten
    * Häufige Fehler und deren Vermeidung (Troubleshooting-Ansätze)
        * Steps nicht sichtbar/falsch positioniert
        * Übergänge ruckelig/fehlerhaft
        * 3D-Effekte flach
        * Navigation fehlerhaft
        * Schrift unscharf
    * Kreative Anwendungsbeispiele und Inspiration
    * Wo man weitere Hilfe und Ressourcen findet (Offizielle Doku, GitHub Issues/Discussions, Stack Overflow)
    * Zusammenfassung der Kernstärken von `impress.js`
    * Abschließende motivierende Worte<<</md>
 
 
## Teil 1: Einführung in impress.js

Willkommen zum ersten Teil unseres umfassenden Tutorials zu `impress.js`\! In dieser Serie wirst du lernen, wie du beeindruckende, nicht-lineare Präsentationen mit Zooming User Interface (ZUI) Effekten erstellen kannst.

### Was ist `impress.js`? Philosophie und Kernkonzept (ZUI)

**`impress.js`** ist ein Präsentations-Framework, das auf der Leistungsfähigkeit von CSS3-Transformationen und -Übergängen in modernen Browsern basiert. Inspiriert wurde es von der Idee hinter prezi.com. Es ermöglicht dir, deine Präsentationsfolien – hier "Steps" genannt – auf einer unendlich erscheinenden 2D-Leinwand oder in einem 3D-Raum zu positionieren, zu drehen und zu skalieren.

Die **Kernphilosophie** von `impress.js` ist es, Präsentationen als eine Art **Zooming User Interface (ZUI)** zu gestalten. Anstatt einer starren, linearen Abfolge von Folien, können sich die Zuschauer durch eine dynamische Landschaft von Ideen bewegen. Große Konzepte können wortwörtlich groß dargestellt werden, während Details herangezoomt oder kleinere Ideen in den Kontext größerer Bilder eingebettet werden können. Die einzige Grenze ist deine Vorstellungskraft\!

Stell dir vor, deine Präsentation ist nicht nur eine Reihe von Dias, sondern eine interaktive Reise, bei der du das Publikum auf Entdeckungstour mitnimmst, hineinzoomst, um Details zu enthüllen, und herauszoomst, um das große Ganze zu zeigen.

### Vorteile für nicht-lineare Präsentationen

Der größte Vorteil von `impress.js` liegt in seiner Fähigkeit, **nicht-lineare Präsentationen** auf eine visuell ansprechende Weise umzusetzen.

  * **Flexibler Erzählfluss**: Du bist nicht an eine strikte Reihenfolge gebunden. Du kannst logische Sprünge zwischen Themen machen, Übersichten einblenden und je nach Bedarf des Publikums von einem Punkt zum anderen navigieren.
  * **Visuelle Hierarchien und Beziehungen**: Durch die räumliche Anordnung und Skalierung von Steps kannst du intuitiv Zusammenhänge und Hierarchien zwischen verschiedenen Informationseinheiten darstellen.
  * **Hoher Engagement-Faktor**: Die dynamischen Übergänge und Zoom-Effekte können das Publikum fesseln und die Präsentation erinnerungswürdiger machen als traditionelle, statische Slideshows.
  * **Kreative Freiheit**: `impress.js` gibt dir die Werkzeuge an die Hand, um deine Inhalte auf einzigartige und kreative Weise zu visualisieren.

### Grundlegendes Setup

Um mit `impress.js` zu starten, benötigst du nur grundlegende HTML-, CSS- und optional JavaScript-Kenntnisse.

**1. Einbinden der Bibliothek:**

Du kannst `impress.js` entweder herunterladen und lokal einbinden oder ein Content Delivery Network (CDN) nutzen. Für dieses Tutorial verwenden wir einen CDN-Link. Achte darauf, dass du für eine Präsentation ohne Internetzugang die Datei herunterladen solltest.

Hier ist ein CDN-Link zur Version 2.0.0 (eine stabile und weit verbreitete Version). Gemäß deiner Anweisung wird kein `integrity`-Attribut verwendet:

```html
<script src="https://cdn.jsdelivr.net/gh/impress/impress.js@2.0.0/js/impress.js"></script>
```

Diese Zeile bindet die `impress.js`-Datei in deine HTML-Seite ein. Du platzierst diesen `<script>`-Tag am besten am Ende deines `<body>`-Tags, damit die HTML-Struktur zuerst geladen wird.

**2. Minimale HTML-Struktur:**

Eine grundlegende `impress.js`-Präsentation hat eine sehr einfache HTML-Struktur:

```html
<!doctype html>
<html lang="de">
<head>
    <meta charset="utf-8" />
    <title>Meine erste impress.js Präsentation</title>
    <link href="css/meine-styles.css" rel="stylesheet" /> </head>
<body class="impress-not-supported">

    <div class="fallback-message">
        <p>Deine Browserversion unterstützt die für <b>impress.js</b> benötigten Features leider nicht.</p>
        <p>Für das beste Erlebnis empfehlen wir die aktuellste Version von <b>Chrome</b>, <b>Safari</b> oder <b>Firefox</b>.</p>
    </div>

    <div id="impress">

        <div id="start" class="step" data-x="0" data-y="0">
            <h1>Hallo impress.js!</h1>
            <p>Dies ist mein erster Step.</p>
        </div>

        </div>

    <script src="https://cdn.jsdelivr.net/gh/impress/impress.js@2.0.0/js/impress.js"></script>
    <script>
        impress().init(); // Initialisiert impress.js
    </script>

</body>
</html>
```

**Wichtige Punkte der HTML-Struktur:**

  * **`<body>`-Klasse `impress-not-supported`**: Diese Klasse wird verwendet, um eine Fallback-Nachricht für Browser anzuzeigen, die `impress.js` nicht unterstützen. `impress.js` entfernt diese Klasse, wenn es erfolgreich startet.
  * **`<div class="fallback-message">`**: Enthält die Nachricht, die angezeigt wird, wenn `impress.js` nicht läuft.
  * **`<div id="impress">`**: Der Hauptcontainer für alle deine Präsentations-Steps. Die ID `impress` ist standardmäßig erforderlich, damit die Bibliothek funktioniert.
  * **`<div class="step">`**: Jeder einzelne "Step" (oder Folie) deiner Präsentation. Du kannst diesen `div`s IDs geben, um sie später leichter ansprechen zu können (z.B. für direkte Navigation oder spezifisches Styling).
  * **Datenattribute**: Attribute wie `data-x`, `data-y`, `data-z`, `data-rotate`, `data-scale` etc. (die wir in späteren Teilen detailliert behandeln) definieren die Position, Größe und Ausrichtung jedes Steps.
  * **Initialisierung**: Nach dem Einbinden der `impress.js`-Datei musst du die Funktion `impress().init();` aufrufen, um die Präsentation zu starten.

**3. Optionale CSS-Dateien:**

Obwohl `impress.js` die notwendigen CSS-Transformationen dynamisch generiert, möchtest du wahrscheinlich das Aussehen deiner Präsentation anpassen.

  * `impress-common.css`: Enthält einige grundlegende Stile, die nützlich sein können. Du findest sie im `css`-Ordner des GitHub-Repositorys.
  * `impress-demo.css`: Enthält die Stile für die offizielle Demo. Gut als Inspiration, aber nicht zwingend notwendig.
  * **Eigene CSS-Datei**: Erstelle eine eigene CSS-Datei (z.B. `meine-styles.css`), um das Aussehen deiner Steps individuell zu gestalten.

Du kannst diese CSS-Dateien im `<head>` deiner HTML-Datei verlinken. Für den Anfang ist keine zusätzliche CSS-Datei zwingend erforderlich, um die Funktionsweise von `impress.js` zu testen.

### Lizenz und Community

`impress.js` wurde ursprünglich von Bartek Szopka erstellt und wird jetzt von einer Community von Entwicklern weitergeführt, maßgeblich durch Henrik Ingo.

  * **Lizenz**: `impress.js` ist unter der **MIT-Lizenz** veröffentlicht. Das bedeutet, du kannst es frei für private und kommerzielle Projekte verwenden, modifizieren und weitergeben, solange du den Copyright-Hinweis und die Lizenzbedingungen beibehältst.
  * **Community und Bezugsquellen**:
      * Die offizielle Webseite (und Demo) findest du unter [impress.js.org](https://impress.js.org/).
      * Der Quellcode und die weitere Entwicklung finden auf **GitHub** statt: [github.com/impress/impress.js](https://github.com/impress/impress.js). Hier findest du auch die `README.md`, `GettingStarted.md` und weitere Dokumentationen.


## Teil 2: Erste Schritte mit impress.js

In diesem Teil werden wir die grundlegende HTML-Struktur einer `impress.js`-Präsentation bis ins kleinste Detail untersuchen, deine erste eigene Präsentation mit einigen Steps erstellen und die Initialisierung von `impress.js` verstehen lernen.

### Die grundlegende HTML-Struktur einer `impress.js`-Präsentation im Detail

Jede Webseite beginnt mit einer HTML-Grundstruktur. Für `impress.js` gibt es einige spezifische Elemente und Konventionen, die wichtig sind.

**1. Dokumenttyp und Wurzelelement:**

  * **`<!doctype html>`**: Diese Deklaration steht immer am Anfang deiner HTML-Datei. Sie teilt dem Browser mit, dass es sich um ein HTML5-Dokument handelt. Das ist wichtig, damit moderne Browserfunktionen korrekt interpretiert werden.
  * **`<html lang="de">`**: Das `<html>`-Tag ist das Wurzelelement jeder HTML-Seite.
      * Das Attribut `lang="de"` (oder eine andere Sprache wie `en` für Englisch) ist wichtig für die Barrierefreiheit und Suchmaschinen. Es gibt die Hauptsprache des Dokuments an.

**2. Der `<head>`-Bereich:**

Der `<head>`-Bereich enthält Metainformationen über dein HTML-Dokument, die nicht direkt auf der Seite angezeigt werden, aber für den Browser und Suchmaschinen wichtig sind.

  * **`<meta charset="utf-8" />`**: Dieses Meta-Tag deklariert die Zeichenkodierung des Dokuments. `UTF-8` ist eine universelle Zeichenkodierung, die fast alle Zeichen und Symbole der Welt unterstützt und dringend empfohlen wird, um Probleme mit Sonderzeichen zu vermeiden.
  * **`<title>Meine erste impress.js Präsentation</title>`**: Der Inhalt des `<title>`-Tags wird in der Titelleiste des Browsers oder im Tab-Titel angezeigt. Er ist auch wichtig für Suchmaschinen und Lesezeichen. Wähle einen aussagekräftigen Titel für deine Präsentation.
  * **Optionale Meta-Tags**:
      * `<meta name="description" content="Eine kurze Beschreibung meiner Präsentation.">`: Hilfreich für Suchmaschinen.
      * `<meta name="author" content="Dein Name">`: Gibt den Autor des Dokuments an.
  * **CSS-Verknüpfungen**:
      * Hier verlinkst du externe CSS-Dateien. Für `impress.js` könntest du hier später Stile für das Aussehen deiner Präsentation definieren.
        ````html
        <link href="css/impress-common.css" rel="stylesheet" /> <link href="css/meine-styles.css" rel="stylesheet" /> ```
        Die Datei `impress-common.css` (aus dem `css`-Verzeichnis des `impress.js`-Pakets) enthält einige nützliche Standardstile. Es ist ratsam, sie einzubinden, wenn du nicht bei Null anfangen möchtest. Deine eigenen Stile (z.B. in `meine-styles.css`) definieren das spezifische Aussehen deiner Präsentation. Für den Anfang sind diese CSS-Dateien jedoch nicht zwingend erforderlich, um die grundlegende Funktionalität zu testen.

        ````

**3. Der `<body>`-Tag:**

Der `<body>`-Tag enthält den gesamten sichtbaren Inhalt deiner Webseite.

  * **`<body class="impress-not-supported">`**:

      * Dem `<body>`-Tag wird initial die Klasse `impress-not-supported` zugewiesen.
      * **Zweck**: Diese Klasse dient als Haken (Hook) für CSS, um eine Fallback-Nachricht anzuzeigen, falls der Browser die für `impress.js` notwendigen Technologien (insbesondere CSS3 3D Transforms) nicht unterstützt oder JavaScript deaktiviert ist.
      * **Verhalten**: Wenn `impress.js` erfolgreich initialisiert wird, entfernt es diese Klasse automatisch vom `<body>`-Element. Dadurch wird die Fallback-Nachricht (siehe nächster Punkt) ausgeblendet und die Präsentation sichtbar.

  * **`<div class="fallback-message">`**:

      * Dieses `<div>`-Element enthält die Nachricht, die Benutzern angezeigt wird, deren Browser `impress.js` nicht korrekt darstellen können.
      * **Inhalt**: Typischerweise enthält es eine Entschuldigung und den Hinweis, einen modernen Browser (wie aktuelle Versionen von Chrome, Safari oder Firefox) zu verwenden.
      * **Styling**: Du kannst dieses `div` mit CSS so gestalten, dass es z.B. zentriert und gut lesbar auf der Seite erscheint, wenn die Klasse `impress-not-supported` am `body` aktiv ist.
        ```html
        <div class="fallback-message">
            <p>Deine Browserversion unterstützt die für <b>impress.js</b> benötigten Features leider nicht.</p>
            <p>Für das beste Erlebnis empfehlen wir die aktuellste Version von <b>Chrome</b>, <b>Safari</b> oder <b>Firefox</b>.</p>
        </div>
        ```

  * **Der Hauptcontainer: `<div id="impress">`**:

      * Dies ist das **Herzstück** deiner `impress.js`-Präsentation. Es ist der Container, der alle einzelnen Präsentations-Steps ("Folien") umschließt.
      * **ID `impress`**: Standardmäßig sucht `impress.js` nach einem Element mit der ID `impress`. Es ist essenziell, dass dieses Element existiert und diese ID trägt, damit die Bibliothek korrekt funktioniert.
      * **Konfigurierbarkeit der ID (für Fortgeschrittene)**: Obwohl `impress` die Standard-ID ist, kann `impress.js` theoretisch auch mit einer anderen Root-ID initialisiert werden. Dies geschieht, indem man die ID an die `impress()` Funktion übergibt, z.B. `impress("meinRootElement").init();`. Für den Anfang und die meisten Anwendungsfälle ist `id="impress"` jedoch die beste und einfachste Wahl.
      * **Funktion**: `impress.js` verwendet diesen Container als seine "Leinwand" oder "Bühne". Die Transformationen der Steps (Positionierung, Drehung, Skalierung) finden relativ zu diesem Container statt.

### Der "Step" im Detail

Innerhalb des `<div id="impress">`-Containers definierst du die einzelnen "Folien" deiner Präsentation, die in `impress.js` als "Steps" bezeichnet werden.

  * **Jeder Step ist ein `<div>`-Element**: Die semantisch korrekteste und gebräuchlichste Art, einen Step zu definieren, ist die Verwendung eines `<div>`-Elements.

    ```html
    <div class="step">
        </div>
    ```

  * **Die obligatorische Klasse `step`**:

      * Jedes Element, das einen Präsentations-Step darstellen soll, **muss** die CSS-Klasse `step` besitzen.
      * `impress.js` identifiziert alle Elemente mit dieser Klasse innerhalb des Hauptcontainers als einzelne Schritte der Präsentation.

  * **Optionale, aber empfohlene `id` für jeden Step**:

      * Obwohl nicht zwingend erforderlich, ist es eine sehr gute Praxis, jedem Step eine **eindeutige `id`** zuzuweisen.
        ```html
        <div id="mein-erster-step" class="step" data-x="0" data-y="0">
            <h2>Titel des ersten Steps</h2>
            <p>Inhalt...</p>
        </div>
        <div id="noch-ein-step" class="step" data-x="1000" data-y="0">
            <p>Anderer Inhalt...</p>
        </div>
        ```
      * **Vorteile einer eindeutigen ID**:
        1.  **Direkte Verlinkung/Navigation**: Du kannst direkt zu einem Step springen, indem du seine ID im URL-Hash angibst (z.B. `meinepraesentation.html#/noch-ein-step`).
        2.  **Spezifisches CSS-Styling**: Du kannst einzelne Steps gezielt über ihre ID mit CSS ansprechen und ihnen ein einzigartiges Aussehen verleihen.
        3.  **API-Nutzung**: Die `impress.js`-API (die wir später behandeln) erlaubt es, über die ID zu spezifischen Steps zu navigieren (z.B. `impress().goto("noch-ein-step");`).
        4.  **Semantik und Übersichtlichkeit**: Eindeutige IDs machen deinen HTML-Code lesbarer und besser strukturierbar.

  * **Inhalt eines Steps**:

      * Innerhalb eines `<div class="step">` kannst du **beliebigen HTML-Inhalt** platzieren. Das umfasst Überschriften (`<h1>`-`<h6>`), Absätze (`<p>`), Listen (`<ul>`, `<ol>`), Bilder (`<img>`), Videos (`<video>`), Zitate (`<blockquote>`), Code-Blöcke (`<pre>`, `<code>`) und vieles mehr.
      * Die Gestaltung und das Layout des Inhalts innerhalb eines Steps erfolgt mit Standard-HTML und CSS. `impress.js` kümmert sich primär um die Positionierung und Transformation des gesamten Step-Containers.

  * **Minimale Datenattribute für den Anfang**:

      * Um deine Steps auf der unendlichen Leinwand zu positionieren, verwendest du `data-*`-Attribute. Für den Anfang sind `data-x` und `data-y` die wichtigsten.
        ```html
        <div id="step-1" class="step" data-x="0" data-y="0"> ... </div>
        ```
      * `data-x="0"`: Setzt die horizontale Position des Steps.
      * `data-y="0"`: Setzt die vertikale Position des Steps.
      * Diese und weitere Attribute wie `data-z` (für die Tiefe), `data-rotate-x`, `data-rotate-y`, `data-rotate-z` (für Drehungen) und `data-scale` (für die Größe) werden wir in Teil 3 und 4 detailliert besprechen. Für unsere erste einfache Präsentation reichen `data-x` und `data-y`, um die Steps anzuordnen. Die Werte sind pixelbasiert.

### Erstellen der ersten einfachen Präsentation

Lass uns nun das Gelernte zusammenfügen und eine minimale Präsentation mit drei Steps erstellen.

**Beispiel-HTML (`meine_praesentation.html`):**

```html
<!doctype html>
<html lang="de">
<head>
    <meta charset="utf-8" />
    <title>Meine erste impress.js Präsentation</title>
    <style>
        /* Grundlegendes Styling, um die Steps sichtbar zu machen */
        .step {
            width: 900px; /* Breite eines Steps */
            padding: 40px;
            border: 1px solid rgba(0, 0, 0, .3);
            border-radius: 10px;
            box-shadow: 0 2px 6px rgba(0, 0, 0, .1);
            color: rgb(52, 52, 52);
            font-family: sans-serif;
            background-color: rgba(255, 255, 255, 0.9);
            display: block; /* Wichtig für impress.js, um die Transformationen korrekt anzuwenden */
        }

        /* Styling für die Fallback-Nachricht */
        .fallback-message {
            font-family: sans-serif;
            line-height: 1.3;
            width: 780px;
            padding: 10px 10px 0;
            margin: 20px auto;
            border: 1px solid #E4C66E;
            border-radius: 10px;
            background: #EFE8C4;
        }
        .fallback-message p {
            margin-bottom: 10px;
        }
        .impress-not-supported .fallback-message {
            display: block; /* Wird angezeigt, wenn impress.js nicht unterstützt wird */
        }
        body:not(.impress-not-supported) .fallback-message {
            display: none; /* Wird ausgeblendet, wenn impress.js läuft */
        }
    </style>
</head>
<body class="impress-not-supported">

    <div class="fallback-message">
        <p>Deine Browserversion unterstützt die für <b>impress.js</b> benötigten Features leider nicht.</p>
        <p>Für das beste Erlebnis empfehlen wir die aktuellste Version von <b>Chrome</b>, <b>Safari</b> oder <b>Firefox</b>.</p>
    </div>

    <div id="impress">

        <div id="step-1" class="step" data-x="0" data-y="0">
            <h1>Willkommen!</h1>
            <p>Dies ist der <strong>erste Step</strong> meiner impress.js Präsentation.</p>
            <p>Wir positionieren ihn bei (0, 0).</p>
        </div>

        <div id="step-2" class="step" data-x="1200" data-y="0">
            <h2>Zweiter Step</h2>
            <p>Dieser Step befindet sich <strong>rechts</strong> vom ersten Step.</p>
            <p>Position: (1200, 0)</p>
        </div>

        <div id="step-3" class="step" data-x="0" data-y="1000">
            <h2>Dritter Step</h2>
            <p>Und dieser Step ist <strong>unterhalb</strong> des ersten Steps positioniert.</p>
            <p>Position: (0, 1000)</p>
        </div>

    </div>

    <script src="https://cdn.jsdelivr.net/gh/impress/impress.js@2.0.0/js/impress.js"></script>
    <script>
        impress().init();
    </script>

</body>
</html>
```

**Erläuterung des Beispiels:**

  * **Styling**: Ich habe minimales CSS direkt in den `<style>`-Tag im `<head>` eingefügt, damit die Steps überhaupt sichtbar sind und eine definierte Größe haben. Normalerweise würdest du dies in eine externe CSS-Datei auslagern. Das `display: block;` für `.step` ist wichtig, da `impress.js` standardmäßig erwartet, dass die Steps Block-Level-Elemente sind, um Dimensionen und Transformationen korrekt zu handhaben.
  * **Step 1 (`id="step-1"`)**:
      * `data-x="0" data-y="0"`: Dieser Step befindet sich am Ursprung des Koordinatensystems (oben links auf der "Leinwand").
  * **Step 2 (`id="step-2"`)**:
      * `data-x="1200" data-y="0"`: Dieser Step wird 1200 Pixel nach rechts vom Ursprung verschoben (da `data-y` weiterhin 0 ist). Da unser erster Step 900px breit ist und 40px Padding auf jeder Seite hat (also 900 + 80 = 980px Gesamtbreite), wird ein Wert von `1200` sicherstellen, dass er rechts daneben platziert wird, mit etwas Abstand.
  * **Step 3 (`id="step-3"`)**:
      * `data-x="0" data-y="1000"`: Dieser Step wird 1000 Pixel nach unten vom Ursprung verschoben (da `data-x` 0 ist). Er erscheint also unterhalb des ersten Steps.

Wenn du diese HTML-Datei in einem modernen Browser öffnest, solltest du den ersten Step sehen. Mit den Pfeiltasten (oder Leertaste für vorwärts, Shift+Leertaste für rückwärts) kannst du zwischen den Steps navigieren. Du wirst sehen, wie `impress.js` die Ansicht verschiebt und sanfte Übergänge erzeugt.

### Initialisierung von `impress.js`

Wie im Beispielcode gezeigt, erfolgt die Initialisierung von `impress.js` durch einen einfachen JavaScript-Aufruf:

```html
<script src="https://cdn.jsdelivr.net/gh/impress/impress.js@2.0.0/js/impress.js"></script>
<script>
    impress().init();
</script>
```

**Wichtige Details zur Initialisierung:**

1.  **Platzierung der Skripte**:

      * Das `<script src=".../impress.js"></script>`-Tag, das die `impress.js`-Bibliothek lädt, sollte **vor** dem Script-Block platziert werden, der `impress().init();` aufruft.
      * Beide Skript-Tags werden üblicherweise **am Ende des `<body>`-Elements** platziert, kurz vor dem schließenden `</body>`-Tag.
          * **Grund**: Dies stellt sicher, dass das gesamte HTML-Dokument (insbesondere der `<div id="impress">`-Container und alle `class="step"`-Elemente) vom Browser geladen und geparst wurde, bevor `impress.js` versucht, darauf zuzugreifen und es zu manipulieren. Würde man die Skripte im `<head>` ohne spezielle Attribute wie `defer` platzieren, könnte `impress.js` versuchen, auf Elemente zuzugreifen, die noch nicht existieren, was zu Fehlern führen würde.

2.  **Der Aufruf `impress().init();`**:

      * `impress()`: Diese Funktion ist der Einstiegspunkt zur `impress.js`-API. Wenn sie ohne Argumente aufgerufen wird, sucht sie standardmäßig nach einem Element mit der ID `impress` als Wurzel-Element für die Präsentation.
      * `.init()`: Diese Methode wird auf dem von `impress()` zurückgegebenen API-Objekt aufgerufen und startet den Initialisierungsprozess.
      * **Was passiert bei `init()` im Detail?**
          * `impress.js` prüft, ob der Browser die benötigten Features unterstützt.
          * Es sucht im DOM nach dem Wurzelelement (standardmäßig `#impress`).
          * Es sammelt alle Kindelemente des Wurzelelements, die die Klasse `step` haben.
          * Für jeden gefundenen Step liest es die `data-*`-Attribute aus, um Position, Rotation, Skalierung etc. zu bestimmen.
          * Es berechnet die notwendigen CSS-Transformationen für jeden Step.
          * Es fügt dem `<html>`-Element und dem `<body>`-Element spezifische Klassen hinzu (z.B. `impress-supported`, `impress-enabled`) und entfernt `impress-not-supported` vom `body`, wenn alles erfolgreich war.
          * Es richtet die Event-Listener für Tastatur- und Mausnavigation ein.
          * Es positioniert den ersten Step im Ansichtsfenster.
          * Es löst das `impress:init`-Event auf dem Wurzelelement aus, falls andere Skripte oder Plugins darauf reagieren müssen.

3.  **Konfiguration bei der Initialisierung (Ausblick)**:

      * Die `impress()`-Funktion kann ein Konfigurationsobjekt als optionalen Parameter akzeptieren. Damit lassen sich verschiedene Aspekte von `impress.js` anpassen, z.B. die Breite und Höhe der Steps, Übergangsdauer, Perspektive etc.
        ```javascript
        impress().init({
            width: 1024,
            height: 768,
            // weitere Optionen
        });
        ```
      * Dies ist ein fortgeschritteneres Thema, das wir später behandeln werden. Für den Anfang ist der parameterlose Aufruf `impress().init();` ausreichend und verwendet die Standardeinstellungen.

4.  **Verwendung einer benutzerdefinierten Root-ID**:

      * Wenn du aus irgendeinem Grund nicht die ID `impress` für deinen Hauptcontainer verwenden möchtest (oder kannst), kannst du `impress.js` anweisen, eine andere ID zu verwenden:
        ```html
        <div id="meine-praesentation-wurzel">
            </div>

        <script src="https://cdn.jsdelivr.net/gh/impress/impress.js@2.0.0/js/impress.js"></script>
        <script>
            impress("meine-praesentation-wurzel").init();
        </script>
        ```
      * Hier wird `impress()` mit dem String `"meine-praesentation-wurzel"` aufgerufen, was `impress.js` anweist, dieses Element als Basis zu nehmen.

### Verständnis des Hauptcontainers und der einzelnen Steps

Zum Abschluss dieses Teils fassen wir noch einmal die Rollen der Hauptelemente zusammen:

  * **`<div id="impress">` (Der Hauptcontainer/Die Leinwand)**:

      * Dies ist deine virtuelle Bühne oder unendliche Leinwand. Alle deine Steps "leben" innerhalb dieses Containers.
      * `impress.js` wendet globale Transformationen und Perspektiveinstellungen auf diesen Container an, um den 3D-Raum zu simulieren, in dem sich deine Steps bewegen.
      * Die Größe dieses Containers kann das Standardverhalten der Step-Skalierung beeinflussen, wenn keine expliziten Skalierungswerte für Steps angegeben sind (Details dazu später).

  * **`<div class="step">` (Die einzelnen Präsentations-Steps)**:

      * Jeder Step ist eine eigenständige Einheit deiner Präsentation.
      * `impress.js` positioniert, dreht und skaliert jeden dieser `div`s individuell basierend auf seinen `data-*`-Attributen.
      * Die Übergänge zwischen den Steps (das "Fliegen" von einem zum anderen) werden durch CSS-Transitionen realisiert, die `impress.js` auf diese Step-Elemente anwendet. `impress.js` fügt und entfernt Klassen wie `active`, `past` und `future`, um diese Übergänge zu steuern.
          * Der `active` Step ist der aktuell sichtbare.
          * `past` Steps wurden bereits besucht.
          * `future` Steps kommen noch.

  * **Reihenfolge der Steps im HTML**:

      * Die Reihenfolge, in der du die `<div class="step">`-Elemente in deiner HTML-Datei notierst, bestimmt die **Standard-Navigationsreihenfolge**, wenn du die Pfeiltasten (rechts/links) oder die Leertaste/Shift+Leertaste benutzt und keine spezifischen Navigationspfade (z.B. über `goto` oder das `rel`-Plugin) definiert hast. Der erste Step im HTML ist der Start-Step, der nächste Step im HTML wird der zweite usw.

Mit diesem Wissen bist du nun gut gerüstet, um die Positionierung und Transformation deiner Steps im Detail zu erkunden, was wir in den nächsten Teilen tun werden.



## Teil 3: Positionierung von Steps im 2D- und 3D-Raum

Nachdem wir im zweiten Teil die grundlegende Struktur einer `impress.js`-Präsentation kennengelernt haben, wollen wir uns nun dem Herzstück der ZUI-Funktionalität widmen: der präzisen Platzierung deiner "Steps" (Folien) auf der unendlichen Präsentationsleinwand. `impress.js` ermöglicht es dir, Steps nicht nur nebeneinander, sondern auch in die Tiefe des Raumes zu verschieben, was faszinierende 3D-Effekte erzeugt.

### Das Koordinatensystem von `impress.js` im Detail

Um Steps gezielt positionieren zu können, musst du das zugrundeliegende Koordinatensystem verstehen.

  * **Die Leinwand (`<div id="impress">`)**: Stell dir den Hauptcontainer deiner Präsentation, also das `<div>` mit der ID `impress`, als eine unendlich große, dreidimensionale Bühne vor. Alle deine Steps werden relativ zu dieser Bühne positioniert.

  * **Der Ursprungspunkt (0, 0, 0)**:

      * Standardmäßig liegt der Ursprung dieses Koordinatensystems (der Punkt, an dem X=0, Y=0 und Z=0 ist) **in der Mitte des Ansichtsfensters (Viewport)**, wenn die Präsentation geladen wird, bevor irgendwelche globalen Transformationen auf den `impress`-Container angewendet werden.
      * Der erste Step deiner Präsentation (also das erste `<div class="step">` im HTML), wenn er keine expliziten Koordinaten (`data-x`, `data-y`, `data-z`) hat, wird standardmäßig um diesen Ursprung herum zentriert. Das bedeutet, die Mitte des ersten Steps liegt bei (0,0,0).
      * Wenn du dem ersten Step explizite Koordinaten gibst (z.B. `data-x="0" data-y="0" data-z="0"`), dann wird die obere linke Ecke dieses Steps am Ursprung des Koordinatensystems der *Leinwand* ausgerichtet (bevor Skalierungen oder Rotationen angewendet werden). Die Kamera blickt dann auf diesen Punkt.

  * **Die Achsen**: `impress.js` verwendet ein rechtshändiges Koordinatensystem, wie es in vielen 3D-Grafikanwendungen üblich ist.

      * **X-Achse**: Verläuft horizontal.
          * Positive Werte verschieben den Step nach **rechts**.
          * Negative Werte verschieben den Step nach **links**.
      * **Y-Achse**: Verläuft vertikal.
          * Positive Werte verschieben den Step nach **unten**.
          * Negative Werte verschieben den Step nach **oben**.
            (Beachte: Dies ist eine gängige Konvention in der Computergrafik, wo der Ursprung oft oben links ist und die Y-Achse nach unten positiv verläuft.)
      * **Z-Achse**: Stellt die Tiefe dar und verläuft senkrecht zum Bildschirm.
          * Positive Werte verschieben den Step **näher zum Betrachter** (als ob er "aus dem Bildschirm herauskommt").
          * Negative Werte verschieben den Step **weiter weg vom Betrachter** (als ob er "in den Bildschirm hineingeht").

  * **Einheiten**: Die Werte, die du für die Positionierungsattribute (siehe unten) angibst, werden in der Regel als **Pixel (px)** interpretiert. Ein `data-x="1000"` bedeutet also eine Verschiebung um 1000 Pixel entlang der X-Achse.

  * **Visualisierung des Koordinatensystems (aus Sicht des Betrachters auf den Bildschirm):**

    ```
          ^ -Y (Oben)
          |
          |
    -X <---- O ----> +X (Rechts)
          | (0,0,0)
          |
          v +Y (Unten)

    Z-Achse:
    ⊙ (Punkt) : +Z (kommt auf dich zu)
    ⊗ (Kreuz)  : -Z (geht von dir weg, in den Bildschirm hinein)
    ```

### Datenattribute zur Positionierung im Detail

`impress.js` verwendet HTML5-`data-*`-Attribute, um die Eigenschaften jedes Steps zu definieren. Für die Positionierung sind dies:

  * **`data-x` (Horizontale Position)**

      * Dieses Attribut definiert die Position des Steps entlang der X-Achse.
      * Es ist ein numerischer Wert (Pixel).
      * **Beispiel**:
        ```html
        <div class="step" data-x="0">Step am Ursprung (horizontal)</div>
        <div class="step" data-x="1000">Step 1000px rechts vom Ursprung</div>
        <div class="step" data-x="-500">Step 500px links vom Ursprung</div>
        ```
      * **Interaktion mit der Step-Breite**: Der `data-x`-Wert bezieht sich auf den Ankerpunkt des Steps (standardmäßig die obere linke Ecke, bevor Rotationen angewendet werden). Wenn du Steps nebeneinander platzieren möchtest, ohne dass sie sich überlappen, musst du die Breite deiner Steps (definiert durch CSS oder die Standardbreite von `impress.js`) in deine Berechnungen einbeziehen. Die Standardbreite eines Steps in `impress.js` (ohne eigenes CSS) ist oft durch die `width`-Option bei der Initialisierung festgelegt (z.B. 1000px in vielen Demos).

  * **`data-y` (Vertikale Position)**

      * Dieses Attribut definiert die Position des Steps entlang der Y-Achse.
      * Es ist ein numerischer Wert (Pixel).
      * **Beispiel**:
        ```html
        <div class="step" data-y="0">Step am Ursprung (vertikal)</div>
        <div class="step" data-y="800">Step 800px unterhalb des Ursprungs</div>
        <div class="step" data-y="-400">Step 400px oberhalb des Ursprungs</div>
        ```
      * **Interaktion mit der Step-Höhe**: Ähnlich wie bei `data-x` bezieht sich `data-y` auf den Ankerpunkt des Steps. Die Höhe des Steps (CSS oder `impress.js`-Standard, z.B. 700px in vielen Demos) ist relevant für die Anordnung.

  * **`data-z` (Position in der Tiefe)**

      * Dieses Attribut definiert die Position des Steps entlang der Z-Achse und ist entscheidend für 3D-Effekte.
      * Es ist ein numerischer Wert (Pixel).
      * **Auswirkungen**:
          * `data-z="0"`: Der Step befindet sich auf der Hauptebene (der "Bildschirmebene", wenn keine globale Z-Transformation auf den `#impress`-Container angewendet wurde).
          * `data-z > 0` (z.B. `data-z="500"`): Der Step wird um 500px **näher zum Betrachter** verschoben. Durch die Perspektive wirkt er dadurch **größer**.
          * `data-z < 0` (z.B. `data-z="-1000"`): Der Step wird um 1000px **weiter vom Betrachter weg** in den Bildschirm hinein verschoben. Durch die Perspektive wirkt er dadurch **kleiner**.
      * **Beispiel**:
        ```html
        <div class="step" data-z="0">Step auf der Hauptebene</div>
        <div class="step" data-z="1000">Step 1000px vor der Hauptebene (wirkt größer)</div>
        <div class="step" data-z="-2000">Step 2000px hinter der Hauptebene (wirkt kleiner)</div>
        ```
      * **Einfluss der Perspektive**: Der 3D-Effekt und wie stark die Skalierung bei Änderung von `data-z` ausfällt, hängt maßgeblich von der CSS `perspective`-Eigenschaft des Elternelements des `#impress`-Containers ab (typischerweise der `<body>`). `impress.js` setzt oft einen Standardwert für die Perspektive, z.B. `1000px`, in seinen Demo-CSS-Dateien oder über die `perspective`-Option bei der Initialisierung (Standard ist 1000).
          * **Was bedeutet `perspective`?** Stell dir vor, du schaust auf eine lange Straße. Die Ränder der Straße scheinen in der Ferne an einem Punkt (dem Fluchtpunkt) zusammenzulaufen. Der `perspective`-Wert gibt den Abstand des Betrachters zu dieser "Bildschirmebene" (Z=0 Ebene) an.
          * Ein **kleinerer `perspective`-Wert** (z.B. `500px`) bedeutet, der Betrachter ist "näher dran", was zu stärkeren, dramatischeren 3D-Verzerrungen und Skalierungseffekten führt.
          * Ein **größerer `perspective`-Wert** (z.B. `2000px`) bedeutet, der Betrachter ist "weiter weg", was zu subtileren 3D-Effekten führt.
          * Wenn kein `perspective`-Wert gesetzt ist oder dieser `0` ist, gibt es keinen 3D-Effekt durch `data-z` (außer dass Steps mit unterschiedlichem Z-Wert übereinander liegen können, aber ohne perspektivische Skalierung).

**Wichtig**: Wenn ein `data-*`-Attribut für die Position nicht angegeben wird, nimmt `impress.js` für dieses Attribut den Wert `0` an. Ein `<div class="step">` ohne jegliche `data-x/y/z`-Attribute wird also bei (0,0,0) positioniert.

### Erstellen von 2D-Layouts

Für viele Präsentationen reicht eine Anordnung der Steps auf einer einzelnen Ebene (also mit `data-z="0"` oder ohne explizite `data-z`-Angabe).

**1. Lineare Anordnungen:**

  * **Horizontale Reihe von Steps**:
    Alle Steps haben denselben `data-y`-Wert, während sich `data-x` erhöht (oder verringert).

    ```html
    <div id="impress">
        <div id="h-step1" class="step" data-x="0" data-y="0">Inhalt Step 1</div>
        <div id="h-step2" class="step" data-x="1200" data-y="0">Inhalt Step 2 (rechts daneben)</div>
        <div id="h-step3" class="step" data-x="2400" data-y="0">Inhalt Step 3 (weiter rechts)</div>
        <div id="h-step4" class="step" data-x="-1200" data-y="0">Inhalt Step 4 (links vom ersten)</div>
    </div>
    <script>impress().init();</script>
    ```

    *Um die Steps sichtbar und nebeneinander zu positionieren, ohne dass sie sich überlappen, müsstest du ihnen via CSS eine Breite geben (z.B. `width: 900px; padding: 40px;`) und die `data-x`-Werte entsprechend anpassen.*

  * **Vertikale Reihe von Steps**:
    Alle Steps haben denselben `data-x`-Wert, während sich `data-y` erhöht (oder verringert).

    ```html
    <div id="impress">
        <div id="v-step1" class="step" data-x="0" data-y="0">Inhalt Step 1</div>
        <div id="v-step2" class="step" data-x="0" data-y="900">Inhalt Step 2 (darunter)</div>
        <div id="v-step3" class="step" data-x="0" data-y="1800">Inhalt Step 3 (weiter darunter)</div>
        <div id="v-step4" class="step" data-x="0" data-y="-900">Inhalt Step 4 (darüber)</div>
    </div>
    <script>impress().init();</script>
    ```

    *Auch hier ist CSS für die Step-Höhe und Abstände relevant.*

**2. Nicht-lineare 2D-Anordnungen:**

Hier kombinierst du `data-x` und `data-y` frei, um komplexere Layouts zu erstellen.

  * **Raster (Grid) Layout**:
    Steps werden in Zeilen und Spalten angeordnet.

    ```html
    <div id="impress">
        <div id="grid-r1c1" class="step" data-x="0"    data-y="0">R1, C1</div>
        <div id="grid-r1c2" class="step" data-x="1200" data-y="0">R1, C2</div>
        <div id="grid-r1c3" class="step" data-x="2400" data-y="0">R1, C3</div>

        <div id="grid-r2c1" class="step" data-x="0"    data-y="900">R2, C1</div>
        <div id="grid-r2c2" class="step" data-x="1200" data-y="900">R2, C2</div>
        <div id="grid-r2c3" class="step" data-x="2400" data-y="900">R2, C3</div>
    </div>
    <script>impress().init();</script>
    ```

    In diesem Beispiel wurde ein Abstand von 1200px horizontal und 900px vertikal zwischen den Ankerpunkten der Steps gewählt.

  * **Zirkuläre oder freie Anordnungen**: Du kannst Steps auch in einem Kreis, einer Spirale oder jeder anderen denkbaren 2D-Form anordnen, indem du die `data-x` und `data-y` Werte entsprechend berechnest (ggf. mit etwas Mathematik wie Sinus/Kosinus für Kreise).

  * **Abstände und Überlappungen**:

      * Die tatsächlichen Abstände hängen von den `data-x`/`data-y`-Werten **und** den per CSS definierten Dimensionen (Breite, Höhe, Padding, Margin) deiner Steps ab.
      * Wenn der Abstand zwischen den `data-x`-Werten zweier Steps kleiner ist als die Breite des ersten Steps (plus ggf. Margins/Paddings), werden sie sich überlappen. Dies kann ein gewünschter Effekt sein.

**Wichtigkeit der Step-Dimensionen (CSS):**
`impress.js` selbst definiert nicht das Aussehen oder die Grundgröße deiner Steps – das machst du mit CSS. Die `data-*`-Attribute für Position, Rotation und Skalierung werden auf die per CSS definierten Elemente angewendet. Wenn du also `data-x="1000"` setzt, ist der Step um 1000px verschoben, unabhängig davon, ob er 100px oder 1000px breit ist. Die Standard-Demo von `impress.js` verwendet oft Steps mit einer Breite von ca. 1000px und einer Höhe von ca. 700px als Referenz, aber du bist hier völlig frei.

### Einführung in 3D-Layouts: Nutzung der Z-Achse für Tiefeneffekte

Jetzt wird es richtig spannend\! Durch Hinzunahme des `data-z`-Attributs öffnet sich die dritte Dimension.

  * **Kombination von `data-x`, `data-y` und `data-z`**: Du kannst alle drei Attribute frei kombinieren, um einen Step an einer beliebigen Stelle im 3D-Raum zu platzieren.

  * **Steps vor und hinter der Hauptebene (Z=0)**:

      * Ein Step mit `data-z="500"` wird 500px "näher" zum Betrachter gerückt. Durch die Perspektive erscheint er größer.
      * Ein Step mit `data-z="-1000"` wird 1000px "tiefer" in die Leinwand hinein verschoben. Er erscheint kleiner.

  * **Staffelungseffekte**: Du kannst Gruppen von Steps auf unterschiedlichen Z-Ebenen anordnen, um visuelle Ebenen und Tiefe zu erzeugen. Zum Beispiel könnte eine Hauptidee auf `data-z="0"` liegen, unterstützende Details auf `data-z="-500"` und eine Zusammenfassung auf `data-z="500"`.

  * **"Durchflug"-Effekte**: Wenn du von einem Step mit `data-z="0"` zu einem Step mit einem stark negativen `data-z`-Wert (z.B. `data-z="-3000"`) navigierst, erzeugt `impress.js` einen Übergang, der sich wie ein Hineinfliegen in eine Szene anfühlt. Umgekehrt wirkt die Navigation zu einem Step mit stark positivem `data-z` wie ein Herauszoomen oder ein Entgegenkommen des Steps.

**Detaillierter Beispielcode für ein einfaches 3D-Layout:**

```html
<!doctype html>
<html lang="de">
<head>
    <meta charset="utf-8" />
    <title>Meine erste 3D impress.js Präsentation</title>
    <style>
        /* Grundlegendes Styling für Sichtbarkeit */
        body {
            font-family: sans-serif;
            /* WICHTIG: Perspektive für den 3D-Raum setzen! Ohne dies kein echter 3D-Effekt. */
            /* impress.js setzt dies normalerweise, aber zur Verdeutlichung hier: */
            /* perspective: 1000px; (wird oft auf body oder einen Wrapper von #impress gesetzt) */
        }
        .step {
            width: 700px;
            height: 500px; /* Höhe hinzugefügt für bessere 3D-Wahrnehmung */
            padding: 20px;
            border: 1px solid navy;
            border-radius: 5px;
            background-color: rgba(200, 220, 255, 0.8);
            display: block;
            text-align: center; /* Inhalt zentrieren für Demo */
            font-size: 24px;
        }
        /* Unterschiedliche Farben zur besseren Unterscheidung der Ebenen */
        #step-1 { background-color: rgba(255, 200, 200, 0.8); } /* Rötlich */
        #step-2 { background-color: rgba(200, 255, 200, 0.8); } /* Grünlich */
        #step-3 { background-color: rgba(200, 200, 255, 0.8); } /* Bläulich */

        .fallback-message { /* ... (Styling wie in Teil 2) ... */ }
        .impress-not-supported .fallback-message { display: block; }
        body:not(.impress-not-supported) .fallback-message { display: none; }
    </style>
</head>
<body class="impress-not-supported">

    <div class="fallback-message">
        <p>Dein Browser scheint impress.js nicht zu unterstützen...</p>
    </div>

    <div id="impress" data-perspective="800">

        <div id="step-1" class="step" data-x="0" data-y="0" data-z="0">
            <h2>Step 1: Die Hauptebene</h2>
            <p>(Z = 0)</p>
            <p>Dieser Step ist unsere Referenz auf der Bildschirmebene.</p>
        </div>

        <div id="step-2" class="step" data-x="1000" data-y="700" data-z="-1500">
            <h2>Step 2: Weit entfernt</h2>
            <p>(Z = -1500)</p>
            <p>Dieser Step ist nach rechts unten und 1500px <em>hinter</em> die Hauptebene verschoben. Er wird kleiner erscheinen.</p>
        </div>

        <div id="step-3" class="step" data-x="-800" data-y="-500" data-z="700">
            <h2>Step 3: Ganz nah</h2>
            <p>(Z = 700)</p>
            <p>Dieser Step ist nach links oben und 700px <em>vor</em> die Hauptebene gerückt. Er wird größer erscheinen.</p>
        </div>

    </div>

    <script src="https://cdn.jsdelivr.net/gh/impress/impress.js@2.0.0/js/impress.js"></script>
    <script>
        impress().init();
    </script>

</body>
</html>
```

**Erläuterungen zum 3D-Beispiel:**

  * **`data-perspective="800"`**: Am `<div id="impress">` habe ich `data-perspective="800"` hinzugefügt. Dies ist eine Möglichkeit, die Perspektive direkt über `impress.js` zu konfigurieren (alternativ zu CSS auf dem `body` oder einer Konfigurationsoption in `init()`). Ein Wert von 800px erzeugt eine deutlichere Perspektive als der Standardwert von 1000px.
  * **Step 1**: Ist auf der Ebene Z=0, unsere Basis.
  * **Step 2**: Liegt bei `data-z="-1500"`. Wenn du von Step 1 zu Step 2 navigierst, scheint die Kamera in die Präsentation hineinzufliegen, und Step 2 erscheint weiter weg und kleiner.
  * **Step 3**: Liegt bei `data-z="700"`. Navigierst du hierhin, kommt der Step scheinbar auf dich zu und wirkt größer.

**Experimentiere\!**
Der beste Weg, ein Gefühl für die Positionierung und die 3D-Effekte zu bekommen, ist, mit den `data-x`, `data-y`, `data-z` und `data-perspective` Werten selbst zu experimentieren. Ändere sie und beobachte, wie sich die Darstellung und die Übergänge verändern.



## Teil 4: Rotation und Skalierung von Steps

Nachdem du gelernt hast, wie man Steps im 2D- und 3D-Raum positioniert, eröffnen wir nun die nächsten Dimensionen der Gestaltung: Rotation und Skalierung. Diese Transformationen sind entscheidend, um das volle Potenzial des Zooming User Interface (ZUI) von `impress.js` auszuschöpfen und wirklich eindrucksvolle, nicht-lineare Präsentationspfade zu kreieren.

### Grundlagen der Transformationen in `impress.js`

Bevor wir uns den spezifischen Datenattributen widmen, ein paar grundlegende Konzepte:

  * **Steps als transformierbare Einheiten**: Wie du weißt, ist jeder `<div class="step">` ein eigenständiges HTML-Element. `impress.js` nutzt CSS3-Transformationen, um diese Elemente im Raum zu bewegen, zu drehen und ihre Größe zu ändern.
  * **Transformationsursprung (`transform-origin`)**:
      * Standardmäßig erfolgen alle Rotationen und Skalierungen um den **Mittelpunkt des jeweiligen Steps**. Dieser Referenzpunkt wird in CSS als `transform-origin` bezeichnet und hat standardmäßig den Wert `50% 50% 0` (oder `center center`). Das bedeutet, wenn du einen Step drehst, dreht er sich um seine eigene Mitte.
      * Für die meisten Anwendungsfälle in `impress.js` ist es am intuitivsten, diesen Standard-Transformationsursprung beizubehalten und die Platzierung primär über die `data-x`, `data-y` und `data-z` Attribute zu steuern. Eine Änderung des `transform-origin` über CSS ist zwar möglich, kann aber die intuitive Steuerung über die Datenattribute verkomplizieren.
  * **Reihenfolge der Transformationen**: Wenn mehrere Transformationen (Positionierung, Rotation, Skalierung) auf einen Step angewendet werden, ist die Reihenfolge relevant. `impress.js` generiert CSS-`transform`-Anweisungen. Die interne Reihenfolge der CSS-Transformationen ist typischerweise: Verschiebung (translate), dann Rotation (rotate), dann Skalierung (scale). Für dich als Nutzer von `impress.js` bedeutet das vor allem, dass sich Rotationen auf das bereits durch `data-x/y/z` positionierte Element beziehen und um dessen eigenen (transformierten) Achsen stattfinden.

### Rotation von Steps im Detail

`impress.js` bietet Datenattribute, um Steps um die X-, Y- und Z-Achse ihres eigenen Koordinatensystems zu drehen. Die Werte werden in **Grad (`deg`)** angegeben.

**1. `data-rotate-x` (Rotation um die X-Achse):**

  * **Erklärung**: Dieses Attribut dreht den Step um seine horizontale Achse (die X-Achse, die von links nach rechts durch den Mittelpunkt des Steps verläuft).
  * **Einheit**: Grad.
      * Ein **positiver Wert** (z.B. `data-rotate-x="30"`) kippt den oberen Rand des Steps "nach hinten" (vom Betrachter weg, in den Bildschirm hinein) und den unteren Rand "nach vorne" (zum Betrachter hin).
      * Ein **negativer Wert** (z.B. `data-rotate-x="-45"`) kippt den oberen Rand des Steps "nach vorne" (zum Betrachter hin, aus dem Bildschirm heraus) und den unteren Rand "nach hinten".
  * **Visualisierung/Analogie**: Stell dir ein an der Wand hängendes Schild vor, das du an seiner horizontalen Mittellinie nach vorne oder hinten kippst.
  * **Beispiele**:
    ```html
    <div id="impress" data-perspective="1000">
        <div class="step" data-x="0" data-y="0" data-rotate-x="0">
            Normale Ansicht (0 Grad)
        </div>
        <div class="step" data-x="1200" data-y="0" data-rotate-x="45">
            Um 45 Grad nach hinten gekippt
        </div>
        <div class="step" data-x="0" data-y="900" data-rotate-x="-60">
            Um 60 Grad nach vorne gekippt
        </div>
        <div class="step" data-x="1200" data-y="900" data-rotate-x="90">
            Um 90 Grad nach hinten gekippt (von der Seite betrachtet, sehr schmal)
        </div>
    </div>
    <script>impress().init();</script>
    ```
  * **Auswirkungen**: Starke X-Rotationen können die Lesbarkeit des Inhalts erheblich beeinträchtigen, da der Text perspektivisch stark verzerrt wird. Sie eignen sich gut für subtile Neigungen oder für dynamische Übergänge, bei denen ein Step "hereinklappt". In Kombination mit `data-z` können interessante räumliche Effekte entstehen, z.B. eine geneigte Ebene, die in die Tiefe führt.

**2. `data-rotate-y` (Rotation um die Y-Achse):**

  * **Erklärung**: Dieses Attribut dreht den Step um seine vertikale Achse (die Y-Achse, die von oben nach unten durch den Mittelpunkt des Steps verläuft).
  * **Einheit**: Grad.
      * Ein **positiver Wert** (z.B. `data-rotate-y="30"`) dreht die rechte Kante des Steps "nach hinten" (vom Betrachter weg, in den Bildschirm hinein) und die linke Kante "nach vorne".
      * Ein **negativer Wert** (z.B. `data-rotate-y="-45"`) dreht die linke Kante des Steps "nach hinten" und die rechte Kante "nach vorne".
  * **Visualisierung/Analogie**: Stell dir eine Tür vor, die sich öffnet oder schließt.
  * **Beispiele**:
    ```html
    <div id="impress" data-perspective="1000">
        <div class="step" data-x="0" data-y="0" data-rotate-y="0">
            Normale Ansicht (0 Grad)
        </div>
        <div class="step" data-x="1200" data-y="0" data-rotate-y="45">
            Um 45 Grad gedreht (rechte Seite nach hinten)
        </div>
        <div class="step" data-x="0" data-y="900" data-rotate-y="-60">
            Um 60 Grad gedreht (linke Seite nach hinten)
        </div>
        <div class="step" data-x="1200" data-y="900" data-rotate-y="90">
            Um 90 Grad gedreht (von der Seite betrachtet, sehr schmal)
        </div>
    </div>
    <script>impress().init();</script>
    ```
  * **Auswirkungen**: Ähnlich wie bei `data-rotate-x` kann eine starke Y-Rotation die Lesbarkeit reduzieren. Dieser Effekt wird oft für das "Umblättern" von Seiten oder das Aufdecken von Inhalten genutzt.

**3. `data-rotate-z` (Rotation um die Z-Achse) – Alias: `data-rotate`:**

  * **Erklärung**: Dieses Attribut dreht den Step in seiner eigenen 2D-Ebene, also um die Z-Achse, die senkrecht aus dem Bildschirmmittelpunkt des Steps herausragt.
  * **Einheit**: Grad.
      * Ein **positiver Wert** (z.B. `data-rotate-z="30"`) dreht den Step im **Uhrzeigersinn**.
      * Ein **negativer Wert** (z.B. `data-rotate-z="-45"`) dreht den Step **gegen den Uhrzeigersinn**.
  * **Alias `data-rotate`**: Aus Gründen der Abwärtskompatibilität und Einfachheit für reine 2D-Rotationen kann `data-rotate` als Alias für `data-rotate-z` verwendet werden. Wenn du also nur in der Ebene drehen möchtest, reicht `data-rotate`.
      * `data-rotate="45"` ist äquivalent zu `data-rotate-z="45"`.
  * **Visualisierung/Analogie**: Stell dir ein Blatt Papier vor, das du auf einem Tisch im oder gegen den Uhrzeigersinn drehst.
  * **Beispiele**:
    ```html
    <div id="impress" data-perspective="1000"> <div class="step" data-x="0" data-y="0" data-rotate-z="0"> Normale Ausrichtung (0 Grad)
        </div>
        <div class="step" data-x="1200" data-y="0" data-rotate-z="30"> Um 30 Grad im Uhrzeigersinn gedreht
        </div>
        <div class="step" data-x="0" data-y="900" data-rotate-z="-45"> Um 45 Grad gegen den Uhrzeigersinn gedreht
        </div>
    </div>
    <script>impress().init();</script>
    ```

**4. Kombination von Rotationen:**

Du kannst `data-rotate-x`, `data-rotate-y` und `data-rotate-z` (oder `data-rotate`) miteinander kombinieren, um einen Step um mehrere Achsen gleichzeitig zu drehen.

  * **Wirkungsweise**: Die Rotationen werden nacheinander angewendet. Die genaue Reihenfolge (z.B. erst X, dann Y, dann Z) ist durch die CSS-`transform`-Spezifikation definiert. Das Ergebnis ist eine Rotation des Steps um seine lokalen Achsen, die sich durch vorherige Rotationen bereits mitgedreht haben können.
  * **Komplexität**: Das genaue Ergebnis von kombinierten 3D-Rotationen vorherzusagen, kann schwierig sein (Stichwort: Gimbal Lock bei bestimmten Rotationssequenzen, obwohl dies in der CSS-Implementierung meist gut gehandhabt wird).
  * **Empfehlung**: Experimentiere\! Beginne mit einer Achse, füge dann eine zweite hinzu und beobachte die Änderungen.
    ```html
    <div class="step" data-x="0" data-y="0" data-rotate-x="30" data-rotate-y="45" data-rotate-z="15">
        Komplexe Drehung
    </div>
    ```
    Dieser Step wird zuerst um 30 Grad um seine X-Achse gekippt, dann um 45 Grad um seine (neue) Y-Achse gedreht und schließlich um 15 Grad um seine (nochmals neue) Z-Achse rotiert.

### Skalierung von Steps im Detail (`data-scale`)

Neben der Positionierung und Rotation kannst du die Größe deiner Steps direkt beeinflussen.

  * **Erklärung**: Das Attribut `data-scale` vergrößert oder verkleinert einen Step relativ zu seiner ursprünglichen, per CSS definierten Größe. Die Skalierung erfolgt gleichmäßig in X- und Y-Richtung (es sei denn, man würde dies mit komplexeren CSS-`transform`-Funktionen manuell ändern, was `impress.js` mit `data-scale` allein nicht tut).

  * **Einheit**: Ein dimensionsloser Multiplikationsfaktor.

      * `data-scale="1"`: Der Step wird in seiner Originalgröße dargestellt. Dies ist der Standardwert, wenn das Attribut nicht angegeben ist.
      * `data-scale="2"`: Der Step wird doppelt so groß dargestellt (200% der Originalgröße).
      * `data-scale="0.5"`: Der Step wird halb so groß dargestellt (50% der Originalgröße).
      * `data-scale="0"`: Der Step wäre theoretisch unsichtbar (auf 0% skaliert). Dies wird jedoch selten für statische Zustände verwendet, sondern eher als Ziel für Übergänge, um etwas verschwinden zu lassen.
      * Negative Werte für `data-scale` sind unüblich und können zu gespiegelten, oft unerwünschten Ergebnissen führen.

  * **Wichtiger Unterschied zwischen `data-scale` und der Skalierung durch `data-z`**:

      * **`data-z` (Perspektivische Skalierung)**: Wenn du einen Step mit `data-z` in die Tiefe verschiebst (negativer Wert) oder näher heranholst (positiver Wert), ändert sich seine *wahrgenommene* Größe aufgrund der Perspektive. Der Step selbst behält seine internen Abmessungen, erscheint aber für den Betrachter größer oder kleiner.
      * **`data-scale` (Direkte Skalierung)**: Dieses Attribut ändert die *tatsächliche* gerenderte Größe des Steps, unabhängig von seiner Z-Position. Es ist ein expliziter Skalierungsfaktor, der auf die ursprünglichen Dimensionen des Elements angewendet wird.

  * **Kombination von `data-scale` und `data-z`**:
    Diese beiden Attribute können sehr wirkungsvoll kombiniert werden:

      * Ein Step, der weit entfernt ist (z.B. `data-z="-3000"`), würde durch die Perspektive sehr klein erscheinen. Mit `data-scale="5"` könntest du ihn trotzdem groß und lesbar machen, obwohl er "in der Ferne" liegt.
      * Ein Step, der sehr nah ist (z.B. `data-z="800"`), würde sehr groß erscheinen. Mit `data-scale="0.3"` könntest du ihn verkleinern, um z.B. nur ein kleines Detail hervorzuheben.
        Dies gibt dir eine immense Kontrolle über die Zooming-Effekte und die Komposition deiner Präsentationslandschaft.

  * **Beispiele für `data-scale`**:

    ```html
    <div id="impress" data-perspective="1000">
        <div id="scale-step1" class="step" data-x="0" data-y="0" data-scale="1">
            Originalgröße (Skalierung 1)
        </div>
        <div id="scale-step2" class="step" data-x="1200" data-y="0" data-scale="2.5">
            2.5-fache Größe
        </div>
        <div id="scale-step3" class="step" data-x="0" data-y="900" data-scale="0.75">
            3/4 der Originalgröße
        </div>
        <div id="scale-step4" class="step" data-x="1200" data-y="900" data-z="-1000" data-scale="2">
            Dieser Step ist 1000px tief (erscheint kleiner)
            ABER wird gleichzeitig auf doppelte Größe skaliert.
        </div>
    </div>
    <script>impress().init();</script>
    ```

### Kombination von Positionierung, Rotation und Skalierung für komplexe ZUI-Effekte

Die wahre Magie von `impress.js` entfaltet sich, wenn du alle bisher gelernten Attribute kombinierst: `data-x`, `data-y`, `data-z`, die `data-rotate-*`-Familie und `data-scale`.

Stell dir folgende Szenarien vor:

  * **Hereinfliegende und sich entfaltende Karte**: Ein Step startet weit hinten (`data-z="-2000"`), klein (`data-scale="0.2"`) und vielleicht um die Y-Achse gedreht (`data-rotate-y="90"`), sodass er von der Seite zu sehen ist. Beim Übergang zu diesem Step "fliegt" die Kamera dorthin, der Step wird größer (`data-scale="1"`), kommt nach vorne (`data-z="0"`) und dreht sich in die Frontalansicht (`data-rotate-y="0"`).
  * **Eine Spirale aus Steps**: Steps, die entlang einer Spirale im 3D-Raum angeordnet sind, wobei jeder Step leicht anders gedreht und skaliert ist.
  * **Ein "Gedankencluster"**: Eine zentrale Idee (`data-z="0"`, `data-scale="1.5"`) und darum herum kleinere, leicht geneigte und in die Tiefe versetzte Steps (`data-z="-500"`, `data-scale="0.8"`, leichte `data-rotate-x/y`-Werte), die Details oder verwandte Konzepte darstellen.

**Beispielcode mit einer Kombination von Transformationen:**

```html
<!doctype html>
<html lang="de">
<head>
    <meta charset="utf-8" />
    <title>Kombinierte Transformationen</title>
    <style>
        /* (Minimales CSS wie in vorherigen Beispielen, um Steps sichtbar zu machen) */
        body { perspective: 1000px; font-family: sans-serif; }
        .step {
            width: 600px; height: 400px; padding: 20px;
            border: 1px solid green; background-color: rgba(152, 251, 152, 0.7);
            display: block; text-align: center; border-radius: 8px;
        }
        /* Fallback-Message Styling */
        .fallback-message { /* ... */ }
        .impress-not-supported .fallback-message { display: block; }
        body:not(.impress-not-supported) .fallback-message { display: none; }
    </style>
</head>
<body class="impress-not-supported">
    <div class="fallback-message"><p>Browser nicht unterstützt...</p></div>

    <div id="impress">
        <div id="intro" class="step" data-x="0" data-y="0" data-z="0" data-scale="1">
            <h2>Startpunkt</h2>
            <p>Ganz normaler Step.</p>
        </div>

        <div id="zoomed-rotated" class="step"
             data-x="1500"
             data-y="1000"
             data-z="-1500"
             data-rotate-x="30"
             data-rotate-y="-45"
             data-rotate-z="15"
             data-scale="2">
            <h2>Komplex transformiert!</h2>
            <p>Dieser Step ist verschoben, rotiert um alle Achsen, befindet sich weiter hinten UND ist doppelt so groß skaliert.</p>
        </div>

        <div id="side-view" class="step"
             data-x="500"
             data-y="-800"
             data-z="-500"
             data-rotate-y="80"
             data-scale="1.2">
            <h2>Seitenansicht</h2>
            <p>Fast von der Seite betrachtet, leicht vergrößert und etwas nach hinten versetzt.</p>
        </div>
    </div>

    <script src="https://cdn.jsdelivr.net/gh/impress/impress.js@2.0.0/js/impress.js"></script>
    <script>impress().init();</script>
</body>
</html>
```

**Tipps für die Planung komplexer Transformationen:**

1.  **Schrittweise vorgehen**: Beginne mit der Positionierung (`data-x`, `data-y`, `data-z`). Füge dann Rotationen hinzu und schließlich die Skalierung. Teste nach jeder Änderung.
2.  **Browser-Entwicklertools**: Moderne Browser bieten exzellente Entwicklertools (oft mit F12 erreichbar). Im "Elements"- oder "Inspector"-Tab kannst du dir die angewendeten CSS-Transformationen ansehen und sogar live verändern, um Effekte zu testen.
3.  **Skizzen**: Bei sehr komplexen räumlichen Anordnungen kann eine einfache Skizze auf Papier helfen, die gewünschten Positionen und Drehungen zu visualisieren.
4.  **Keep it simple (KISS-Prinzip)**: Nur weil du alles drehen und wenden kannst, heißt das nicht, dass du es musst. Übermäßige oder schlecht geplante Transformationen können das Publikum eher verwirren als beeindrucken.

### Auswirkungen auf den Inhalt und die Lesbarkeit

  * **Lesbarkeit**: Starke perspektivische Verzerrungen (durch `data-rotate-x/y` und `data-z` in Kombination mit einer starken Perspektive) können Text schwer lesbar machen. Achte darauf, dass deine Inhalte auch nach der Transformation noch gut erfassbar sind.
  * **Schriftgrößen und Kontraste**: Wähle ausreichend große Schriftarten und gute Kontraste, besonders für Steps, die stark skaliert oder aus der Ferne betrachtet werden.
  * **Subtilität vs. Dramatik**:
      * Subtile Rotationen und Skalierungen können helfen, die Aufmerksamkeit sanft zu lenken oder eine räumliche Beziehung anzudeuten.
      * Dramatische Transformationen (z.B. schnelles Hereinzoomen, starke Drehungen) können als "Wow-Effekt" dienen, sollten aber gezielt und nicht inflationär eingesetzt werden, um das Publikum nicht zu überfordern oder abzulenken.

Das Experimentieren mit diesen Attributen ist der Schlüssel zum Meistern von `impress.js`. Du hast nun die grundlegenden Werkzeuge, um deine Steps im Raum tanzen zu lassen\!


## Teil 5: Präsentationssteuerung und Navigation

Nachdem du nun weißt, wie du deine Steps im 2D- und 3D-Raum positionieren, rotieren und skalieren kannst, ist es an der Zeit zu lernen, wie du dich und dein Publikum elegant durch diese gestaltete Landschaft bewegst. `impress.js` bietet hierfür intuitive Standardmechanismen sowie Möglichkeiten zur individuellen Anpassung.

### Grundlagen der Navigation in `impress.js`

  * **Der "aktive" Step**: Zu jedem Zeitpunkt der Präsentation ist genau ein Step der "aktive" Step. Dies ist der Step, der im Ansichtsfenster zentriert und fokussiert dargestellt wird. `impress.js` fügt diesem Step die CSS-Klasse `active` hinzu.
  * **Übergänge**: Wenn du von einem Step zum nächsten navigierst, berechnet `impress.js` die notwendigen Transformationen (Verschiebung, Drehung, Skalierung der gesamten `#impress`-Leinwand), um den Ziel-Step in den Fokus zu rücken. Diese Transformationen werden mittels CSS-Transitionen animiert, was die sanften und oft eindrucksvollen Übergänge erzeugt. Die Dauer und Art der Transition kann über CSS und teilweise über `impress.js`-Optionen beeinflusst werden. Steps, die bereits besucht wurden, erhalten die Klasse `past`, und solche, die noch folgen (gemäß DOM-Reihenfolge), die Klasse `future`.

### Standardmäßige Tastaturnavigation im Detail

`impress.js` bietet eine Reihe von Tastaturbefehlen für die Navigation, die standardmäßig aktiviert sind. Diese ermöglichen eine flüssige Steuerung ohne Maus.

  * **Vorwärts navigieren**:

      * **Leertaste (Spacebar)**: Bewegt die Präsentation zum **nächsten** Step. Dies ist oft die primäre Taste zum Voranschreiten.
      * **Pfeil nach rechts (Right Arrow)**: Hat dieselbe Funktion wie die Leertaste und geht zum nächsten Step.
      * **Pfeil nach unten (Down Arrow)**: Ebenfalls identisch zur Leertaste, geht zum nächsten Step.
      * **Page Down (Bild ↓)**: Auch diese Taste führt zum nächsten Step.
      * **Verhalten am Ende**: Wenn du beim letzten Step bist und eine dieser Tasten drückst, passiert standardmäßig nichts weiter. Die Präsentation bleibt beim letzten Step stehen. Es gibt keine automatische Rückkehr zum ersten Step (Looping), es sei denn, dies wird durch Plugins oder eigene Skripte implementiert.

  * **Rückwärts navigieren**:

      * **Shift + Leertaste (Shift + Spacebar)**: Bewegt die Präsentation zum **vorherigen** Step.
      * **Pfeil nach links (Left Arrow)**: Hat dieselbe Funktion wie Shift + Leertaste und geht zum vorherigen Step.
      * **Pfeil nach oben (Up Arrow)**: Ebenfalls identisch zu Shift + Leertaste, geht zum vorherigen Step.
      * **Page Up (Bild ↑)**: Auch diese Taste führt zum vorherigen Step.
      * **Verhalten am Anfang**: Wenn du beim ersten Step bist und eine dieser Tasten drückst, passiert standardmäßig nichts weiter. Die Präsentation bleibt beim ersten Step.

  * **Direkt zu bestimmten Steps springen**:

      * **Home-Taste (Pos1)**: Springt direkt zum **ersten** Step der Präsentation. Als "erster Step" gilt hier das erste `<div class="step">`-Element innerhalb des `<div id="impress">`-Containers gemäß seiner Reihenfolge im HTML-DOM.
      * **Ende-Taste (End)**: Springt direkt zum **letzten** Step der Präsentation, basierend auf der DOM-Reihenfolge.

  * **Tab-Taste**:

      * Die Tab-Taste dient primär der Navigation zwischen **fokussierbaren Elementen innerhalb des aktuell aktiven Steps** (z.B. Hyperlinks, Formularfelder, Buttons). Sie steuert nicht direkt die Navigation zwischen den `impress.js`-Steps selbst.
      * Wenn du also interaktive Elemente in deinen Steps hast, können diese weiterhin mit der Tab-Taste erreicht werden, was für die Barrierefreiheit wichtig ist.

**Wichtiger Hinweis zur "Nächster/Vorheriger"-Logik**:
Die Standardlogik für "nächster" und "vorheriger" Step basiert strikt auf der **Reihenfolge der `<div class="step">`-Elemente im HTML-Quellcode**. Der erste Step im DOM ist der Start, der zweite ist der nächste, und so weiter. Dies gilt, solange keine spezifischen Navigationspfade durch Plugins (wie das `rel`-Plugin) oder programmatische `goto()`-Aufrufe definiert sind.

### Maus-Klick-Navigation im Detail

Standardmäßig bietet `impress.js` auch eine einfache Form der Mausnavigation:

  * **Klick auf den (scheinbaren) Hintergrund des aktuellen Steps**: Wenn du auf einen Bereich des aktuellen Steps klickst, der selbst kein interaktives Element (wie ein Link) ist, oder auf den sichtbaren Bereich des `#impress`-Containers, der nicht von einem interaktiven Element des aktuellen Steps verdeckt ist, wird dies als Befehl zum **nächsten Step** interpretiert.
      * Technisch gesehen wird oft ein Event-Listener auf den `#impress`-Container oder den `document.body` gelegt, der Klicks abfängt. Wenn der Klick nicht von einem interaktiven Element stammt, wird `impress().next()` ausgelöst.
  * **Klick auf `past` oder `future` Steps in der Overview-Ansicht**: Wie im nächsten Abschnitt genauer erläutert, führt ein Klick auf einen der verkleinert dargestellten Steps in der Overview-Ansicht direkt zu diesem Step.
  * **Deaktivierung/Anpassung**:
      * Dieses Standard-Klickverhalten zum nächsten Step ist nicht immer erwünscht, besonders wenn Steps selbst viele klickbare Bereiche enthalten (z.B. bei interaktiven Infografiken).
      * Eine einfache Möglichkeit, dies zu unterbinden, ist, Klick-Events auf den Steps selbst abzufangen und ihre Weiterleitung zu stoppen (`event.stopPropagation();`).
      * Ob es eine direkte Konfigurationsoption im Core von `impress.js` gibt, um die Maus-Klick-Navigation global zu deaktivieren, müsste in der Dokumentation der spezifischen Version geprüft werden; oft wird dies eher über eigenes Event-Management oder Plugins gehandhabt. Die `mouse-timeout` und `touch` Plugins interagieren ebenfalls mit Maus- und Touch-Events.

### Die "Overview"-Ansicht (Übersichtsmodus) im Detail

Der Overview-Modus ist ein mächtiges Werkzeug, um die nicht-lineare Struktur deiner Präsentation hervorzuheben und eine "Karte" deiner Inhalte anzuzeigen.

  * **Konzept**: Im Overview-Modus zoomt `impress.js` so weit heraus, dass alle (oder die meisten) deiner Steps gleichzeitig auf dem Bildschirm sichtbar werden. Sie behalten dabei ihre relativen Positionen, Rotationen und Skalierungen zueinander bei, erscheinen aber entsprechend verkleinert.

  * **Aktivierung/Deaktivierung des eingebauten Overview-Modus**:

      * Das primäre Tastenkürzel zum Ein- und Ausschalten des Overview-Modus ist die **Escape (ESC)**-Taste.
      * Beim ersten Drücken von ESC wird die Ansicht so transformiert, dass alle Steps in den sichtbaren Bereich passen. Der `#impress`-Container erhält die Klasse `impress-overview`.
      * Ein erneutes Drücken von ESC kehrt zum zuletzt aktiven Step zurück und die Klasse `impress-overview` wird entfernt.
      * Die Berechnung der notwendigen Skalierung und Positionierung für den Overview-Modus erfolgt automatisch durch `impress.js`. Es versucht, alle Steps optimal in das aktuelle Ansichtsfenster einzupassen.

  * **Manuell erstellter "Overview"-Step (wie in der offiziellen Demo)**:

      * Zusätzlich zum eingebauten ESC-basierten Overview kann man einen speziellen Step im HTML definieren, der als manueller Einstiegspunkt in eine ähnliche Ansicht dient. Die offizielle `impress.js`-Demo (`index.html` im Repository) verwendet diesen Ansatz:
        ```html
        <div id="overview" class="step" data-x="3000" data-y="1500" data-scale="10">
        </div>
        ```
      * Dieser "Overview-Step" wird an einer bestimmten Position platziert (`data-x`, `data-y`) und stark vergrößert (`data-scale="10"`). Wenn dieser Step aktiv wird, ist der Effekt, dass die anderen, normal skalierten Steps relativ klein erscheinen und somit eine Übersicht entsteht.
      * **Unterschied zum eingebauten Overview**: Der eingebaute Overview (ESC) ist dynamischer und passt sich der Gesamtgröße aller Steps an. Ein manueller Overview-Step hat feste Transformationswerte und muss sorgfältig platziert und skaliert werden, um alle anderen Steps wie gewünscht darzustellen. Er wird Teil der normalen Navigationssequenz, wenn man ihn nicht überspringt.

  * **Navigation im (eingebauten) Overview-Modus**:

      * **Mausklick**: Wenn du im Overview-Modus bist (via ESC aktiviert), kannst du auf einen beliebigen der verkleinert dargestellten Steps **klicken**. `impress.js` navigiert dann direkt zu diesem Step und verlässt den Overview-Modus.
      * **Tastaturnavigation**: Im eingebauten Overview-Modus ist die Tastaturnavigation (Pfeiltasten, Leertaste) normalerweise nicht dafür gedacht, zwischen den *Miniaturansichten* der Steps zu wechseln. Die Tastaturnavigation (nächster/vorheriger Step) bezieht sich weiterhin auf die DOM-Reihenfolge und würde den Overview-Modus verlassen und zum entsprechenden Step in voller Größe springen.

  * **Visuelle Darstellung im Overview**:

      * Alle Steps werden mit ihren individuellen Transformationen (Position, Rotation, Skalierung) angezeigt, jedoch insgesamt so verkleinert, dass sie ins Bild passen.
      * Der aktuell "aktive" Step (derjenige, von dem aus man in den Overview-Modus gewechselt ist oder der als nächstes aktiv würde) kann visuell hervorgehoben werden (oft durch eine spezielle CSS-Klasse oder indem er nicht so stark "ausgegraut" wird wie die anderen).

  * **Zweck und Vorteile des Overview-Modus**:

      * **Nicht-Linearität**: Er ist das zentrale Werkzeug für echte nicht-lineare Präsentationen. Das Publikum (oder der Präsentierende) kann sehen, "wo" man sich befindet und wohin man als Nächstes springen kann.
      * **Strukturvisualisierung**: Macht die Gesamtarchitektur und die Beziehungen zwischen den Themenblöcken sichtbar.
      * **Flexibilität**: Erlaubt es, spontan von der geplanten Reihenfolge abzuweichen, auf Fragen des Publikums einzugehen oder schnell zu einem bestimmten Punkt zurückzukehren.
      * **Navigation für den Präsentierenden**: Dient als eine Art "Regiepult" oder "Karte".

### Verständnis des Präsentationsflusses in nicht-linearen Strukturen

Wie bereits erwähnt, ist `impress.js` prädestiniert für nicht-lineare Präsentationen.

  * **Die DOM-Reihenfolge als Basis**: Die einfachste "Geschichte", die du erzählen kannst, folgt der Reihenfolge deiner `div.step`-Elemente im HTML. Dies ist der Standardpfad, wenn du nur Leertaste/Pfeiltasten benutzt.

  * **Abweichen von der Linearität**:

    1.  **Räumliches Design**: Ordne deine Steps auf der Leinwand so an, dass logische Gruppen oder alternative Pfade entstehen. Ein Step kann z.B. drei "Unterpunkte" um sich herum gruppiert haben.
    2.  **Overview-Modus nutzen**: Zeige regelmäßig die Übersicht, um dem Publikum Orientierung zu geben und Übergänge zu neuen Themenbereichen anzukündigen.
    3.  **Interne Verlinkung**: Nutze Hyperlinks innerhalb der Steps, um explizite Sprungpunkte zu anderen, nicht direkt benachbarten Steps zu schaffen (siehe nächster Punkt).
    4.  **Programmatische Steuerung**: Fortgeschrittene Nutzer können die `impress().goto()` API-Funktion verwenden, um beliebige Navigationslogiken zu implementieren (mehr dazu in Teil 7).

  * **Planung nicht-linearer Pfade – Extreme Detailtiefe**:

      * **Mindmap-Ansatz**: Beginne mit einer Mindmap deiner Inhalte. Hauptthemen können zentrale Steps sein, Unterthemen können davon abzweigen – räumlich und/oder in der Tiefe.
          * *Beispiel*: Ein zentraler Step "Projektübersicht". Davon ausgehend Steps für "Ziele" (rechts), "Team" (links), "Budget" (darunter), "Risiken" (dahinter, `data-z` negativ).
      * **Mehrere Einstiegspunkte/Pfade**: Du könntest eine Startfolie haben, die verschiedene Hauptbereiche als klickbare Optionen anbietet (jeder Link führt zu einem anderen Step-Cluster).
      * **Zoom-Ebenen für Details**: Ein Übersichtsthema wird groß dargestellt (`data-scale` groß oder `data-z` nah). Beim Navigieren zu einem Unterpunkt zoomt die Präsentation auf einen kleineren Step, der innerhalb des Bereichs des vorherigen großen Steps positioniert ist oder von diesem "abzweigt".
          * *Beispiel*: Ein Step zeigt eine Weltkarte. Klickt man auf einen Kontinent (als Link oder über Navigation), zoomt die Ansicht auf einen Step, der diesen Kontinent detaillierter darstellt und passend auf der Weltkarte positioniert und skaliert war.
      * **Visuelle Metaphern**: Nutze die räumliche Anordnung, um Konzepte zu unterstützen. Eine Zeitachse kann linear von links nach rechts verlaufen. Ein Kreislaufprozess kann zirkulär angeordnet werden. Komplexe Systeme können als miteinander verbundene Knoten dargestellt werden.
      * **"Easter Eggs" oder optionale Details**: Verstecke optionale Zusatzinformationen in Steps, die abseits des Hauptpfades liegen und z.B. nur über einen spezifischen Link oder einen Abstecher im Overview-Modus erreicht werden.
      * **Konsistente Rückkehrpunkte**: Sorge dafür, dass es von detaillierten Abzweigungen klare Wege zurück zu übergeordneten Themen oder zur Hauptübersicht gibt. Dies kann durch Links wie "Zurück zur Übersicht" oder durch Nutzung des Overview-Modus geschehen.
      * **Publikumsführung**: Auch wenn die Struktur nicht-linear ist, solltest du als Präsentierender einen oder mehrere "empfohlene Pfade" im Kopf haben, um das Publikum nicht zu verlieren. Die Freiheit der Nicht-Linearität sollte die Klarheit der Botschaft unterstützen, nicht behindern.

### Verwendung von IDs für Steps zur direkten Navigation und Verlinkung

Die Vergabe eindeutiger IDs an deine Steps ist, wie in Teil 2 erwähnt, extrem nützlich für die Navigation.

  * **HTML-Anker (Hash-Navigation)**:

      * Wenn ein Step eine ID hat, z.B. `<div id="einfuehrung" class="step" ...>`, kannst du direkt zu diesem Step navigieren, indem du den Hash-Identifier an die URL deiner Präsentationsdatei anhängst:
        `meine_praesentation.html#/einfuehrung`
      * **Beim Laden der Seite**: Wenn die URL beim ersten Aufruf bereits einen solchen Hash enthält, springt `impress.js` direkt zum entsprechenden Step.
      * **Während der Präsentation**: Wenn du navigierst, aktualisiert `impress.js` automatisch den Hash in der URL-Leiste des Browsers. Das bedeutet, der Browser-Verlauf (Vorwärts/Rückwärts-Buttons) funktioniert und spiegelt die Step-Navigation wider. Benutzer können die URL eines bestimmten Steps kopieren und teilen.
      * **Eindeutigkeit ist entscheidend**: Stelle sicher, dass jede ID im Dokument nur einmal vorkommt, wie es die HTML-Spezifikation vorschreibt.

  * **Interne Verlinkung zwischen Steps mit `<a>`-Tags**:

      * Du kannst Standard-HTML-Hyperlinks (`<a>`-Tags) innerhalb des Inhalts eines Steps verwenden, um Querverweise oder explizite Navigationspfade zu anderen Steps zu erstellen.
      * Das `href`-Attribut des Links muss auf den Hash der ID des Ziel-Steps zeigen.

    **Beispielcode für interne Verlinkung:**

    ```html
    <div id="impress">
        <div id="start" class="step" data-x="0" data-y="0">
            <h1>Willkommen</h1>
            <p>Von hier aus können Sie zu <a href="#thema-a">Thema A</a> oder <a href="#thema-b">Thema B</a> springen.</p>
            <p>Oder folgen Sie einfach dem <a href="#uebersicht">Pfad zur Übersicht</a>.</p>
        </div>

        <div id="thema-a" class="step" data-x="1200" data-y="-200">
            <h2>Thema A</h2>
            <p>Details zu Thema A...</p>
            <p><a href="#start">Zurück zum Start</a></p>
        </div>

        <div id="thema-b" class="step" data-x="1200" data-y="800">
            <h2>Thema B</h2>
            <p>Details zu Thema B...</p>
            <p><a href="#start">Zurück zum Start</a></p>
        </div>

        <div id="uebersicht" class="step" data-x="3000" data-y="1500" data-scale="6">
            <h3>Übersicht</h3>
            <p><a href="#start">Start</a> | <a href="#thema-a">Thema A</a> | <a href="#thema-b">Thema B</a></p>
        </div>
    </div>
    <script>impress().init();</script>
    ```

      * Wenn ein Benutzer auf einen solchen Link klickt, fängt `impress.js` dieses Ereignis ab (da es ein interner Hash-Link ist) und führt statt eines abrupten Seiten-Neuladens einen sanften, animierten Übergang zum Ziel-Step durch.

### Anpassen des Navigationsverhaltens (Ausblick)

Während die Standardnavigation sehr robust ist, gibt es Situationen, in denen Anpassungen gewünscht sind.

  * **Konfigurationsoptionen bei `impress().init({...})`**:

      * Obwohl der Kern von `impress.js` relativ wenige direkte Konfigurationsoptionen für die *Art* der Tastenbelegung bietet, können Optionen wie `transitionDuration` (Standard: 1000ms) das *Gefühl* der Navigation stark beeinflussen. Längere Dauer = langsamere Übergänge.
      * Einige Plugins, die Navigations-UI-Elemente hinzufügen (wie das `navigation` oder `toolbar` Plugin), können eigene Konfigurationsmöglichkeiten für diese Elemente mitbringen.

  * **Deaktivieren der Standard-Mausklick-Navigation**:

      * Wie oben erwähnt, kann es notwendig sein, das Standardverhalten "Klick-zum-nächsten-Step" zu unterbinden. Dies geschieht am zuverlässigsten, indem man Klick-Events auf den Inhalten der Steps gezielt behandelt:
        ```javascript
        // Beispiel mit jQuery (kann auch mit reinem JavaScript gemacht werden)
        // $('.step').on('click', function(event) {
        //   if (event.target.tagName.toLowerCase() !== 'a') { // Nur stoppen, wenn nicht auf einen Link geklickt wurde
        //     event.stopPropagation();
        //   }
        // });
        ```
        Ein solcher Code würde verhindern, dass Klicks auf einen Step (außer auf Links) an `impress.js` weitergeleitet werden.

  * **Programmatische Navigation über die API (Vorschau auf Teil 7)**:

      * Die `impress.js`-API bietet volle programmatische Kontrolle:
          * `impress().next()`: Geht zum nächsten Step.
          * `impress().prev()`: Geht zum vorherigen Step.
          * `impress().goto( 'step-id' )`: Springt direkt zum Step mit der angegebenen ID.
          * `impress().goto( stepElement )`: Springt direkt zum angegebenen DOM-Element eines Steps.
          * `impress().goto( stepIndex )`: Springt zum Step mit dem angegebenen numerischen Index (beginnend bei 0).
      * Mit diesen Funktionen kannst du eigene Navigationssteuerungen (z.B. benutzerdefinierte Buttons, Menüs) erstellen oder auf benutzerdefinierte Ereignisse reagieren.

  * **Reagieren auf Navigations-Events (Vorschau auf Teil 7)**:

      * `impress.js` löst Events aus, wenn sich der aktive Step ändert:
          * `impress:stepenter`: Wird auf dem Step-Element ausgelöst, das gerade aktiv wird.
          * `impress:stepleave`: Wird auf dem Step-Element ausgelöst, das gerade verlassen wird.
      * Du kannst Event-Listener für diese Events registrieren, um beispielsweise Animationen innerhalb eines Steps zu starten/stoppen, Videos zu steuern oder den Zustand deiner eigenen UI-Elemente zu aktualisieren.

Die Steuerung und Navigation sind zentrale Aspekte, um das Potenzial von `impress.js` für dynamische und nicht-lineare Präsentationen auszuschöpfen. Mit den Standardeinstellungen hast du bereits eine solide Basis, und mit etwas Anpassung kannst du das Erlebnis perfekt auf deine Bedürfnisse zuschneiden.



## Teil 6: Styling von `impress.js`-Präsentationen mit CSS

Während `impress.js` die Logik für die räumlichen Transformationen und die Navigation deiner Steps bereitstellt, liegt die visuelle Gestaltung – das Aussehen deiner Folien und die Art der Übergänge – vollständig in der Hand von CSS (Cascading Style Sheets). Ein gutes Verständnis, wie `impress.js` und CSS zusammenspielen, ist entscheidend für die Erstellung professioneller und ansprechender Präsentationen.

### Die Rolle von CSS in `impress.js`-Präsentationen

1.  **Erscheinungsbild der Steps**: Alles, was du innerhalb eines `<div class="step">` siehst – Textformatierung, Hintergrundfarben, Bilder, Rahmen, Schatten usw. – wird durch CSS-Regeln definiert, die du entweder selbst schreibst oder aus Vorlagen übernimmst. `impress.js` greift hier nicht direkt in das Inhaltsstyling ein.
2.  **Übergangsanimationen**: Wenn du von einem Step zum nächsten navigierst, berechnet `impress.js` die notwendigen Änderungen der `transform`-Eigenschaft (Position, Rotation, Skalierung) des Hauptcontainers (`<div id="impress">` oder eines darin verschachtelten "canvas"-Elements). Die eigentliche *Animation* dieses Übergangs – also wie sanft und mit welcher Geschwindigkeit die Kamera von einem Punkt zum anderen schwenkt – wird durch **CSS-Transitions** auf diesen Transformationseigenschaften gesteuert.
3.  **Zustandsabhängiges Styling**: `impress.js` fügt dem `<body>`-Element und den einzelnen `.step`-Elementen dynamisch CSS-Klassen hinzu, die den aktuellen Zustand der Präsentation oder eines Steps widerspiegeln (z.B. ob ein Step aktiv, bereits besucht oder zukünftig ist). Diese Klassen kannst du nutzen, um Steps je nach ihrem Zustand unterschiedlich darzustellen.

### Grundlegendes CSS-Setup und empfohlene Basis-Stylesheets

Um deine Präsentation zu gestalten, wirst du mindestens eine eigene CSS-Datei erstellen und diese im `<head>` deiner HTML-Datei verlinken:

```html
<head>
    <meta charset="utf-f_8" />
    <title>Meine gestylte impress.js Präsentation</title>
    <link href="css/impress-common.css" rel="stylesheet" /> <link href="css/meine-praesentation-styles.css" rel="stylesheet" /> </head>
```

**1. `impress-common.css` (aus dem `impress.js`-Paket)**

  * **Zweck**: Diese Datei, die du im `css`-Ordner des offiziellen `impress.js`-Repositorys findest, enthält einige grundlegende und nützliche CSS-Regeln. Sie ist nicht zwingend erforderlich, bildet aber eine gute Ausgangsbasis und behebt einige browserübergreifende Inkonsistenzen.
  * **Wichtige Inhalte (eine genaue Analyse lohnt sich für das Verständnis):**
      * **Fallback-Nachricht**: Stile für `.fallback-message`, wenn `body.impress-not-supported` aktiv ist, um diese Nachricht sichtbar und formatiert darzustellen.
      * **Grundlagen für den Support-Fall**: Stile für `body.impress-supported` (oft `height: 100%; overflow: hidden;` um Scrollbalken zu vermeiden) und `body.impress-enabled` (kann z.B. die `perspective` für den 3D-Raum setzen, falls nicht anders konfiguriert).
      * **Step-Basics**: Grundlegende Stile für `.step`-Elemente, wie `position: absolute;` (da ihre Position durch `transform: translate(...)` gesteuert wird), `transform-style: preserve-3d;` (wichtig für verschachtelte 3D-Transformationen, falls du komplexere Step-Inhalte hast) und eine Standard-Transition für `opacity`.
      * **Zustandsdefinitionen (Basis)**: Oft enthält sie bereits rudimentäre Stile für `.step.past { opacity: 0.3; }` und `.step.future { opacity: 0.3; }` sowie `.step.active { opacity: 1; }`, um nicht-aktive Steps leicht auszublenden.
  * **Empfehlung**: Es ist ratsam, sich den Inhalt von `impress-common.css` anzusehen. Du kannst sie entweder direkt einbinden oder die für dich relevanten Teile in dein eigenes Stylesheet übernehmen und anpassen.

**2. `impress-demo.css` (aus dem `impress.js`-Paket)**

  * **Zweck**: Diese Datei enthält alle spezifischen Stile, die für die offizielle `impress.js`-Demopräsentation (`index.html` im Hauptverzeichnis des Repositorys) verwendet werden.
  * **Nutzung**: Sie ist **nicht** als allgemeine Basis für deine eigenen Präsentationen gedacht, da sie sehr umfangreich und auf die Demo zugeschnitten ist. Sie dient jedoch hervorragend als **Inspirationsquelle** und zeigt, wie komplexe Layouts, thematische Gestaltungen für einzelne Steps und ansprechende visuelle Effekte mit CSS in `impress.js` umgesetzt werden können.

**3. Deine eigene CSS-Datei (`meine-praesentation-styles.css`)**

  * Hier definierst du alle spezifischen Stile für deine Präsentation: das Aussehen der Steps, Hintergründe, Schriftarten, Farben und benutzerdefinierte Animationen.

### Wichtige CSS-Klassen, die von `impress.js` dynamisch verwaltet werden

`impress.js` manipuliert Klassen an verschiedenen Elementen, um deren Zustand widerzuspiegeln. Diese Klassen sind deine wichtigsten Werkzeuge für zustandsabhängiges Styling.

**1. Klassen auf dem `<body>`-Element:**

  * **`impress-not-supported`**:
      * Initial beim Laden der Seite vorhanden.
      * Wird von `impress.js` entfernt, falls der Browser die notwendigen Features unterstützt und `impress.js` erfolgreich startet.
      * CSS-Selektor: `body.impress-not-supported .fallback-message { display: block; }` (um die Fallback-Nachricht nur dann anzuzeigen).
  * **`impress-supported`**:
      * Wird hinzugefügt, wenn der Browser die CSS3 3D-Transformationen und andere Kernfeatures unterstützt.
      * Kann für globales Styling verwendet werden, das nur greift, wenn die Präsentation grundsätzlich laufen kann.
  * **`impress-enabled`**:
      * Wird hinzugefügt, nachdem `impress().init()` erfolgreich aufgerufen wurde und die Präsentation vollständig initialisiert und aktiv ist. Dies ist oft der Haupt-Hook, um Präsentations-spezifische Stile anzuwenden und die Fallback-Nachricht endgültig auszublenden:
        ```css
        body.impress-enabled .fallback-message { display: none; }
        ```
  * **`impress-disabled`**: (Seltener, aber möglich)
      * Könnte hinzugefügt werden, wenn `impress().tear()` aufgerufen wird oder die Präsentation anderweitig deaktiviert wird. Das `body` würde dann nicht mehr `impress-enabled` sein.
  * **`impress-overview`**:
      * Wird dem `<body>`-Element (oder manchmal dem `#impress`-Container, je nach Version/Konfiguration) hinzugefügt, wenn der Overview-Modus (durch Drücken von ESC) aktiv ist.
      * Ermöglicht es dir, das Aussehen der gesamten Seite oder der Steps speziell für die Übersichtsansicht anzupassen (z.B. Hintergründe abdunkeln, Step-Hervorhebungen ändern).
        ```css
        body.impress-overview {
            background-color: #333; /* Dunklerer Hintergrund im Overview */
        }
        body.impress-overview .step {
            opacity: 0.5 !important; /* Alle Steps im Overview leicht transparent machen */
            border: 1px dashed #fff; /* Anderer Rahmen im Overview */
        }
        body.impress-overview .step.active {
            opacity: 1 !important; /* Den "Ursprungs"-Step im Overview hervorheben */
            border: 2px solid yellow;
        }
        ```

**2. Klassen und Stile auf dem `#impress`-Container (oder dem Canvas-Element):**

  * `impress.js` erzeugt oft ein internes `div` mit der Klasse `canvas` innerhalb von `#impress`. Dieser `canvas`-Div (oder `#impress` selbst, wenn `canvas` nicht verwendet wird) ist das Element, dessen `transform`-Eigenschaft dynamisch per JavaScript (Inline-Style) geändert wird, um die Kamerafahrten zu realisieren.
  * Die CSS-Transition für diese Transformationen wird typischerweise auf dieses Element angewendet.

**3. Klassen auf den `.step`-Elementen:**

Das sind die wichtigsten Klassen für das Styling einzelner Steps je nach ihrem Zustand in der Präsentationsabfolge:

  * **`step`**: Die Basisklasse, die jedes Step-Element haben muss.
  * **`active`**:
      * Wird dem aktuell sichtbaren, fokussierten Step hinzugefügt.
      * Entfernt, wenn der Step verlassen wird.
      * **Verwendung**: Um den aktuellen Step hervorzuheben (z.B. volle Opazität, spezieller Schatten, andere Umrandung) oder um Animationen *innerhalb* des Steps zu starten, sobald er aktiv wird.
        ```css
        .step {
            transition: opacity 1s ease-in-out, transform 0.5s ease-out; /* Übergang für Opazität und eigene Transformationen des Steps */
        }
        .step.active {
            /* Stile für den aktiven Step */
            border-color: blue;
            box-shadow: 0 0 20px rgba(0, 0, 255, 0.5);
        }
        ```
  * **`past`**:
      * Wird einem Step hinzugefügt, nachdem er verlassen wurde und in der Navigationshistorie *vor* dem aktuellen `active`-Step liegt.
      * **Verwendung**: Um bereits besuchte Steps visuell in den Hintergrund treten zu lassen (z.B. Opazität reduzieren, ausgrauen, kleiner skalieren).
        ```css
        .step.past {
            opacity: 0.2;
            filter: grayscale(80%); /* Beispiel: Ausgrauen */
        }
        ```
  * **`future`**:
      * Wird einem Step hinzugefügt, der in der Navigationshistorie *nach* dem aktuellen `active`-Step liegt und noch nicht besucht wurde.
      * **Verwendung**: Ähnlich wie `past`, um zukünftige Steps weniger prominent darzustellen.
        ```css
        .step.future {
            opacity: 0.2;
        }
        ```
    Oft werden `past` und `future` initial gleich gestylt, um einen klaren Fokus auf den `active` Step zu legen:
    ```css
    .step {
        opacity: 0; /* Standardmäßig unsichtbar, bis sie `active` werden, oder leicht sichtbar */
        transition: opacity 0.8s ease-in-out;
    }
    .step.active {
        opacity: 1;
    }
    .step.past, .step.future { /* Wenn sie nicht komplett unsichtbar sein sollen */
        opacity: 0.25;
    }
    ```
    Das genaue Verhalten (ob Steps initial `opacity: 0` haben und dann eingeblendet werden oder immer eine gewisse Grundsichtbarkeit haben) hängt von deinem CSS ab. `impress.js` selbst steuert primär die `active`, `past`, `future` Klassen.

### Grundlegende CSS-Anpassungen

Hier sind einige Beispiele, wie du das grundlegende Aussehen deiner Präsentation anpassen kannst. Diese Regeln gehören in deine eigene CSS-Datei (z.B. `meine-praesentation-styles.css`).

  * **Globaler Hintergrund der Präsentation**:

    ```css
    body.impress-enabled { /* Stile nur anwenden, wenn impress.js läuft */
        background-color: #f0f0f0; /* Ein heller Grauton */
        /* Oder ein Farbverlauf: */
        /* background-image: linear-gradient(to bottom, #e0e0e0, #c0c0c0); */
        /* Oder ein Hintergrundbild: */
        /* background-image: url('../images/mein-hintergrund.jpg'); */
        /* background-size: cover; */
        /* background-repeat: no-repeat; */
    }
    ```

  * **Standard-Styling für alle `.step`-Elemente**:

    ```css
    .step {
        /* Dimensionen */
        width: 960px;
        height: 700px; /* Höhe ist optional, Inhalt kann Höhe bestimmen */
        padding: 40px 60px; /* Innenabstand */

        /* Hintergrund und Rahmen */
        background-color: white;
        border: 1px solid #ccc;
        border-radius: 12px;
        box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.1);

        /* Typografie */
        font-family: 'Helvetica Neue', Arial, sans-serif;
        font-size: 22px;
        line-height: 1.5;
        color: #333;

        /* Wichtig für impress.js: Muss ein positioniertes Element sein */
        position: absolute; 
        /* Damit 3D-Transformationen von Kindelementen korrekt sind, falls benötigt */
        transform-style: preserve-3d; 
    }

    /* Styling für Überschriften und Absätze innerhalb der Steps */
    .step h1, .step h2, .step h3 {
        font-weight: bold;
        color: #005a9e; /* Eine Akzentfarbe */
        margin-bottom: 0.5em;
    }
    .step h1 { font-size: 2.5em; }
    .step h2 { font-size: 2em; }
    .step p { margin-bottom: 1em; }
    .step a { color: #0077cc; text-decoration: none; }
    .step a:hover { text-decoration: underline; }
    ```

  * **Styling für spezifische Steps über ihre ID**:
    Wenn du einem Step eine ID gegeben hast (z.B. `<div id="fazit" class="step">...</div>`), kannst du ihn gezielt stylen:

    ```css
    #fazit {
        background-color: #333;
        color: white;
        border-color: #555;
    }
    #fazit h2 {
        color: #87cefa; /* Hellblau */
    }
    ```

### Styling der Übergänge (CSS Transitions)

Die "Kamerafahrt" zwischen den Steps wird durch CSS-Transitions auf dem Element gesteuert, das `impress.js` für die globalen Transformationen verwendet. Dies ist meist ein von `impress.js` erzeugtes `div` mit der Klasse `canvas` innerhalb von `<div id="impress">`, oder `#impress` selbst.

  * **Kern-CSS-Eigenschaft**: `transition`
  * **Ziel-Eigenschaft**: Die `transform`-Eigenschaft dieses Canvas-Elements wird von `impress.js` per JavaScript (Inline-Style) geändert. Die Transition sorgt dafür, dass dieser Wechsel animiert wird.
  * **Beispiel für sanfte Übergänge**:
    ```css
    /* In impress-common.css oder deinem eigenen Stylesheet */
    .impress-enabled div#impress .canvas { /* Ziel ist das Canvas-Div */
        /* Definiert den Ursprungspunkt für die Transformationen der gesamten Leinwand.
           0 0 0 ist oft die obere linke Ecke der Leinwand.
           Kann auch '50% 50%' oder 'center center' sein, je nach gewünschtem Effekt
           und wie die Steps initial positioniert werden.
           Der Default von impress.js für den `transform-origin` des Canvas ist meist 0 0.
        */
        transform-origin: 0 0; 
        
        /* Die eigentliche Transition:
           - 'transform': Die Eigenschaft, die animiert wird.
           - '1s': Die Dauer der Animation (1 Sekunde). Du kannst dies anpassen (z.B. 700ms, 1.5s).
           - 'ease-in-out': Die Timing-Funktion, die die Beschleunigungskurve steuert.
             Weitere Optionen: linear, ease, ease-in, ease-out, cubic-bezier(...).
        */
        transition: transform 1s ease-in-out;

        /* Wichtig für 3D-Transformationen von Kindelementen (den Steps) innerhalb des Canvas */
        transform-style: preserve-3d; 
    }

    /* Manchmal wird auch die Opazität des Canvas für globale Effekte animiert */
    /* .impress-enabled div#impress .canvas {
        transition: transform 1s ease-in-out, opacity 0.5s linear;
    } */
    ```
  * **Anpassung der Übergangsdauer**: Ändere einfach den Wert für `transition-duration` (z.B. `transition: transform 700ms ease-out;`).
  * **Unterschiedliche Timing-Funktionen**:
      * `ease`: Startet langsam, beschleunigt in der Mitte, endet langsam (Standard).
      * `linear`: Gleichmäßige Geschwindigkeit über die gesamte Dauer.
      * `ease-in`: Langsamer Start.
      * `ease-out`: Langsames Ende.
      * `ease-in-out`: Langsamer Start und langsames Ende (oft sehr angenehm).
      * `cubic-bezier(n,n,n,n)`: Erlaubt die Definition einer komplett eigenen Beschleunigungskurve.

### Fortgeschrittenes Styling für individuelle Looks und Animationen

  * **Zustandsabhängige Animationen für Steps**:
    Kombiniere die `.active`, `.past`, `.future` Klassen mit CSS-Transitions oder CSS-Keyframe-Animationen, um Steps beim Betreten/Verlassen nicht nur ihre Opazität ändern zu lassen, sondern auch andere Eigenschaften wie `transform` (für eine zusätzliche kleine Bewegung des Steps selbst) oder `filter`.

    ```css
    .step {
        opacity: 0.3;
        transform: scale(0.8); /* Steps sind standardmäßig etwas kleiner */
        transition: opacity 0.5s ease-in-out, transform 0.5s ease-in-out;
    }
    .step.active {
        opacity: 1;
        transform: scale(1); /* Aktiver Step wird auf volle Größe skaliert */
    }
    ```

  * **CSS-Keyframe-Animationen (`@keyframes`) *innerhalb* von Steps**:
    Du kannst Elemente *innerhalb* eines Steps animieren, sobald dieser Step die Klasse `.active` erhält.

    ```css
    /* Keyframe-Animation definieren */
    @keyframes fadeInText {
        from { opacity: 0; transform: translateY(20px); }
        to   { opacity: 1; transform: translateY(0); }
    }

    /* Animation auf ein Element im aktiven Step anwenden */
    .step.active .animated-text-element {
        animation-name: fadeInText;
        animation-duration: 0.8s;
        animation-timing-function: ease-out;
        animation-fill-mode: both; /* Behält den Endzustand der Animation bei */
        animation-delay: 0.3s; /* Startet mit einer kleinen Verzögerung, nachdem der Step aktiv wurde */
    }
    ```

    HTML:

    ```html
    <div id="animated-content-step" class="step" data-x="0" data-y="0">
        <h2 class="animated-text-element">Dieser Text</h2>
        <p class="animated-text-element" style="animation-delay: 0.5s;">blendet sich ein.</p> </div>
    ```

  * **Verwendung von Pseudo-Elementen (`::before`, `::after`)**:
    Für dekorative Zwecke (z.B. benutzerdefinierte Hintergründe, Rahmen, Nummerierungen für Steps) sind Pseudo-Elemente sehr nützlich und halten dein HTML sauber.

  * **Responsive Gestaltung von Steps**:
    Dies ist eine fortgeschrittene Herausforderung mit `impress.js`, da die Kern-Transformationen pixelbasiert sind.

      * **Relative Einheiten im Step-Inhalt**: Verwende `em`, `rem` oder `%` für Schriftgrößen und Layouts *innerhalb* der Steps, damit diese besser mit der Skalierung des Steps harmonieren.
      * **`viewport`-Einheiten (`vw`, `vh`)**: Können für die Größe der Steps selbst oder für Elemente darin verwendet werden, um sie an die Größe des Browserfensters anzupassen. Dies kann aber die `impress.js`-Skalierung beeinflussen und erfordert sorgfältige Tests.
      * **Das `resize`-Plugin**: `impress.js` hat ein `resize`-Plugin, das versucht, die Skalierung der gesamten Präsentation anzupassen, wenn die Fenstergröße geändert wird. Es skaliert den gesamten `#impress`-Container, um das Seitenverhältnis der Steps beizubehalten.
      * **Media Queries**: Können verwendet werden, um das grundlegende CSS der Steps (z.B. `width`, `height`, `font-size`) für sehr unterschiedliche Bildschirmgrößen anzupassen, bevor `impress.js` seine Transformationen anwendet.

### Zusammenspiel mit JavaScript für dynamisches Styling (Kurzer Ausblick)

Während CSS für das meiste Styling ausreicht, kannst du JavaScript nutzen, um auf `impress.js`-Events (wie `impress:stepenter`) zu reagieren und dynamisch Klassen zu ändern oder Inline-Styles zu setzen. Dies ermöglicht noch komplexere interaktive visuelle Effekte, die über die deklarativen Möglichkeiten von CSS hinausgehen. Mehr dazu in Teil 7, wenn wir die API und Events genauer betrachten.

Mit diesen CSS-Techniken kannst du das Aussehen deiner `impress.js`-Präsentationen vollständig kontrollieren und an deine Bedürfnisse anpassen, von schlicht und elegant bis hin zu komplex und effektgeladen.


## Teil 7: Die `impress.js` API und Ereignisbehandlung

Bisher haben wir uns darauf konzentriert, `impress.js`-Präsentationen deklarativ über HTML-Datenattribute und CSS zu erstellen. Jetzt tauchen wir tiefer in die Materie ein und erkunden die JavaScript-Programmierschnittstelle (API) sowie das Ereignissystem von `impress.js`. Diese Werkzeuge ermöglichen eine dynamische Steuerung und Interaktion, die weit über die Standardnavigation hinausgeht.

### Einführung in die `impress.js` JavaScript-API

Die API von `impress.js` dient als deine programmatische "Fernbedienung" für die Präsentation. Mit ihr kannst du:

  * Die Präsentation initialisieren und konfigurieren.
  * Programmatisch zwischen Steps navigieren.
  * Informationen über den aktuellen Zustand der Präsentation abrufen.
  * Auf interne Ereignisse der Präsentation reagieren.

**1. Das API-Objekt erhalten:**

Der erste Schritt zur Nutzung der API ist der Zugriff auf das API-Objekt. Dies geschieht durch den Aufruf der globalen `impress()`-Funktion.

  * **Standardfall (Root-Container mit `id="impress"`)**:
    Wenn dein Hauptcontainer die Standard-ID `impress` hat, rufst du die Funktion ohne Argumente auf:

    ```javascript
    var impressApi = impress();
    ```

    Die Variable `impressApi` (du kannst sie beliebig benennen) hält nun das API-Objekt, auf dem du Methoden aufrufen kannst.

  * **Mit spezifischer Root-ID**:
    Falls dein Hauptcontainer eine andere ID hat (z.B. `<div id="meineShow">...</div>`), übergibst du diese ID als String an die `impress()`-Funktion:

    ```javascript
    var impressApi = impress('meineShow');
    ```

    **Wichtig**: Dieser Aufruf `impress(rootId?)` gibt das API-Objekt zurück, **initialisiert aber die Präsentation noch nicht\!** Die Initialisierung erfolgt durch einen separaten Methodenaufruf.

### Die `init()` Methode im Detail

Die `init()`-Methode ist fundamental, da sie die `impress.js`-Präsentation aufbaut und startet.

  * **Aufruf**:

    ```javascript
    impressApi.init(config); // oder impress().init(config);
    ```

  * **`config` (optionales Konfigurationsobjekt)**:
    Du kannst der `init()`-Methode ein JavaScript-Objekt mit Konfigurationsoptionen übergeben, um das Standardverhalten von `impress.js` anzupassen. Hier sind einige der wichtigsten Optionen (die genauen Standardwerte können je nach `impress.js`-Version leicht variieren; ein Blick in die `src/impress.js`-Quelldatei oder die offizielle Dokumentation ist bei Bedarf empfehlenswert):

      * `width`: Die Standardbreite eines Steps in Pixeln.
          * *Standardwert*: Oft `1024`.
          * *Beispiel*: `{ width: 1280 }`
      * `height`: Die Standardhöhe eines Steps in Pixeln.
          * *Standardwert*: Oft `768`.
          * *Beispiel*: `{ height: 720 }`
      * `maxScale`: Der maximale Skalierungsfaktor, der auf Steps im Overview-Modus angewendet wird, um sicherzustellen, dass sie nicht zu groß werden.
          * *Standardwert*: `3` (früher oft `1`). Ein Wert von `0` würde bedeuten, dass es keine Obergrenze gibt.
          * *Beispiel*: `{ maxScale: 2 }`
      * `minScale`: Der minimale Skalierungsfaktor, der auf Steps angewendet wird (z.B. wenn sie sehr weit weg sind). Ein Wert von `0` (Standard) erlaubt es Steps, beliebig klein zu werden.
          * *Standardwert*: `0`.
          * *Beispiel*: `{ minScale: 0.1 }` (Steps werden nie kleiner als 10% ihrer Größe)
      * `perspective`: Der CSS `perspective`-Wert in Pixeln, der auf den Präsentationscontainer angewendet wird. Dieser Wert bestimmt die Stärke des 3D-Effekts. Kleinere Werte bedeuten eine stärkere, "dramatischere" Perspektive.
          * *Standardwert*: `1000`.
          * *Beispiel*: `{ perspective: 800 }`
      * `transitionDuration`: Die Standarddauer für CSS-Übergänge zwischen den Steps in Millisekunden.
          * *Standardwert*: `1000` (also 1 Sekunde).
          * *Beispiel*: `{ transitionDuration: 700 }` (für schnellere Übergänge)
      * `rootId`: (Normalerweise nicht hier gesetzt, sondern über `impress(rootId?)`) Die ID des Wurzelelements der Präsentation.

    **Beispiel für die Initialisierung mit Konfiguration:**

    ```javascript
    var api = impress();
    api.init({
        width: 1600,
        height: 900,
        perspective: 1200,
        transitionDuration: 800
    });
    ```

  * **Was genau passiert während `init()` (technische Details):**

    1.  **Browser-Kompatibilitätsprüfung**: Überprüft, ob der Browser die notwendigen DOM- und CSS3-Funktionen unterstützt (z.B. `document.body`, `classList`, `dataset`, CSS 3D Transforms).
    2.  **DOM-Referenzen**: Holt Referenzen auf das `document`, `window`, das Wurzelelement (`#impress`) und erzeugt ggf. ein inneres "Canvas"-Element, auf das die Transformationen angewendet werden.
    3.  **Klassen-Management**: Fügt dem `<body>` und dem Wurzelelement CSS-Klassen wie `impress-supported` und `impress-enabled` hinzu und entfernt `impress-not-supported`.
    4.  **Step-Erfassung**: Durchsucht das Wurzelelement nach allen Kindelementen mit der Klasse `step`.
    5.  **Datenextraktion**: Für jeden gefundenen `.step` werden die `data-*`-Attribute (wie `data-x`, `data-y`, `data-z`, `data-rotate-x`, `data-scale` etc.) ausgelesen und intern in einem Datenobjekt für jeden Step gespeichert. Fehlende Attribute erhalten Standardwerte (meist 0 für Positionen/Rotationen, 1 für Skalierung).
    6.  **Transformationsberechnung**: Basierend auf den ausgelesenen Daten werden die initialen CSS-Transformationen für jeden Step berechnet.
    7.  **Event-Listener**: Es werden Event-Listener für Tastatureingaben (Pfeiltasten, Leertaste etc.), Änderungen des URL-Hash (`hashchange`-Event) und Mausklicks (für die Standard-Klicknavigation) eingerichtet.
    8.  **Initialer Step**: Die Präsentation navigiert zum initialen Step. Dies ist entweder der Step, dessen ID im URL-Hash angegeben ist (z.B. `index.html#/mein-start-step`), oder, falls kein Hash vorhanden ist, der erste `.step` im DOM.
    9.  **`impress:init`-Event**: Schließlich wird das `impress:init`-Ereignis auf dem Wurzelelement ausgelöst, um anderen Teilen des Codes (oder Plugins) zu signalisieren, dass die Präsentation einsatzbereit ist. Das `event.detail`-Objekt dieses Events enthält in der Regel eine Referenz auf die `impressApi` selbst.

### Navigationsmethoden der API im Detail

Sobald die Präsentation initialisiert ist, kannst du sie mit folgenden API-Methoden programmatisch steuern:

  * **`impressApi.next()`**:

      * Navigiert zum **nächsten** Step in der Präsentationsreihenfolge.
      * Die Reihenfolge basiert standardmäßig auf der DOM-Struktur der `.step`-Elemente. Plugins (wie das `rel`-Plugin) können diese Logik modifizieren.
      * **Rückgabewert**: Gibt das DOM-Element des Ziel-Steps zurück, zu dem navigiert wurde. Wenn es keinen nächsten Step gibt (man ist bereits beim letzten), gibt die Methode `false` zurück.
      * **Interne Logik (vereinfacht)**: Ermittelt den Index des aktuellen Steps, erhöht ihn und ruft dann intern `goto()` mit dem neuen Index oder dem entsprechenden Step-Element auf. Berücksichtigt dabei Steps, die übersprungen werden sollen (z.B. mit der Klasse `.skip` oder durch das `skip`-Plugin).

  * **`impressApi.prev()`**:

      * Navigiert zum **vorherigen** Step.
      * **Rückgabewert**: Gibt das DOM-Element des Ziel-Steps zurück. Wenn es keinen vorherigen Step gibt (man ist bereits beim ersten), gibt die Methode `false` zurück.
      * **Interne Logik (vereinfacht)**: Ähnlich wie `next()`, nur dass der Index dekrementiert wird.

  * **`impressApi.goto( el, duration )`**:

      * Dies ist die **flexibelste und mächtigste Navigationsmethode**. Sie ermöglicht es, zu einem beliebigen Step zu springen.
      * **Parameter `el` (Ziel-Step)**: Kann auf verschiedene Weisen spezifiziert werden:
        1.  **DOM-Element**: Du kannst ein direktes DOM-Element eines Steps übergeben.
            ```javascript
            var zielStepElement = document.getElementById('mein-spezieller-step');
            impressApi.goto( zielStepElement );
            ```
        2.  **ID-String**: Du kannst die `id` des Ziel-Steps als String übergeben.
            ```javascript
            impressApi.goto( 'mein-spezieller-step' );
            ```
        3.  **Numerischer Index (0-basiert)**: Du kannst den Index des Steps angeben, basierend auf seiner Position in der internen Liste aller Steps (die der DOM-Reihenfolge entspricht).
            ```javascript
            impressApi.goto( 0 ); // Geht zum ersten Step
            impressApi.goto( 2 ); // Geht zum dritten Step (Index 2)
            ```
        4.  **Spezielle Step-Referenzen (Plugins)**: Einige Plugins könnten spezielle Referenzen wie `impressApi.goto("next-on-path")` einführen, aber die oben genannten sind die Kernfunktionalitäten.
      * **Parameter `duration` (optionale Übergangsdauer)**:
          * Ermöglicht es, die Dauer der CSS-Transition *speziell für diesen einen Navigationsaufruf* zu überschreiben. Der Wert wird in Millisekunden angegeben.
          * ```javascript
              impressApi.goto( 'wichtiger-hinweis', 2000 ); // Übergang dauert 2 Sekunden
              impressApi.goto( 'schneller-wechsel', 300 );  // Übergang dauert 0.3 Sekunden
            ```
          * Wenn `duration` nicht angegeben wird oder `undefined` ist, verwendet `impress.js` den globalen `transitionDuration`-Wert, der bei der Initialisierung festgelegt wurde (Standard: 1000ms).
          * **Technischer Hintergrund**: `impress.js` setzt kurzzeitig eine spezifische `transition-duration` auf das Canvas-Element, führt die Transformation durch und setzt die Dauer dann wieder auf den globalen Wert zurück.
      * **Rückgabewert**: Gibt das DOM-Element des Ziel-Steps zurück, falls dieser gefunden und angesteuert werden konnte. Gibt `false` zurück, wenn der angegebene Ziel-Step nicht existiert.
      * **Interne Logik**: `goto()` identifiziert den Ziel-Step basierend auf dem `el`-Parameter, berechnet die notwendigen Transformationen für das Canvas-Element, um diesen Step in den Mittelpunkt zu rücken, wendet diese Transformationen an (was die CSS-Transition auslöst) und aktualisiert den internen Zustand (`active` Step etc.).

  * **`impressApi.home()` und `impressApi.end()`**:

      * Im Kern von `impress.js` gibt es **keine** dedizierten öffentlichen API-Methoden namens `home()` oder `end()`.
      * Dieses Verhalten wird typischerweise über `impressApi.goto(0)` für den ersten Step und `impressApi.goto(indexOfLastStep)` für den letzten Step realisiert.
      * Um den Index des letzten Steps zu erhalten, könntest du die (nicht-öffentliche, aber oft zugängliche) interne Liste der Steps verwenden oder die Anzahl der Steps zählen:
        ```javascript
        // Nicht Teil der öffentlichen API, aber oft so gemacht:
        // var steps = impressApi.getSteps(); // Hypothetische Methode, oder intern ermitteln
        // if (steps && steps.length > 0) {
        //     impressApi.goto(steps.length - 1); // Zum letzten Step
        // }
        // Sicherer ist es, die Steps selbst im DOM zu zählen, wenn keine getSteps() API existiert.
        ```
        Die Tastaturkürzel (Home/Ende) implementieren diese Logik intern.

  * **`impressApi.getActiveStep()`**:

      * Gibt das DOM-Element des aktuell aktiven (sichtbaren) Steps zurück.
      * Sehr nützlich, um Informationen über den aktuellen Step abzufragen oder Aktionen relativ zum aktuellen Zustand auszuführen.

### Ereignisbehandlung (`EventListeners`) im Detail

`impress.js` löst benutzerdefinierte DOM-Events aus, die es dir ermöglichen, auf bestimmte Zustandsänderungen der Präsentation zu reagieren. Diese Events werden auf dem **Root-Element der Präsentation** (also dem `<div id="impress">` oder dem Element, das bei `impress(rootId)` angegeben wurde) ausgelöst.

**1. Event-Listener registrieren:**

Du verwendest die Standard-DOM-Methode `addEventListener`, um auf diese Events zu lauschen:

```javascript
var rootElement = document.getElementById('impress'); // Oder dein benutzerdefiniertes Root-Element

rootElement.addEventListener('impress:init', function(event) {
    console.log('Ereignis: impress:init');
    console.log('API-Objekt aus Event-Detail:', event.detail.api);
    // Hier kannst du Code ausführen, der nach der Initialisierung laufen soll
});

rootElement.addEventListener('impress:stepenter', function(event) {
    var betretenerStep = event.target; // Das Step-Element, das gerade aktiv wurde
    console.log('Ereignis: impress:stepenter auf Step mit ID:', betretenerStep.id);
    // console.log('Zusatzinfos im Detail:', event.detail); // Untersuche event.detail
});

rootElement.addEventListener('impress:stepleave', function(event) {
    var verlassenerStep = event.target; // Das Step-Element, das gerade verlassen wird
    console.log('Ereignis: impress:stepleave von Step mit ID:', verlassenerStep.id);
    // console.log('Zusatzinfos im Detail:', event.detail);
});
```

**2. Das `event.detail`-Objekt:**

Viele der von `impress.js` ausgelösten Events übergeben zusätzliche, kontextspezifische Informationen in der `event.detail`-Eigenschaft des Event-Objekts. Die genaue Struktur von `event.detail` kann je nach Event variieren. Es ist immer eine gute Idee, `console.log(event.detail)` zu verwenden, um zu sehen, welche Daten verfügbar sind.

**3. Wichtige Core-Events im Detail:**

  * **`impress:init`**:

      * **Ausgelöst**: Einmalig, nachdem `impress().init()` vollständig ausgeführt wurde und die Präsentation initialisiert und bereit ist.
      * **`event.target`**: Das Root-Element der Präsentation (`#impress`).
      * **`event.detail`**: Dieses Objekt enthält typischerweise eine Referenz auf das `impressApi`-Objekt selbst, oft unter `event.detail.api`. Es kann auch andere Initialisierungsdaten enthalten.
      * **Zweck**: Ideal, um eigenen Code auszuführen, der von einer vollständig initialisierten `impress.js`-Umgebung abhängt (z.B. Hinzufügen benutzerdefinierter Navigationssteuerungen, Initialisieren von Plugins, die die API benötigen).

  * **`impress:stepenter`**:

      * **Ausgelöst**: Jedes Mal, wenn ein Step **aktiv wird** (also in den Fokus der Präsentation rückt und vollständig sichtbar ist).
      * **`event.target`**: Das DOM-Element des Steps, der gerade betreten wurde.
      * **`event.detail`**: Kann zusätzliche Informationen enthalten, wie z.B. den Index des Steps oder manchmal eine Referenz auf den vorherigen Step (`previousStep`). Die genauen Inhalte können variieren und sollten geprüft werden.
      * **Zweck**: Dies ist eines der nützlichsten Events. Du kannst es verwenden, um:
          * Animationen *innerhalb* des Steps zu starten.
          * Videos oder Audio-Elemente im Step abzuspielen.
          * Inhalte dynamisch in den Step zu laden.
          * Den Zustand von UI-Elementen (z.B. eine Fortschrittsanzeige) zu aktualisieren.
          * Benutzerdefinierte Aktionen auszulösen, die spezifisch für diesen Step sind.

  * **`impress:stepleave`**:

      * **Ausgelöst**: Jedes Mal, wenn ein Step **verlassen wird** (also nicht mehr der aktive Step ist).
      * **`event.target`**: Das DOM-Element des Steps, der gerade verlassen wurde.
      * **`event.detail`**: Ähnlich wie bei `stepenter`, kann dies kontextbezogene Daten enthalten, z.B. den Index des verlassenen Steps oder eine Referenz auf den nächsten Step (`nextStep`).
      * **Zweck**: Nützlich, um:
          * Animationen *innerhalb* des Steps zurückzusetzen oder zu beenden.
          * Videos oder Audio zu pausieren oder zu stoppen.
          * Ressourcen freizugeben, die nur für diesen Step benötigt wurden.

  * **`impress:steprefresh`**: (Seltener direkt genutzt, aber intern relevant)

      * Wird ausgelöst, wenn die Daten oder die Darstellung eines Steps aktualisiert werden, ohne dass notwendigerweise ein Verlassen oder Betreten stattfindet. Dies kann durch Plugins geschehen, die z.B. relative Positionen dynamisch neu berechnen oder das Layout anpassen.

  * **Events für den Overview-Modus**:

      * Obwohl nicht immer Teil des Cores (manchmal durch Plugins wie das `extras`-Plugin oder ein spezifisches `overview`-Plugin bereitgestellt), sind Events wie `impress:overview:enter` und `impress:overview:leave` extrem nützlich.
      * `impress:overview:enter`: Wird ausgelöst, wenn in den Overview-Modus (via ESC) gewechselt wird.
      * `impress:overview:leave`: Wird ausgelöst, wenn der Overview-Modus verlassen wird.
      * **`event.target`**: Das Root-Element (`#impress`).
      * **Zweck**: Um UI-Elemente anzuzeigen/auszublenden, die nur im Overview-Modus sinnvoll sind, oder um das Styling der Seite anzupassen.

**4. Reihenfolge der Events:**
Wenn du von Step A zu Step B navigierst, ist die typische Reihenfolge:

1.  `impress:stepleave` wird auf dem Element von Step A ausgelöst.
2.  Die Kamerafahrt (CSS-Transition) findet statt.
3.  `impress:stepenter` wird auf dem Element von Step B ausgelöst.

### Beispiele für die dynamische Manipulation der Präsentation zur Laufzeit

Hier sind einige praktische Beispiele, wie du die API und Events nutzen kannst:

**1. Benutzerdefinierte Navigations-Buttons:**
Erstelle eigene HTML-Buttons und verknüpfe sie mit den API-Navigationsmethoden.

HTML:

```html
<button id="customPrev">Vorheriger</button>
<button id="customNext">Nächster</button>
<button id="gotoSpecial">Zu "Spezialthema"</button>
```

JavaScript:

```javascript
// Sicherstellen, dass DOM geladen ist, bevor impress() aufgerufen wird,
// oder das Skript am Ende des Body platzieren.
document.addEventListener('DOMContentLoaded', function() {
    var impressApi = impress();
    impressApi.init(); // Präsentation initialisieren!

    var prevButton = document.getElementById('customPrev');
    var nextButton = document.getElementById('customNext');
    var specialButton = document.getElementById('gotoSpecial');

    if (prevButton) {
        prevButton.addEventListener('click', function() {
            impressApi.prev();
        });
    }
    if (nextButton) {
        nextButton.addEventListener('click', function() {
            impressApi.next();
        });
    }
    if (specialButton) {
        specialButton.addEventListener('click', function() {
            // Angenommen, es gibt einen Step mit der ID "spezial"
            impressApi.goto('spezial'); 
        });
    }
});
```

**2. Inhalt eines Steps beim Betreten dynamisch ändern:**
Aktualisiere den Inhalt eines Steps jedes Mal, wenn er betreten wird.

HTML:

```html
<div id="live-update-step" class="step" data-x="0" data-y="1000">
    <h2>Live Info</h2>
    <p>Aktuelle Uhrzeit: <span class="current-time">wird geladen...</span></p>
    <p>Dieser Step wurde <span class="visit-count">0</span> Mal besucht.</p>
</div>
```

JavaScript:

```javascript
document.addEventListener('DOMContentLoaded', function() {
    var impressApi = impress();
    impressApi.init();

    var liveStep = document.getElementById('live-update-step');
    var visitCounter = 0;

    if (liveStep) {
        liveStep.addEventListener('impress:stepenter', function(event) {
            var now = new Date();
            var timeSpan = event.target.querySelector('.current-time');
            var countSpan = event.target.querySelector('.visit-count');
            
            if (timeSpan) {
                timeSpan.textContent = now.toLocaleTimeString();
            }
            
            visitCounter++;
            if (countSpan) {
                countSpan.textContent = visitCounter;
            }
        });
    }
});
```

**3. Eine einfache Fortschrittsanzeige (vereinfacht):**
Zeige an, beim wievielten Step man sich befindet. (Ein echtes `progress`-Plugin ist hierfür natürlich mächtiger).

HTML:

```html
<div id="presentation-progress" style="position: fixed; bottom: 10px; left: 10px; background: #eee; padding: 5px;">
    Step <span id="current-step-number">0</span> von <span id="total-step-number">0</span>
</div>
```

JavaScript:

```javascript
document.addEventListener('DOMContentLoaded', function() {
    var impressApi = impress();
    var root = document.getElementById('impress'); // impress root
    var currentStepSpan = document.getElementById('current-step-number');
    var totalStepSpan = document.getElementById('total-step-number');
    var allStepsElements = []; // Array der Step DOM Elemente

    // Nach der Initialisierung die Step-Informationen holen
    root.addEventListener('impress:init', function(event) {
        // Die getSteps() Methode ist nicht Teil der öffentlichen API, aber
        // man kann die Steps direkt aus dem DOM lesen.
        allStepsElements = Array.from(root.querySelectorAll('.step'));
        if (totalStepSpan) {
            totalStepSpan.textContent = allStepsElements.length;
        }
    });

    // Bei jedem Betreten eines Steps die Anzeige aktualisieren
    root.addEventListener('impress:stepenter', function(event) {
        var activeStepElement = event.target; // Der Step, der betreten wurde
        var currentIndex = allStepsElements.indexOf(activeStepElement);

        if (currentStepSpan && currentIndex !== -1) {
            currentStepSpan.textContent = currentIndex + 1; // 1-basierte Anzeige
        }
    });

    impressApi.init(); // Am Ende initialisieren
});
```

*Hinweis*: Die genaue Ermittlung des aktuellen Step-Index und der Gesamtanzahl kann variieren. `impress.js` speichert die Steps intern. Eine öffentliche `getSteps()`-Methode oder `getStepCount()` wäre hier nützlich. Falls nicht vorhanden, muss man wie im Beispiel die DOM-Elemente selbst abfragen.

### `impress().tear()` Methode (Aufräumen) – Gibt es sie?

Im Kern von `impress.js` (Versionen um 1.x, 2.x) gibt es **keine** standardmäßig dokumentierte und implementierte öffentliche API-Methode wie `impress().tear()` oder `impress().destroy()` die alle Event-Listener entfernt, Klassen zurücksetzt und den ursprünglichen DOM-Zustand komplett wiederherstellt.

Die Datei `src/lib/gc.js` (Garbage Collection) im Repository enthält zwar eine `deinit()` Funktion, die einige Aufräumarbeiten (Entfernen von Event-Listenern vom `window`) durchführt, aber diese wird intern über einen Mechanismus aufgerufen, der eher für die Plugin-Entwicklung gedacht ist, um spezifische Plugin-Listener zu entfernen.

Für die meisten Anwendungsfälle, bei denen eine `impress.js`-Präsentation eine eigenständige Seite ist, ist ein explizites "Teardown" nicht notwendig. Wenn `impress.js` jedoch in eine komplexe Single-Page-Anwendung (SPA) eingebettet wird und dynamisch entfernt werden soll, müssten Entwickler manuell dafür sorgen, dass:

1.  Alle durch `impress.js` hinzugefügten globalen Event-Listener (z.B. auf `window` für `resize`, `hashchange` oder auf `document` für `keydown`) entfernt werden.
2.  Alle CSS-Klassen vom `body` und `#impress`-Container entfernt werden.
3.  Ggf. Inline-Styles, die `impress.js` gesetzt hat, zurückgesetzt werden.

Dies ist ein fortgeschrittenes Szenario. Für den normalen Gebrauch genügt es, die Seite neu zu laden, um einen "sauberen" Zustand zu erhalten.

Die JavaScript-API und das Event-System von `impress.js` bieten eine enorme Flexibilität. Sie sind der Schlüssel zur Erstellung von Präsentationen, die nicht nur visuell beeindrucken, sondern auch auf Benutzerinteraktionen reagieren und dynamische Inhalte präsentieren können.


## Teil 8: Offizielle Plugins – Teil 1

`impress.js` ist von Haus aus schon sehr leistungsfähig, aber seine wahre Stärke und Flexibilität zeigt sich auch in seiner Erweiterbarkeit durch Plugins. Plugins ermöglichen es, spezifische Funktionalitäten hinzuzufügen oder das Verhalten der Präsentation anzupassen, ohne den Kern von `impress.js` unnötig aufzublähen.

### Einführung in die Plugin-Architektur von `impress.js`

  * **Zweck von Plugins**:

      * **Modularität**: Ermöglichen es, nur die Funktionen zu laden, die tatsächlich benötigt werden.
      * **Erweiterbarkeit**: Erlauben Entwicklern, neue Features beizusteuern, ohne den Core direkt modifizieren zu müssen.
      * **Spezifische Anwendungsfälle**: Bieten Lösungen für häufige Anforderungen wie Autoplay, Notizen, Fortschrittsanzeigen etc.

  * **Wie Plugins konzeptionell funktionieren**:

      * Plugins sind im Grunde JavaScript-Module, die sich in den `impress.js`-Lebenszyklus und dessen API einklinken.
      * **Registrierung**: Ein Plugin "meldet" sich bei `impress.js` an, oft indem es eine Funktion oder ein Objekt bereitstellt, das `impress.js` beim Initialisieren aufruft.
      * **Event-basiert**: Viele Plugins lauschen auf die von `impress.js` ausgelösten Events (siehe Teil 7, z.B. `impress:init`, `impress:stepenter`, `impress:stepleave`) und führen darauf basierend Aktionen aus.
      * **API-Nutzung**: Plugins können die `impress.js`-API (`impress().next()`, `impress().goto()` etc.) verwenden, um die Präsentation zu steuern.
      * **Eigene Elemente**: Sie können neue Datenattribute, CSS-Klassen oder sogar HTML-Elemente einführen, um ihre Funktionalität zu steuern oder darzustellen.
      * **Tastatur-Interaktion**: Plugins können eigene Tastenkürzel definieren und auf Tastatureingaben reagieren.

  * **Integration von Plugins in deine Präsentation**:

      * **Plugin-Quellen**: Die offiziellen Plugins findest du im `src/plugins/`-Verzeichnis des `impress.js`-GitHub-Repositorys. Jedes Plugin befindet sich dort typischerweise in einem eigenen Unterordner mit seiner JavaScript-Datei und oft einer `README.md` mit spezifischen Anweisungen.
      * **Verwendung der gebauten `js/impress.js`**:
          * Die Datei `js/impress.js` (im Hauptverzeichnis des Repositorys oder über gängige CDNs wie jsDelivr verfügbar, z.B. `https://cdn.jsdelivr.net/gh/impress/impress.js@2.0.0/js/impress.js`) ist eine **konkatenierte und oft minifizierte Version**, die den `impress.js`-Core **und alle offiziellen Plugins** aus dem `src/plugins/`-Verzeichnis bereits enthält.
          * **Vorteil**: Wenn du diese Datei verwendest, musst du die Plugin-Skripte nicht einzeln einbinden. Die Funktionalität der meisten Plugins ist dann automatisch verfügbar oder kann einfach aktiviert werden.
          * Für dieses Tutorial gehen wir davon aus, dass du diese gebaute Version nutzt.
      * **Manuelles Einbinden (historisch oder für eigene Builds)**: Wenn du `impress.js` direkt aus `src/impress.js` (dem Core) verwenden würdest, müsstest du jedes gewünschte Plugin als separate `<script>`-Datei *nach* `impress.js` und *vor* dem `impress().init();`-Aufruf einbinden. Dies ist heute seltener der Fall, wenn man Standard-Distributionen nutzt.

  * **Aktivierung und Konfiguration von Plugins**:

      * **Standardaktivität**: Viele Plugins, die in der gebauten `js/impress.js` enthalten sind, sind "passiv" aktiv und reagieren auf bestimmte Bedingungen (z.B. Tastendrücke, das Vorhandensein spezifischer Datenattribute).
      * **Explizite Konfiguration**: Einige Plugins können oder müssen über das Konfigurationsobjekt bei `impress().init()` feiner eingestellt oder explizit aktiviert werden. Dies geschieht oft über ein verschachteltes `plugins`-Objekt:
        ```javascript
        impress().init({
            // ... andere impress.js Optionen ...
            plugins: {
                'plugin-name-A': { /* Optionen für Plugin A */ },
                'plugin-name-B': { /* Optionen für Plugin B */ }
            }
        });
        ```
        Der Schlüssel (`'plugin-name-A'`) ist dabei der offizielle Name des Plugins (oft der Name des Ordners oder der JS-Datei im `src/plugins/`-Verzeichnis).

### Detaillierte Vorstellung ausgewählter offizieller Plugins (Teil 1)

Wir betrachten nun einige häufig genutzte Plugins im Detail.

#### A. `autoplay` Plugin

  * **Zweck/Funktionalität**:
    Das `autoplay`-Plugin ermöglicht das automatische Abspielen deiner Präsentation. Nach einem definierten Zeitintervall wechselt `impress.js` selbstständig zum nächsten Step. Dies ist nützlich für unbeaufsichtigte Präsentationen (z.B. auf Messeständen) oder um einen schnellen Durchlauf zu geben.

  * **Integration/Aktivierung**:

      * Ist in der Standard-`js/impress.js` enthalten.
      * Die einfachste Aktivierung erfolgt durch das Hinzufügen des `data-autoplay`-Attributs zum Hauptcontainer `<div id="impress">`. Der Wert des Attributs gibt das Intervall in **Sekunden** an.
        ```html
        <div id="impress" data-autoplay="7">
            </div>
        ```
        In diesem Beispiel würde die Präsentation alle 7 Sekunden automatisch zum nächsten Step wechseln.

  * **Konfigurationsoptionen (über `impress().init()`)**:
    Du kannst Autoplay auch über das JavaScript-Konfigurationsobjekt steuern und feiner einstellen:

    ```javascript
    impress().init({
        // ...
        plugins: {
            'autoplay': {
                // Intervall in Millisekunden. Dieser Wert überschreibt data-autoplay.
                interval: 5000, // Entspricht 5 Sekunden

                // Richtung des Autoplays.
                // 'forward' (Standard): Geht zum nächsten Step.
                // 'backward': Geht zum vorherigen Step.
                direction: 'forward',

                // (Die Verfügbarkeit weiterer Optionen wie 'progress' sollte in der
                // spezifischen Plugin-Dokumentation geprüft werden, ist aber unüblich.)
            }
        }
    });
    ```

      * `interval`: Definiert das Zeitintervall in Millisekunden, nach dem zum nächsten/vorherigen Step gewechselt wird.
      * `direction`: Bestimmt, ob `impressApi.next()` (`'forward'`) oder `impressApi.prev()` (`'backward'`) aufgerufen wird.

  * **Steuerung und Verhalten**:

      * **Start**: Autoplay beginnt, sobald `impress.js` initialisiert ist und die entsprechende Konfiguration (entweder `data-autoplay` oder JS-Config) vorliegt.
      * **Stopp**: Jegliche manuelle Navigation durch den Benutzer (Tastendruck, Klick zum Navigieren) **stoppt** üblicherweise den Autoplay-Modus. Dies verhindert, dass die automatische Wiedergabe die manuelle Steuerung stört.
      * **API-Steuerung**: Das Plugin fügt dem `impressApi`-Objekt oft Methoden hinzu (Namen können variieren, z.B. `impressApi.autoplay.start()`, `impressApi.autoplay.stop()`), um Autoplay programmatisch zu steuern. Dies muss in der Plugin-Dokumentation oder im Quellcode verifiziert werden.
      * **Ende der Präsentation**: Wenn Autoplay aktiv ist und der letzte Step erreicht wird (bei `direction: 'forward'`), stoppt Autoplay normalerweise. Es gibt kein automatisches Looping zum Anfang, es sei denn, ein anderer Mechanismus (z.B. ein Link vom letzten zum ersten Step) ist implementiert.

  * **Anwendungsbeispiel**:
    HTML:

    ```html
    <div id="impress" data-autoplay="10"> <div class="step" data-x="0" data-y="0"><h1>Step 1</h1></div>
        <div class="step" data-x="1000" data-y="0"><h1>Step 2</h1><p>(wird nach 10s erreicht)</p></div>
        <div class="step" data-x="2000" data-y="0"><h1>Step 3</h1><p>(nochmal 10s später)</p></div>
    </div>

    <script src="https://cdn.jsdelivr.net/gh/impress/impress.js@2.0.0/js/impress.js"></script>
    <script>
        impress().init();
    </script>
    ```

#### B. `blackout` Plugin

  * **Zweck/Funktionalität**:
    Mit dem `blackout`-Plugin kann der Präsentationsbildschirm komplett schwarz (oder optional weiß) geschaltet werden. Dies ist sehr nützlich, um die Aufmerksamkeit des Publikums vorübergehend von den Folien weg und auf den Sprecher zu lenken, z.B. während einer Diskussion oder einer längeren mündlichen Erläuterung.

  * **Integration/Aktivierung**:

      * Standardmäßig in `js/impress.js` enthalten und über Tastenkürzel aktivierbar.

  * **Tastenkürzel**:

      * `.` (Punkt-Taste): Schaltet den Bildschirm schwarz (Blackout). Erneutes Drücken hebt den Blackout-Modus wieder auf.
      * `B` (Taste B): Hat dieselbe Funktion wie die Punkt-Taste.
      * (Einige Versionen oder Konfigurationen könnten auch `W` für "Whiteout" unterstützen, bei dem der Bildschirm weiß wird. Dies ist seltener und muss geprüft werden.)

  * **CSS-Klassen und Styling**:

      * Wenn der Blackout-Modus aktiv ist, fügt das Plugin dem `<body>`-Element die CSS-Klasse `impress-blackout` hinzu.
      * Du musst das eigentliche Aussehen des Blackouts über CSS definieren. Typischerweise:
        ```css
        /* CSS für den Blackout-Effekt */
        body.impress-blackout {
            background-color: black !important; /* Überschreibt andere Hintergründe */
            transition: background-color 0.5s ease-in-out; /* Sanfter Übergang */
        }
        body.impress-blackout #impress { /* Der Hauptcontainer wird ausgeblendet */
            opacity: 0;
            transition: opacity 0.5s ease-in-out; /* Sanftes Ausblenden */
        }
        ```
      * Für einen "Whiteout" (falls unterstützt oder selbst implementiert) wären die Stile analog mit `background-color: white !important;`.

  * **Konfigurationsoptionen (über `impress().init()`)**:
    Das `blackout`-Plugin selbst bietet im Kern von `impress.js` (Stand Versionen um 2.0.0) keine umfangreichen JavaScript-Konfigurationsoptionen direkt über den `plugins`-Block. Das Verhalten wird primär über CSS und die Standard-Tastenkürzel gesteuert. Die Funktionalität ist oft direkt im `impress.js`-Kern oder einem eng verwandten Hilfsplugin verankert.

      * Ältere Versionen oder benutzerdefinierte Builds könnten spezifischere Optionen gehabt haben. Die aktuelle Tendenz ist, solche UI-Aspekte eher durch CSS und DOM-Manipulation (Klassen) zu steuern.

  * **Anwendungsbeispiel**:
    Keine spezielle HTML-Konfiguration ist für die Grundfunktion nötig. Das CSS oben reicht aus. Während der Präsentation einfach `.` oder `B` drücken.

#### C. `bookmarks` Plugin

  * **Zweck/Funktionalität**:
    Das `bookmarks`-Plugin ermöglicht es, bestimmten Steps einen "Lesezeichen-Namen" zu geben. Diese Lesezeichen können dann direkt über den URL-Hash angesprungen werden. Dies ist besonders nützlich, um:

      * Verschiedene "Kapitel" oder Sektionen einer langen, nicht-linearen Präsentation zu definieren.
      * Einfach zu merkende Einstiegspunkte für das Publikum oder für dich selbst zu schaffen.
      * Die URL-Struktur sauberer zu gestalten, falls Step-IDs sehr technisch oder lang sind.

  * **Integration/Aktivierung**:

      * Standardmäßig in `js/impress.js` enthalten und aktiv.

  * **Datenattribut**:

      * `data-bookmark-id="MEIN_LESEZEICHEN_NAME"`: Dieses Attribut wird einem `.step`-Element hinzugefügt.
      * Der `MEIN_LESEZEICHEN_NAME` sollte ein gültiger URL-Fragment-Identifier sein (keine Leerzeichen, spezielle URL-Zeichen vermeiden oder kodieren).

  * **Funktionsweise im Detail**:

    1.  Du definierst einen Step mit einem Lesezeichen:
        ```html
        <div id="actual-step-id-fuer-thema1" class="step" data-bookmark-id="kapitelEins">
            Inhalt von Kapitel 1...
        </div>
        ```
    2.  Um direkt zu diesem Lesezeichen zu springen, verwendest du folgenden URL-Hash:
        `deine-praesentation.html#kapitelEins` (Beachte: `#` ohne `/` davor, im Gegensatz zu direkten Step-ID-Hashes wie `#/actual-step-id-fuer-thema1`).
    3.  Wenn `impress.js` mit einem solchen Hash im URL geladen wird (z.B. `#kapitelEins`), sucht das `bookmarks`-Plugin nach einem Step mit `data-bookmark-id="kapitelEins"` und navigiert zu diesem Step.
    4.  **Wichtig**: Der URL-Hash für Bookmarks wird *ohne* den Schrägstrich (`/`) verwendet, der typischerweise für die Navigation zu Step-IDs benutzt wird. `impress.js` unterscheidet zwischen `#/stepId` (geht zu Step mit `id="stepId"`) und `#bookmarkName` (geht zu Step mit `data-bookmark-id="bookmarkName"`).

  * **Unterschied zu normalen Step-IDs in der URL**:

      * `#/meine-step-id`: Navigiert zum Element mit `id="meine-step-id"`. Die URL wird beim Navigieren auch so aktualisiert.
      * `#mein-bookmark`: Navigiert zum Element mit `data-bookmark-id="mein-bookmark"`. Beim Erreichen dieses Steps wird die URL typischerweise auf den Hash des Bookmarks (`#mein-bookmark`) aktualisiert, nicht notwendigerweise auf die ID des Steps selbst. Dies sorgt für konsistente Bookmark-URLs.

  * **Konfigurationsoptionen**:
    Das `bookmarks`-Plugin hat in der Regel keine spezifischen JavaScript-Konfigurationsoptionen. Seine Funktionalität wird vollständig über das `data-bookmark-id`-Attribut gesteuert.

  * **Anwendungsbeispiel**:
    HTML:

    ```html
    <div id="impress">
        <div id="s1" class="step" data-x="0" data-y="0" data-bookmark-id="start">
            <h1>Willkommen</h1>
            <p>Dies ist der Startpunkt.</p>
        </div>
        <div id="s2-details" class="step" data-x="1000" data-y="0" data-bookmark-id="feature-x">
            <h2>Feature X</h2>
            <p>Details zu Feature X...</p>
        </div>
        <div id="s3" class="step" data-x="2000" data-y="0">
            <p>Ein normaler Zwischenschritt ohne Bookmark.</p>
        </div>
        <div id="s4-summary" class="step" data-x="3000" data-y="0" data-bookmark-id="abschluss">
            <h2>Abschluss</h2>
            <p>Zusammenfassung der Präsentation.</p>
        </div>
    </div>
    <script src="https://cdn.jsdelivr.net/gh/impress/impress.js@2.0.0/js/impress.js"></script>
    <script>impress().init();</script>
    ```

    Du könntest diese Steps nun über folgende URLs direkt ansteuern:

      * `deine_datei.html#start`
      * `deine_datei.html#feature-x`
      * `deine_datei.html#abschluss`

#### D. `extras` Plugin (und verwandte Funktionen wie `skip`, `substep`)

Das `extras`-Plugin ist oft ein Sammelbegriff oder eine Basis für verschiedene nützliche Zusatzfunktionen, die über Tastenkürzel oder spezielle Klassen gesteuert werden. Die genaue Implementierung, welche Funktionen unter "extras" gebündelt sind und welche als eigenständige kleine Plugins existieren, kann sich zwischen `impress.js`-Versionen oder Forks leicht unterscheiden. In der Regel sind die Kernfunktionalitäten jedoch in der Standarddistribution (`js/impress.js`) enthalten.

**1. `skip` Funktionalität (Steps überspringen):**

  * **Zweck**: Ermöglicht es, bestimmte Steps bei der linearen Vorwärts-/Rückwärtsnavigation (Leertaste, Pfeiltasten) zu überspringen. Diese übersprungenen Steps bleiben jedoch über direkte Navigation (URL-Hash, `goto()`-API, Klick im Overview-Modus) erreichbar. Nützlich für optionale Details, Backup-Folien oder um alternative Pfade zu ermöglichen.
  * **Integration/Aktivierung**:
      * Meist standardmäßig aktiv, wenn `js/impress.js` verwendet wird.
  * **CSS-Klasse**:
      * Füge die Klasse `skip` zu dem `.step`-Element hinzu, das übersprungen werden soll:
        ```html
        <div id="step-A" class="step" data-x="0" data-y="0">Step A</div>
        <div id="step-B-optional" class="step skip" data-x="1000" data-y="0">Optionaler Step B (wird übersprungen)</div>
        <div id="step-C" class="step" data-x="2000" data-y="0">Step C</div>
        ```
        Wenn du von Step A mit der Leertaste weitergehst, landest du direkt bei Step C.
  * **Konfigurationsoptionen**: Typischerweise keine spezifischen JS-Optionen für die `skip`-Funktion selbst.

**2. `substep` Funktionalität (Unter-Schritte innerhalb eines Steps):**

  * **Zweck**: Ermöglicht es, Elemente *innerhalb* eines einzelnen `impress.js`-Steps nacheinander erscheinen zu lassen oder andere inkrementelle Animationen durchzuführen, bevor zum nächsten Haupt-Step gewechselt wird. Jeder "Weiter"-Befehl deckt dann den nächsten Substep auf.
  * **Integration/Aktivierung**:
      * Standardmäßig in `js/impress.js` enthalten und aktiv.
  * **CSS-Klasse**:
      * Elemente innerhalb eines `.step`-Containers, die als Substeps agieren sollen, erhalten die Klasse `substep`.
        ```html
        <div id="main-points" class="step" data-x="0" data-y="0">
            <h2>Meine Hauptpunkte</h2>
            <ul>
                <li class="substep">Erster wichtiger Punkt</li>
                <li class="substep">Zweiter wichtiger Punkt</li>
                <li class="substep">Dritter wichtiger Punkt, der nach dem zweiten erscheint</li>
            </ul>
            <p class="substep">Ein abschließender Gedanke zu diesen Punkten.</p>
        </div>
        ```
  * **Verhalten im Detail**:
    1.  Wenn der Haupt-Step (`#main-points`) betreten wird, sind initial alle Elemente mit `class="substep"` unsichtbar oder in einem "Startzustand" (gesteuert durch CSS).
    2.  Der erste "Weiter"-Befehl (Leertaste, Pfeil rechts etc.) macht das erste `.substep`-Element sichtbar und fügt ihm die Klasse `substep-visible` (oder `substep-active` / `present` je nach genauer Implementierung) hinzu.
    3.  Jeder weitere "Weiter"-Befehl macht das nächste `.substep`-Element sichtbar und aktualisiert die Klassen.
    4.  Wenn alle `.substep`-Elemente innerhalb des aktuellen Haupt-Steps sichtbar gemacht wurden, führt der nächste "Weiter"-Befehl zum nächsten `impress.js`-Haupt-Step.
    5.  Die Rückwärtsnavigation (Shift+Leertaste etc.) kehrt diesen Prozess um und blendet die Substeps wieder aus.
  * **Zugehörige CSS-Klassen (werden vom Plugin dynamisch gesetzt)**:
      * `.substep-active` (oder `.active-substep`, `.present`): Wird dem aktuell sichtbaren/fokussierten Substep hinzugefügt.
      * `.substep-visible` (oder `.past` für Substeps): Wird Substeps hinzugefügt, die bereits aufgedeckt wurden.
      * Du musst CSS-Regeln definieren, um diese Klassen zu nutzen und die Substeps entsprechend ein- oder auszublenden oder zu animieren:
        ```css
        .substep {
            opacity: 0; /* Standardmäßig unsichtbar */
            transition: opacity 0.5s ease-in-out;
        }
        .substep.substep-visible, /* Ältere Konvention */
        .substep.present,        /* Neuere/alternative Konvention für sichtbare, aber nicht aktive */
        .substep.active,         /* Neuere/alternative Konvention für den gerade aktiven */
        .substep.substep-active { /* Kombinierte Konvention, sehr wahrscheinlich */
            opacity: 1;
        }

        /* Optional: Den gerade aktivierten Substep hervorheben */
        .substep.substep-active {
            /* z.B. font-weight: bold; color: blue; */
        }
        ```
        Es ist wichtig, die genauen Klassen, die deine `impress.js`-Version für Substeps verwendet, durch Inspektion im Browser oder Blick in die Plugin-Quelle zu verifizieren. Oft ist es `.substep-active` für den aktuellen und `.substep-visible` für alle bereits gezeigten.
  * **Konfigurationsoptionen**:
    In der `impress().init()`-Konfiguration unter `plugins: { 'substep': { ... } }` könnten Optionen existieren:
      * `activeStyle`: Ein Objekt mit CSS-Eigenschaften, das auf den `.substep-active` angewendet wird (obwohl dies meist besser direkt in CSS gehandhabt wird).
      * `  порядок ` (order): (selten) Beeinflusst die Reihenfolge der Substeps, falls nicht durch DOM-Reihenfolge.

**3. `goto`-Tastenkürzel (oft Teil von `extras` oder einem `goto`-Plugin)**:

  * **Zweck**: Ermöglicht schnelles Springen zu einem Step über dessen Nummer (Index) oder ID.
  * **Tastenkürzel**: Typischerweise `G`.
  * **Funktionsweise**:
    1.  Drücken von `G` öffnet ein JavaScript `prompt()`-Fenster.
    2.  Der Benutzer gibt die 0-basierte Nummer des Ziel-Steps oder die ID des Ziel-Steps ein.
    3.  `impress.js` versucht dann, mit `impressApi.goto()` zu diesem Step zu navigieren.
  * **Konfiguration**: Manchmal kann das Verhalten (z.B. ob nach ID oder Index gefragt wird) konfiguriert werden.

**4. `help`-Tastenkürzel (oft Teil von `extras` oder einem `help`-Plugin)**:

  * **Zweck**: Zeigt eine Hilfe-Übersicht oder ein Pop-up mit den verfügbaren Tastenkürzeln an.
  * **Tastenkürzel**: Typischerweise `H` oder `?` (Shift + `/`).
  * **Funktionsweise**: Das Plugin generiert oft dynamisch ein HTML-Overlay, das die Tastenkürzel auflistet, die vom Core und den aktiven Plugins unterstützt werden. Das Aussehen dieses Overlays wird per CSS gesteuert.
  * **Konfiguration**: Kann Optionen für den Inhalt oder das Aussehen des Hilfe-Dialogs haben.

**Zusammenfassend zu `extras`**: Da "extras" ein Sammelbegriff sein kann, ist es immer ratsam, die `src/plugins/extras/extras.js` Datei und die dazugehörige `README.md` (falls vorhanden) zu konsultieren, um genau zu verstehen, welche Funktionen in deiner `impress.js`-Version enthalten sind und wie sie konfiguriert werden. Die hier beschriebenen Funktionen `skip` und `substep` sind jedoch sehr verbreitete und mächtige Werkzeuge.


## Teil 9: Offizielle Plugins – Teil 2

Nachdem wir in Teil 8 bereits einige grundlegende Plugins kennengelernt haben, widmen wir uns nun weiteren offiziellen Erweiterungen, die `impress.js` um nützliche Navigationshilfen, Layout-Optionen und Darstellungsmodi ergänzen. Denke daran, dass bei Verwendung der Standard-Distribution `js/impress.js` (oft über CDN bezogen) diese Plugins bereits enthalten und meist ohne weiteres Zutun aktiv sind oder einfach konfiguriert werden können.

### Detaillierte Vorstellung ausgewählter offizieller Plugins (Fortsetzung)

#### A. `navigation` (Logik) und `navigation-ui` (Oberfläche) Plugins

Diese beiden Plugins arbeiten oft eng zusammen, um eine sichtbare Navigationssteuerung für deine Präsentation bereitzustellen.

  * **`navigation` Plugin (`src/plugins/navigation/`)**

      * **Zweck/Funktionalität**: Dieses Plugin erweitert die Kern-Navigationslogik von `impress.js`. Seine Hauptaufgabe ist es, die `goto()`-Funktion der API so zu erweitern, dass sie relative Keywords und numerische Sprünge versteht. Es ermöglicht auch eine komplexere Steuerung des "nächsten" und "vorherigen" Steps über spezielle Datenattribute.
      * **API-Erweiterungen (für `impressApi.goto()`):**
          * `"next"`: Springt zum nächsten Step (äquivalent zu `impressApi.next()`).
          * `"prev"`: Springt zum vorherigen Step (äquivalent zu `impressApi.prev()`).
          * `"first"`: Springt zum allerersten Step im DOM (Index 0).
          * `"last"`: Springt zum allerletzten Step im DOM.
          * `"+N"` (z.B. `"+1"`, `"+5"`): Springt N Steps vorwärts relativ zum aktuellen Step.
          * `"-N"` (z.B. `"-1"`, `"-3"`): Springt N Steps rückwärts relativ zum aktuellen Step.
      * **Datenattribute für benutzerdefinierte Pfade**:
          * `data-goto-next="ziel-step-id"`: Definiert, welcher Step als nächstes angesteuert wird, wenn von diesem Step aus "vorwärts" navigiert wird (überschreibt die DOM-Reihenfolge).
          * `data-goto-prev="ziel-step-id"`: Definiert den vorherigen Step.
          * `data-goto-first`, `data-goto-last`: (seltener, aber möglich)
          * `data-goto-relative-next-id`, `data-goto-relative-prev-id`: (fortgeschritten) Erlaubt das Referenzieren von Steps basierend auf deren relativer Position zu einem anderen Referenz-Step.
      * **Integration/Aktivierung**: In `js/impress.js` enthalten und standardmäßig aktiv. Die API-Erweiterungen sind sofort nutzbar. Die Datenattribute werden automatisch berücksichtigt.
      * **Konfigurationsoptionen**: Typischerweise keine direkten Konfigurationen für das reine `navigation`-Logik-Plugin.

  * **`navigation-ui` Plugin (`src/plugins/navigation-ui/`)**

      * **Zweck/Funktionalität**: Dieses Plugin ist dafür zuständig, sichtbare UI-Elemente (typischerweise Pfeil-Buttons) auf dem Bildschirm zu erzeugen, mit denen der Benutzer durch die Präsentation navigieren kann. Es nutzt intern die Logik des `navigation`-Plugins (bzw. die Core-API).
      * **HTML-Struktur**: Das Plugin fügt dem `#impress`-Container oder dem `<body>` dynamisch HTML-Elemente für die Navigationspfeile hinzu. Dies sind oft `<div>`-Elemente mit spezifischen IDs oder Klassen.
          * Beispielhafte generierte Struktur (kann variieren):
            ```html
            <div id="impress-navigation-ui">
                <div id="impress-navigation-ui-prev" class="impress-arrow"></div>
                <div id="impress-navigation-ui-next" class="impress-arrow"></div>
                </div>
            ```
      * **CSS-Styling**: Das Aussehen (Form, Farbe, Position, Sichtbarkeit) dieser Buttons wird vollständig über CSS gesteuert. Das Plugin selbst oder `impress-common.css` liefert oft Basis-Stile.
          * Wichtige CSS-Klassen könnten sein: `impress-navigation-ui` (für den Container), `impress-arrow`, `impress-arrow-prev`, `impress-arrow-next`, `impress-arrow-up`, `impress-arrow-down`.
          * Die Buttons werden oft am Rand des Bildschirms positioniert und können bei Inaktivität (siehe `mouse-timeout`-Plugin) ausgeblendet werden.
      * **Integration/Aktivierung**: In `js/impress.js` enthalten. Ob es standardmäßig aktiv ist oder via Konfiguration aktiviert werden muss, hängt von der `impress.js`-Version ab. Oft ist es standardmäßig aktiv.
      * **Konfigurationsoptionen (via `impress().init({ plugins: { 'navigation-ui': { ... } } })`)**:
          * `showNextPrev` (boolean): Ob die Vorwärts- und Rückwärts-Pfeile angezeigt werden. *Default*: `true`.
          * `showProgressBar` (boolean): (Manchmal hier, manchmal im `progress`-Plugin) Ob eine Fortschrittsanzeige als Teil der UI dargestellt wird. *Default*: `true` (in einigen Konfigurationen).
          * `showStepNumbers` (boolean): Ob Seitenzahlen angezeigt werden. *Default*: `true` (in einigen Konfigurationen).
          * (Weitere Optionen könnten spezifische Klassen oder das Verhalten der UI betreffen.)
      * **Anwendungsbeispiel (CSS-Anpassung)**:
        ```css
        /* Beispiel: Pfeile größer und rot machen */
        #impress-navigation-ui .impress-arrow {
            width: 50px;
            height: 50px;
            background-color: rgba(200, 0, 0, 0.7);
            border-radius: 25px;
        }
        #impress-navigation-ui-prev {
            left: 20px; /* Position anpassen */
            bottom: 20px;
        }
        #impress-navigation-ui-next {
            right: 20px; /* Position anpassen */
            bottom: 20px;
        }
        /* Icons für Pfeile werden oft über :before/:after Pseudo-Elemente und content oder SVGs realisiert */
        ```

#### B. `progress` Plugin (`src/plugins/progress/`)

  * **Zweck/Funktionalität**: Zeigt eine visuelle Fortschrittsanzeige an, die dem Benutzer (und dem Präsentierenden) einen Überblick gibt, an welcher Stelle der Präsentation er sich befindet (z.B. "Step 5 von 12").
  * **HTML-Struktur**: Das Plugin erstellt dynamisch ein `<div>`-Element, typischerweise mit der Klasse `impress-progressbar` (für den Balken) und manchmal ein separates Element für die Textanzeige (z.B. mit Klasse `impress-progress`). Diese Elemente werden oft am oberen oder unteren Bildschirmrand positioniert.
    ```html
    <div class="impress-progressbar"><div></div></div> <div class="impress-progress">5/12</div>
    ```
  * **CSS-Styling**: Das Aussehen, die Position und die Animation der Fortschrittsanzeige werden vollständig über CSS gesteuert.
    ```css
    .impress-progressbar {
        position: fixed;
        left: 0;
        bottom: 0; /* Oder top: 0; */
        width: 100%;
        height: 10px;
        background-color: rgba(0, 0, 0, 0.1);
    }
    .impress-progressbar div { /* Der eigentliche Fortschrittsbalken */
        width: 0%; /* Wird per JS aktualisiert */
        height: 100%;
        background-color: rgba(0, 120, 255, 0.7);
        transition: width 0.5s ease-out; /* Sanfter Übergang bei Fortschritt */
    }
    .impress-progress { /* Textanzeige */
        position: fixed;
        left: 10px;
        bottom: 12px; /* Knapp über dem Balken */
        font-size: 12px;
        color: #333;
    }
    ```
  * **Funktionsweise im Detail**:
    1.  Bei `impress:init` ermittelt das Plugin die Gesamtanzahl der Steps.
    2.  Bei jedem `impress:stepenter`-Event ermittelt es den Index des aktuellen Steps.
    3.  Es berechnet den prozentualen Fortschritt: `(aktueller_Index + 1) / gesamt_Anzahl * 100`.
    4.  Es aktualisiert die `width` des inneren `div`s der Fortschrittsleiste auf diesen Prozentwert.
    5.  Wenn die Textanzeige aktiviert ist, aktualisiert es auch diese (z.B. "3/10").
  * **Integration/Aktivierung**: In `js/impress.js` enthalten. Typischerweise standardmäßig aktiv, wenn das HTML/CSS dafür vorhanden ist oder durch das `navigation-ui` oder `toolbar` Plugin mit eingebunden wird.
  * **Konfigurationsoptionen (via `impress().init({ plugins: { 'progress': { ... } } })`)**:
      * Die Optionen sind oft eng mit denen des `navigation-ui` oder `toolbar` Plugins verknüpft, falls diese die Anzeige übernehmen. Ein eigenständiges `progress`-Plugin könnte eigene Schalter haben, z.B.:
          * `show`: (boolean) Ob die Fortschrittsanzeige überhaupt aktiv ist.

#### C. `rel` Plugin (`src/plugins/rel/`)

  * **Zweck/Funktionalität**: Revolutioniert die Art und Weise, wie komplexe Layouts erstellt werden, indem es die **relative Positionierung, Rotation und Skalierung** von Steps zueinander ermöglicht. Anstatt jeden Step mit absoluten Koordinaten zum globalen Ursprung (0,0,0) zu definieren, kannst du einen Step relativ zur *Endposition und -ausrichtung des vorherigen Steps* platzieren.

  * **Datenattribute**: Das `rel`-Plugin führt eine Reihe von `data-rel-*`-Attributen ein:

      * `data-rel-x`, `data-rel-y`, `data-rel-z`: Numerische Werte (Pixel), die angeben, um wie viel der aktuelle Step von der *finalen Position des vorherigen Steps* verschoben werden soll.
      * `data-rel-rotate-x`, `data-rel-rotate-y`, `data-rel-rotate-z`: Numerische Werte (Grad), die eine *zusätzliche* Rotation relativ zur *finalen Ausrichtung des vorherigen Steps* angeben.
      * `data-rel-rotate`: Alias für `data-rel-rotate-z`.
      * `data-rel-scale`: Ein numerischer Faktor, der eine *zusätzliche* Skalierung relativ zur *finalen Skalierung des vorherigen Steps* angibt (d.h. wenn der vorherige Step `data-scale="2"` hatte und der aktuelle `data-rel-scale="1.5"`, wird der aktuelle Step effektiv mit `2 * 1.5 = 3` skaliert).

  * **Funktionsweise im Detail ("Kettenreaktion" der Transformationen)**:

    1.  Der erste Step in einer Kette von relativ positionierten Steps benötigt in der Regel absolute Startwerte (`data-x`, `data-y`, `data-z` etc.) oder wird standardmäßig bei (0,0,0) mit Rotation 0 und Skalierung 1 platziert.
    2.  Für jeden nachfolgenden Step mit `data-rel-*`-Attributen:
          * `impress.js` (mit dem `rel`-Plugin) nimmt die berechneten **absoluten** Transformationswerte (Position, Rotation, Skalierung) des *direkt im DOM vorhergehenden Steps*.
          * Die Werte aus den `data-rel-*`-Attributen des aktuellen Steps werden zu diesen absoluten Werten des Vorgängers addiert (für Positionen und Rotationen) oder mit ihnen multipliziert (für Skalierungen), um die neuen absoluten Transformationswerte für den aktuellen Step zu berechnen.
          * Beispiel:
              * Step A: `data-x="100" data-y="0" data-rotate-z="10" data-scale="1"`
              * Step B: `data-rel-x="500" data-rel-rotate-z="15" data-rel-scale="2"`
              * Berechnete absolute Werte für Step B:
                  * `x = 100 (von A) + 500 (rel) = 600`
                  * `y = 0 (von A) + 0 (rel, da nicht angegeben) = 0`
                  * `z = 0 (von A) + 0 (rel) = 0`
                  * `rotate-z = 10 (von A) + 15 (rel) = 25`
                  * `scale = 1 (von A) * 2 (rel) = 2`

    <!-- end list -->

      * **Wichtig**: Die relativen Attribute beziehen sich auf den **im DOM vorhergehenden Step**, nicht notwendigerweise auf den in der Navigationssequenz vorherigen Step (falls diese z.B. durch `data-goto-next` verändert wurde).
      * **Kombination mit absoluten Werten**: Du kannst `data-rel-*` Attribute auch mit absoluten `data-*` Attributen am selben Step mischen. Die `data-rel-*` Werte werden dann auf die absoluten Werte des *aktuellen* Steps addiert/multipliziert, *nachdem* diese bereits als Basis genommen wurden (die genaue Logik kann hier komplex werden und sollte durch Experimentieren verifiziert werden; typischer ist, dass `data-rel-*` sich auf den *Vorgänger* bezieht und die absoluten Attribute des aktuellen Steps als Basis dienen, wenn kein Vorgänger `data-rel` beeinflusst hat). Die primäre und klarste Nutzung ist, dass `data-rel-*` sich auf den Vorgänger bezieht und die absoluten Attribute des aktuellen Steps dann weggelassen werden oder als Basis für diese relative Anpassung dienen. In der Regel werden die `data-rel-*` Attribute auf die transformierten Werte des Vorgängers angewendet.

  * **Integration/Aktivierung**: In `js/impress.js` enthalten und standardmäßig aktiv.

  * **Konfigurationsoptionen**: Normalerweise keine, die Funktionalität wird vollständig durch die Datenattribute gesteuert.

  * **Anwendungsbeispiel**: Erstellen einer einfachen Spirale oder einer Kette von Folien, die sich jeweils leicht verschieben und drehen.

    ```html
    <div id="impress">
        <div class="step" data-x="0" data-y="0" data-rotate-z="0" data-scale="3">Basis Step</div>
        <div class="step" data-rel-x="800" data-rel-y="200" data-rel-rotate-z="30" data-rel-scale="0.8">Step 2 (relativ zu Basis)</div>
        <div class="step" data-rel-x="700" data-rel-y="150" data-rel-rotate-z="30" data-rel-scale="0.8">Step 3 (relativ zu Step 2)</div>
        <div class="step" data-rel-x="600" data-rel-y="100" data-rel-rotate-z="30" data-rel-scale="0.8">Step 4 (relativ zu Step 3)</div>
    </div>
    <script>impress().init();</script>
    ```

    Jeder nachfolgende Step ist kleiner, weiter rechts oben und weiter gedreht als sein Vorgänger.

#### D. `resize` Plugin (`src/plugins/resize/`)

  * **Zweck/Funktionalität**: Dieses Plugin sorgt dafür, dass sich die gesamte `impress.js`-Präsentation an Änderungen der Browserfenstergröße anpasst. Es skaliert die "Leinwand" so, dass das ursprüngliche Seitenverhältnis der Präsentation (definiert durch `width` und `height` in der `init`-Konfiguration) so gut wie möglich beibehalten wird und die Inhalte sichtbar bleiben.
  * **Funktionsweise im Detail**:
    1.  Das Plugin speichert die initialen Dimensionen (`width`, `height`), die bei `impress().init()` konfiguriert wurden.
    2.  Es lauscht auf das `resize`-Event des `window`-Objekts.
    3.  Wenn das Fenster neu dimensioniert wird, berechnet es einen globalen Skalierungsfaktor. Dieser Faktor wird so gewählt, dass die Präsentation (basierend auf ihren konfigurierten `width`/`height`-Werten) in die neue Fenstergröße passt, wobei das Seitenverhältnis erhalten bleibt.
    4.  Dieser Skalierungsfaktor wird dann als CSS `transform: scale(FAKTOR)` auf den `#impress`-Container (oder dessen internes Canvas-Element) angewendet. Dies skaliert die gesamte Präsentationsansicht.
  * **Integration/Aktivierung**: In `js/impress.js` enthalten und standardmäßig aktiv.
  * **Konfigurationsoptionen (via `impress().init({ plugins: { 'resize': { ... } } })`)**:
      * Normalerweise sind keine expliziten Konfigurationen notwendig, da es "einfach funktioniert". Es könnte interne, nicht öffentlich dokumentierte Parameter geben, aber die Standardeinstellung ist meistens gewünscht.
  * **Wichtigkeit**: Sehr wichtig für Präsentationen, die auf unterschiedlichen Bildschirmgrößen oder Projektoren mit variierenden Auflösungen gezeigt werden sollen. Ohne dieses Plugin könnten Teile der Präsentation abgeschnitten sein oder die Proportionen verzerrt wirken.

#### E. `stop` Plugin (`src/plugins/stop/`)

  * **Zweck/Funktionalität**: Ermöglicht es, einen bestimmten Step als "Endpunkt" der normalen Vorwärtsnavigation zu definieren. Wenn dieser Step erreicht wird, führen weitere "Nächster Step"-Befehle (z.B. Leertaste) nicht mehr zum nächsten Step in der DOM-Reihenfolge.
  * **CSS-Klasse**:
      * Füge die Klasse `stop` zu dem `.step`-Element hinzu, das die Präsentation (vorläufig) beenden soll:
        ```html
        <div id="letzter-haupt-step" class="step stop" data-x="5000" data-y="0">
            <h2>Vielen Dank!</h2>
            <p>Ende des Hauptteils.</p>
        </div>
        <div id="appendix-1" class="step" data-x="6000" data-y="0"> <h3>Anhang A</h3>
        </div>
        ```
  * **Funktionsweise**:
      * Wenn ein Step mit der Klasse `stop` aktiv wird, modifiziert das Plugin das Verhalten von `impressApi.next()` (und verwandten Funktionen), sodass es `false` zurückgibt oder keine Aktion ausführt.
      * Die Rückwärtsnavigation (`impressApi.prev()`) funktioniert in der Regel weiterhin.
      * Steps, die nach dem `stop`-Step im DOM folgen, sind weiterhin über direkte Navigation (ID-Hash, `goto()`-API, Overview-Modus) erreichbar.
  * **Nützlich für**:
      * Ein klares, definiertes Ende des Hauptpräsentationsflusses.
      * "Bonusfolien" oder einen Anhang, der nur bei Bedarf gezeigt wird.
      * Interaktive Präsentationen, bei denen der Benutzer an einem bestimmten Punkt eine Auswahl treffen soll, bevor es weitergeht.
  * **Konfigurationsoptionen**: Normalerweise keine. Die Funktionalität wird durch die `stop`-Klasse gesteuert.

#### F. `toolbar` Plugin (`src/plugins/toolbar/`)

  * **Zweck/Funktionalität**: Fügt eine sichtbare Werkzeugleiste (Toolbar) zur Präsentation hinzu. Diese Toolbar enthält typischerweise verschiedene Steuerelemente für die Navigation und andere Präsentationsfunktionen. Sie ist oft eine Alternative oder Ergänzung zum `navigation-ui`-Plugin.
  * **HTML-Struktur und Inhalt**:
      * Das Plugin generiert dynamisch das HTML für die Toolbar (oft ein `<div>` mit der ID `impress-toolbar`) und fügt es dem DOM (meist direkt in den `<body>`) hinzu.
      * Die Toolbar kann verschiedene Elemente enthalten, z.B.:
          * Navigationspfeile (Vor, Zurück).
          * Eine Fortschrittsanzeige (Balken und/oder Text).
          * Ein Dropdown-Menü oder eine Button-Leiste, um direkt zu bestimmten Steps (oft per ID oder Titel) zu springen (nutzt `goto()`).
          * Einen Button zum Aktivieren des Overview-Modus.
          * Einen Hilfe-Button (der das `help`-Plugin oder eine ähnliche Funktion aufruft).
          * Einen Button für Autoplay Start/Stop.
  * **CSS-Styling**: Das Aussehen der Toolbar ist vollständig über CSS anpassbar. Das Plugin liefert meist Standardstile.
      * CSS-Klassen könnten sein: `impress-toolbar`, `impress-toolbar-button`, `impress-toolbar-progress`, `impress-toolbar-menu`.
  * **Integration/Aktivierung**: In `js/impress.js` enthalten. Muss oft explizit über die Konfiguration aktiviert und konfiguriert werden, welche Elemente es enthalten soll.
  * **Konfigurationsoptionen (via `impress().init({ plugins: { 'toolbar': { ... } } })`)**:
      * `bar`: (boolean oder array) Legt fest, welche Steuerelemente in der Toolbar angezeigt werden. Ein Array von Strings könnte die Namen der Elemente enthalten, z.B. `['prev', 'next', 'title', 'progress', 'menu']`.
      * `style`: (string) Vordefinierte Stile für die Toolbar (z.B. `'default'`, `'dark'`).
      * (Weitere Optionen könnten die Position oder das Verhalten spezifischer Toolbar-Elemente steuern.)
  * **Abhängigkeiten**: Die Toolbar nutzt oft Funktionen anderer Plugins (z.B. `progress` für die Fortschrittsanzeige, `goto` für das Sprungmenü).
  * **Anwendungsbeispiel**:
    JavaScript zur Aktivierung einer Toolbar mit spezifischen Elementen:
    ```javascript
    impress().init({
        // ...
        plugins: {
            'toolbar': {
                // Definiert die Elemente und ihre Reihenfolge in der Toolbar
                // Die genauen Namen der Elemente ('prev', 'next', 'title', etc.)
                // müssen der Plugin-Implementierung entnommen werden.
                bar: [ "prev", "next", "title", "progress", "menu" ],
                // Möglicherweise weitere Optionen für das Aussehen oder Verhalten
            }
        }
    });
    ```
    Das Plugin würde dann das HTML generieren und man könnte es mit CSS wie folgt anpassen:
    ```css
    #impress-toolbar {
        position: fixed;
        bottom: 0;
        left: 0;
        width: 100%;
        background-color: rgba(0, 0, 0, 0.7);
        padding: 10px;
        display: flex; /* Für die Anordnung der Elemente */
        justify-content: space-around;
        color: white;
    }
    #impress-toolbar button, #impress-toolbar .impress-toolbar-element {
        background: none;
        border: 1px solid white;
        color: white;
        padding: 5px 10px;
        cursor: pointer;
    }
    /* ... weiteres spezifisches Styling ... */
    ```

#### G. `touch` Plugin (`src/plugins/touch/`)

  * **Zweck/Funktionalität**: Ermöglicht die Steuerung der `impress.js`-Präsentation durch Touch-Gesten auf Geräten mit Touchscreen (Smartphones, Tablets).
  * **Funktionsweise im Detail**:
    1.  Das Plugin lauscht auf Standard-Touch-Events:
          * `touchstart`: Wenn ein Finger den Bildschirm berührt.
          * `touchmove`: Wenn sich ein Finger über den Bildschirm bewegt.
          * `touchend`: Wenn ein Finger vom Bildschirm gehoben wird.
    2.  **Swipe-Gesten**: Es analysiert die Bewegung zwischen `touchstart` und `touchend`.
          * Ein horizontaler Swipe nach links (Finger bewegt sich von rechts nach links) wird als Befehl für `impressApi.next()` interpretiert.
          * Ein horizontaler Swipe nach rechts (Finger bewegt sich von links nach rechts) wird als Befehl für `impressApi.prev()` interpretiert.
    3.  **Pinch-to-Zoom (für Overview)**: Einige Implementierungen des Touch-Plugins (oder in Kombination mit anderen mobilen Plugins) könnten eine Pinch-Geste (zwei Finger zusammenziehen) erkennen, um in den Overview-Modus zu wechseln, und eine "Reverse Pinch"-Geste (zwei Finger auseinanderziehen), um ihn wieder zu verlassen. Dies ist eine fortgeschrittenere Funktion und nicht immer Standard.
    4.  **Tap-Navigation**: Ein einfacher Tap auf den Bildschirm könnte ebenfalls als `impressApi.next()` interpretiert werden, ähnlich dem Mausklick.
  * **Integration/Aktivierung**: In `js/impress.js` enthalten und funktioniert in der Regel automatisch auf Geräten, die Touch-Events unterstützen. Es sind keine speziellen HTML-Attribute oder CSS-Klassen für die Grundfunktion nötig.
  * **Konfigurationsoptionen (via `impress().init({ plugins: { 'touch': { ... } } })`)**:
      * `swipeThreshold` (number): Die Mindestdistanz in Pixeln, die ein Finger horizontal bewegt werden muss, damit die Geste als Swipe erkannt wird. *Default*: oft um die `50` (Pixel). Ein kleinerer Wert macht die Swipe-Erkennung empfindlicher, ein größerer unempfindlicher.
      * `preventDefaults` (boolean): Ob das Plugin `event.preventDefault()` für die von ihm verarbeiteten Touch-Events aufrufen soll.
          * *`true` (oft Default)*: Verhindert das Standard-Browserverhalten für diese Touch-Gesten (z.B. Scrollen der Seite), was für eine reine Präsentationssteuerung meist gewünscht ist.
          * *`false`*: Lässt das Standardverhalten zu, was nützlich sein kann, wenn die `impress.js`-Präsentation in eine scrollbare Seite eingebettet ist und Swipes außerhalb der Präsentation weiterhin scrollen sollen.
  * **Wichtigkeit**: Essentiell für jede Präsentation, die auf mobilen Geräten oder Touch-Laptops präsentiert oder betrachtet werden soll.

#### H. `mobile` Plugin (oft als Teil von `extras` oder als separates Plugin)

  * **Zweck/Funktionalität**: Dieses Plugin (oder diese Sammlung von Funktionen) zielt darauf ab, das allgemeine Benutzererlebnis auf mobilen Geräten zu verbessern. Es kann sich mit dem `touch`-Plugin überschneiden oder es ergänzen.
  * **Mögliche Funktionen**:
      * **Swipe-Navigation**: Implementiert oder integriert die Swipe-Gesten (siehe `touch`-Plugin).
      * **Viewport-Optimierung**: Fügt dynamisch einen `<meta name="viewport" ...>`-Tag hinzu oder modifiziert ihn, um die Skalierung und Darstellung auf mobilen Bildschirmen zu optimieren (z.B. `width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no`).
      * **CSS-Anpassungen/Klassen**: Kann spezielle CSS-Klassen zum `<body>` hinzufügen, wenn ein mobiles Gerät erkannt wird (z.B. `impress-mobile`), damit du über CSS spezifische Stile für kleinere Bildschirme anwenden kannst (z.B. kleinere Schriftgrößen für UI-Elemente, Anpassung der Toolbar-Position).
      * **Adressleiste ausblenden**: Versucht manchmal, die Adressleiste mobiler Browser durch Scroll-Tricks auszublenden, um mehr Bildschirmfläche für die Präsentation zu gewinnen.
  * **Integration/Aktivierung**: Wenn es Teil von `extras.js` oder der Standard-`js/impress.js` ist, ist es oft automatisch aktiv.
  * **Konfigurationsoptionen**: Könnten Schalter enthalten, um bestimmte mobile Optimierungen zu de-/aktivieren. Beispiel (hypothetisch):
    ```javascript
    impress().init({
        plugins: {
            'mobile': {
                // optimizeViewport: true,
                // hideAddressBar: true
            }
        }
    });
    ```

Die genaue Funktionalität und die Konfigurationsmöglichkeiten für das "mobile" Verhalten sollten immer in der Dokumentation der verwendeten `impress.js`-Version oder im Quellcode der entsprechenden Plugin-Datei (`extras.js` oder `mobile.js`) überprüft werden.

Diese Plugins erweitern `impress.js` um viele wertvolle Funktionen. Es lohnt sich, ihre `README.md`-Dateien im `src/plugins/`-Ordner des Repositorys zu studieren, um alle Details und Konfigurationsmöglichkeiten zu verstehen.


## Teil 10: Best Practices, nicht-lineares ZUI-Design & weiterführende Tipps

Herzlichen Glückwunsch\! Du hast dich durch die Kernkonzepte, die API und die Plugin-Welt von `impress.js` gearbeitet. Du bist nun bestens gerüstet, um beeindruckende, nicht-lineare Präsentationen mit Zooming User Interface (ZUI) zu erstellen. In diesem letzten Teil wollen wir einige Best Practices, Design-Überlegungen, Performance-Tipps und Hilfestellungen für deine zukünftigen `impress.js`-Projekte zusammenfassen.

### Design-Prinzipien für effektive und verständliche nicht-lineare ZUI-Präsentationen

Die Freiheit, die `impress.js` bietet, ist enorm, birgt aber auch die Gefahr, das Publikum zu überfordern. Hier sind detaillierte Prinzipien für ein gelungenes Design:

1.  **Klarheit vor Spektakel (Content First – Der Inhalt regiert\!)**:

      * **Zweck der Effekte**: Jede Bewegung, jeder Zoom, jede Drehung sollte einen klaren **semantischen Zweck** haben. Unterstützt die Transformation das Verständnis, lenkt sie den Fokus, verdeutlicht sie eine Beziehung zwischen Inhalten? Oder ist es nur ein Effekt um des Effektes willen?
          * *Beispiel gut*: Hineinzoomen in eine Detailgrafik, die auf einem Übersichts-Step angedeutet wurde. Herauszoomen, um zu zeigen, wie verschiedene besprochene Punkte Teil eines größeren Ganzen sind.
          * *Beispiel schlecht*: Ständige, willkürliche Drehungen und schnelle Zooms zwischen jedem Satz, die keine inhaltliche Logik widerspiegeln und das Auge ermüden.
      * **Lesbarkeit des Inhalts**: Die Transformationen dürfen die Lesbarkeit des Inhalts auf den Steps niemals signifikant beeinträchtigen. Ein Step, der auf dem Kopf steht oder extrem perspektivisch verzerrt ist, mag technisch interessant sein, ist aber nutzlos, wenn die Botschaft nicht ankommt.
      * **Weniger ist oft mehr**: Eine oder zwei gut platzierte, bedeutungsvolle ZUI-Effekte pro Themenblock können wirkungsvoller sein als ein Feuerwerk an ständigen Bewegungen.

2.  **Struktur und Storytelling in nicht-linearen Räumen**:

      * **Mentale Karte (Mindmap-Ansatz)**: Bevor du beginnst, `data-x/y/z`-Werte einzutippen, skizziere die Struktur deiner Präsentation.
          * Identifiziere Hauptthemen und Unterthemen.
          * Überlege, wie diese räumlich zueinander in Beziehung stehen könnten (nebeneinander für gleichrangige Themen, untereinander für eine Abfolge, in die Tiefe für Details oder übergeordnete Kontexte).
          * Nutze die "unendliche Leinwand" als Werkzeug, um diese logischen Beziehungen visuell darzustellen.
      * **Klare Pfade und Orientierung**:
          * Obwohl die Präsentation nicht-linear sein kann, sollte es für das Publikum (und dich) einen oder mehrere klare "empfohlene Pfade" durch die Inhalte geben.
          * Der **Overview-Modus (ESC-Taste)** ist dein wichtigstes Werkzeug, um dem Publikum jederzeit eine "Karte" der Präsentation zu bieten und die Orientierung zu erleichtern. Nutze ihn aktiv\!
          * **Visuelle Anker**: Konsistente Designelemente, Farben oder räumliche Gruppierungen können helfen, thematische Blöcke zu kennzeichnen und die Navigation zu erleichtern.
          * **Logische Übergänge**: Auch wenn der Sprung groß ist, sollte der Übergang selbst (die Kamerabewegung) möglichst flüssig und nachvollziehbar sein. `impress.js` leistet hier gute Arbeit, aber deine räumliche Anordnung hat großen Einfluss.
      * **Erzählerische Klammer**: Jede gute Geschichte hat einen Anfang, einen Mittelteil und ein Ende. Definiere klare Start- und Endpunkte für deine Präsentation, auch wenn der Weg dazwischen variabel ist. Das `stop`-Plugin kann hier nützlich sein.

3.  **Lesbarkeit und Zugänglichkeit (Accessibility) – Extrem wichtig\!**:

      * **Textkontraste**: Achte auf einen sehr guten Kontrast zwischen Textfarbe und Hintergrundfarbe auf jedem Step. Dies ist besonders wichtig, da Lichtverhältnisse bei Projektionen variieren können. Tools zur Kontrastprüfung sind online verfügbar.
      * **Schriftgrößen und -arten**:
          * Wähle serifenlose Schriften (`sans-serif`) für gute Lesbarkeit auf Bildschirmen und Projektionen.
          * Die Schriftgröße muss ausreichend groß sein, auch für Zuschauer in der letzten Reihe. Teste dies unbedingt unter realen Bedingungen\!
          * Berücksichtige, dass Steps durch `data-scale` oder `data-z` kleiner erscheinen können – der Text muss dann immer noch lesbar sein oder der Zoom-Faktor muss entsprechend hoch sein.
      * **Animationsdauer und -geschwindigkeit (`transitionDuration`)**:
          * Zu schnelle Übergänge (unter 500ms) können abrupt und desorientierend wirken.
          * Zu langsame Übergänge (über 2000-3000ms) können das Publikum langweilen und ungeduldig machen.
          * Der Standardwert von `1000ms` (1 Sekunde) ist oft ein guter Kompromiss. Teste, was sich für deine Inhalte und deinen Sprechstil am besten anfühlt.
      * **Reduzierung von "Motion Sickness" (Reisekrankheit)**:
          * Exzessive, schnelle und wiederholte Drehungen (besonders um die X- oder Y-Achse) oder schnelle, unkontrollierte Zoomfahrten können bei empfindlichen Personen Unbehagen oder sogar Übelkeit auslösen.
          * Setze starke 3D-Rotationen und schnelle Zooms sehr gezielt und sparsam ein.
          * Sorge für "Ruhephasen": Jeder aktive Step sollte für eine ausreichende Zeit stabil im Fokus bleiben, damit das Publikum den Inhalt erfassen kann, bevor der nächste Übergang beginnt.
      * **Tastaturnavigation**: Stelle sicher, dass alle wesentlichen Navigationsschritte per Tastatur erreichbar sind (Pfeiltasten, Leertaste, ESC für Overview). `impress.js` bietet hier eine gute Grundlage.
      * **Fallback-Nachricht**: Die `<div class="fallback-message">` (siehe Teil 2) ist unerlässlich für Nutzer mit Browsern, die die für `impress.js` notwendigen CSS3-Features nicht unterstützen. Halte diese Nachricht informativ.

4.  **Konsistenz im Design**:

      * **Visuelle Sprache**: Entwickle eine einheitliche visuelle Sprache für deine Präsentation (Farbpalette, Typografie-Hierarchie, Stil von Grafiken und Bildern).
      * **Step-Design**: Steps, die zum selben Themenblock gehören, könnten ein ähnliches Layout oder Farbschema haben, um ihre Zusammengehörigkeit zu signalisieren.
      * **Navigationselemente**: Wenn du benutzerdefinierte Navigationselemente (Buttons, Links) verwendest, sollten diese konsistent gestaltet und positioniert sein.

5.  **Nutzung des Raumes (2D und 3D) mit Bedacht**:

      * **Z-Achse (`data-z`)**: Nutze die Tiefe, um Hierarchie, Fokus oder eine zeitliche/logische Abfolge darzustellen.
          * *Beispiel*: Ein Hauptthema auf `data-z="0"`, Details dazu auf `data-z="-500"`, weiterführende Gedanken auf `data-z="-1000"`. Der Übergang wirkt wie ein "Eintauchen".
          * Vermeide zu viele, sehr eng beieinander liegende Z-Ebenen, da dies die Orientierung erschweren kann.
      * **Rotationen (`data-rotate-x/y/z`)**:
          * Setze sie für dynamische Übergänge oder um die Perspektive auf ein Objekt zu ändern (z.B. die Seiten eines Würfels zeigen, wie im Cube-Beispiel).
          * Eine leichte Neigung (`data-rotate-x` oder `data-rotate-y` von wenigen Grad) kann einem Step eine subtile räumliche Präsenz verleihen, ohne die Lesbarkeit zu stören.
      * **Skalierung (`data-scale`)**:
          * Ideal, um Wichtigkeit zu betonen (größere Skalierung für wichtige Punkte).
          * Unverzichtbar, um bei starken Zooms in die Tiefe (`data-z` negativ) die Lesbarkeit von entfernten Steps zu gewährleisten, indem man sie gleichzeitig größer skaliert.

### Performance-Überlegungen bei komplexen Präsentationen

Je komplexer deine Präsentation, desto wichtiger wird die Performance. Ruckelnde Übergänge oder lange Ladezeiten können den positiven Eindruck zunichtemachen.

  * **Anzahl der Steps**: `impress.js` kann viele Steps verwalten, aber eine sehr hohe Anzahl (z.B. über 100-200, je nach Komplexität jedes Steps) kann die Initialisierungszeit verlängern und potenziell die Browser-Performance belasten, da für jeden Step Transformationen berechnet und im DOM gehalten werden. Fasse Inhalte sinnvoll zusammen.
  * **Inhalte der Steps – Optimierung ist der Schlüssel**:
      * **Bilder**:
          * **Komprimierung**: Nutze Tools wie TinyPNG, ImageOptim oder Squoosh, um die Dateigröße deiner Bilder ohne sichtbaren Qualitätsverlust drastisch zu reduzieren.
          * **Richtige Formate**: JPG für Fotos, PNG für Grafiken mit Transparenz oder scharfen Linien, SVG für Vektorgrafiken (skalieren verlustfrei\!). Moderne Formate wie WebP bieten oft bessere Kompression bei guter Qualität.
          * **Korrekte Dimensionen**: Skaliere Bilder vor dem Hochladen auf die ungefähre Größe, in der sie maximal auf einem Step angezeigt werden. Ein 5000px breites Bild für einen 800px breiten Bereich im Step zu verwenden, ist unnötige Ressourcenverschwendung.
      * **Videos**:
          * Binde Videos über das `<video>`-Tag ein und nutze das `preload="metadata"`-Attribut, damit nicht das gesamte Video sofort geladen wird.
          * Erwäge, Videos erst per JavaScript zu laden oder das Abspielen zu starten, wenn der entsprechende Step aktiv wird (`impress:stepenter`-Event).
          * Hoste Videos auf Plattformen wie Vimeo oder YouTube und binde sie als iFrame ein, wenn die Internetverbindung gesichert ist.
      * **Komplexe CSS-Effekte**:
          * Viele gleichzeitig animierte, komplexe `box-shadow`s, `filter`-Effekte (wie `blur()`) oder aufwendige CSS-Gradients können rechenintensiv sein. Setze sie gezielt ein.
      * **Anzahl der DOM-Elemente**: Ein Step, der aus tausenden von einzelnen HTML-Elementen besteht, wird den Browser beim Rendern und Transformieren stärker belasten als ein einfacherer Step. Halte dein HTML so schlank wie möglich.
  * **CSS-Selektoren**: Obwohl moderne Browser hier sehr optimiert sind, können extrem komplexe und tief verschachtelte CSS-Selektoren die Rendering-Performance geringfügig beeinflussen. Kurze, präzise Selektoren sind generell vorzuziehen.
  * **JavaScript-Interaktionen**:
      * Vermeide langlaufende JavaScript-Operationen, die synchron während eines `impress:stepenter`- oder `impress:stepleave`-Events ausgeführt werden, da diese die Übergangsanimation blockieren und zu Rucklern führen können.
      * Lagere aufwendige Berechnungen in `setTimeout(..., 0)` oder Web Worker aus, falls möglich.
  * **Hardwarebeschleunigung nutzen**:
      * `impress.js` und moderne Browser sind darauf ausgelegt, CSS-Transformationen (insbesondere `transform: translate3d(...)`, `scale3d(...)`, `rotate3d(...)`) und `opacity` über die GPU hardwarebeschleunigt auszuführen. Dies ist in der Regel sehr performant.
      * Vermeide es, andere CSS-Eigenschaften (wie `margin`, `top`, `left`, `width`, `height`) während der Hauptübergänge zu animieren, da diese oft CPU-intensiver sind und Layout-Neuberechnungen (Reflows) auslösen können.
  * **Testen, Testen, Testen**:
      * Teste deine Präsentation regelmäßig auf verschiedenen Geräten und Browsern, insbesondere auf dem Zielgerät, auf dem sie live präsentiert wird.
      * Nutze die Performance-Analyse-Tools der Browser-Entwicklerkonsolen (z.B. Chrome DevTools "Performance"-Tab), um Engpässe zu identifizieren.
  * **Plugins mit Bedacht wählen**: Jedes Plugin fügt potenziell JavaScript-Code und CSS hinzu, das ausgeführt und verarbeitet werden muss. Aktiviere nur die Plugins, die du wirklich für deine Präsentation benötigst.

### Häufige Fehler und deren Vermeidung (Troubleshooting-Ansätze)

  * **Problem: Steps sind nicht sichtbar oder völlig falsch positioniert.**

      * **CSS `position`**: Sicherstellen, dass `.step`-Elemente `position: absolute;` haben (oder `fixed`, falls ein sehr spezieller Effekt erzielt werden soll, aber `absolute` ist Standard für die `impress.js`-Logik).
      * **CSS-Konflikte**: Überprüfe, ob andere CSS-Regeln (aus eigenen Stylesheets oder Frameworks) die Transformationen oder die Sichtbarkeit der Steps überschreiben. Nutze die Browser-Entwicklertools, um die angewendeten Stile zu inspizieren.
      * **Fehlende `id="impress"`**: Der Hauptcontainer muss die korrekte ID haben, die `impress.js` erwartet (Standard: `impress`).
      * **Tippfehler in `data-*`-Attributen**: `data-x`, nicht `datax` oder `datax-x`. Überprüfe Groß-/Kleinschreibung und korrekte Attributnamen.
      * **JavaScript-Fehler**: Öffne die Browser-Konsole (meist mit F12). Fehler bei der Initialisierung von `impress.js` oder in deinem eigenen JavaScript werden hier angezeigt und verhindern oft die korrekte Ausführung.
      * **Falsche Pfade zu JS/CSS-Dateien**: Sicherstellen, dass die `impress.js`-Datei und deine CSS-Dateien korrekt verlinkt sind und geladen werden (Netzwerk-Tab der Entwicklertools).

  * **Problem: Übergänge sind ruckelig, langsam oder funktionieren gar nicht.**

      * **CSS `transition`-Definition**: Überprüfe, ob die `transition`-Eigenschaft korrekt auf das `#impress .canvas` (oder `#impress`) Element angewendet wird und `transform` als zu animierende Eigenschaft enthält. Ist die `transition-duration` vielleicht `0s` oder zu kurz/lang?
      * **Performance-Engpässe**: Siehe Abschnitt "Performance-Überlegungen". Große Bilder, komplexe Animationen innerhalb der Steps, oder rechenintensives JavaScript können die Ursache sein.
      * **Blockierendes JavaScript**: Langer synchroner JavaScript-Code, der während eines `impress:stepenter/leave` Events ausgeführt wird, kann den Browser daran hindern, die CSS-Transition flüssig darzustellen.

  * **Problem: 3D-Effekte (Tiefe, Perspektive) wirken flach oder sind nicht vorhanden.**

      * **`perspective` fehlt**: Dem `body` oder einem Elternelement von `#impress` muss eine CSS `perspective`-Eigenschaft zugewiesen sein (z.B. `perspective: 1000px;`). `impress.js` setzt dies oft über `impress-enabled` auf den Body, oder du kannst es via `data-perspective` am `#impress`-Div oder in der `init()`-Konfiguration setzen.
      * **`transform-style: preserve-3d;`**: Dieses CSS-Attribut muss auf Elementen gesetzt sein, deren Kinder 3D-transformiert werden sollen, damit die 3D-Transformationen korrekt "vererbt" und dargestellt werden. Für `#impress` und `.step` ist dies oft wichtig. `impress-common.css` setzt dies meist schon.
      * **`data-z`-Werte zu klein**: Wenn die Unterschiede in den `data-z`-Werten sehr gering sind und die `perspective` sehr groß ist, sind die Tiefeneffekte kaum wahrnehmbar.

  * **Problem: Navigation (Tastatur, Links) funktioniert nicht wie erwartet.**

      * **DOM-Reihenfolge**: Die Standard-Pfeiltasten-Navigation folgt der Reihenfolge der `.step`-Elemente im HTML. Ist diese korrekt?
      * **Tippfehler in IDs**: Bei `href="#meineID"` oder `impressApi.goto('meineID')` muss die ID exakt mit der `id` des Ziel-Steps übereinstimmen (Groß-/Kleinschreibung beachten\!).
      * **JavaScript-Konflikte**: Andere JavaScript-Bibliotheken auf der Seite könnten Tastatur- oder Klick-Events abfangen und die `impress.js`-Funktionalität stören. Versuche, andere Skripte testweise zu deaktivieren.
      * **`impress().init()` nicht aufgerufen**: Sicherstellen, dass die Initialisierung nach dem Laden der `impress.js`-Datei erfolgt.

  * **Problem: Schrift wird nach Transformationen unscharf.**

      * Dies ist ein bekanntes Rendering-Verhalten mancher Browser, besonders bei nicht-ganzzahligen Skalierungen oder starken Rotationen.
      * **Mögliche CSS-Abhilfen (experimentell)**:
          * `transform: translateZ(0);` oder `transform: translate3d(0,0,0);` auf dem Text-Element oder dem Step selbst kann das Element auf eine separate GPU-Ebene heben und manchmal das Rendering verbessern.
          * `backface-visibility: hidden;` kann ebenfalls helfen.
      * **SVG für Text**: Für kritische Texte, die stark transformiert werden, kann die Verwendung von SVG-Text eine schärfere Darstellung gewährleisten.
      * **Hochwertige Webfonts**: Gut designte Webfonts verhalten sich oft besser bei Transformationen als Systemschriften.

### Kreative Anwendungsbeispiele und Inspiration

Lass deiner Kreativität freien Lauf\! `impress.js` ist mehr als nur ein Präsentationstool.

  * **Storytelling mit räumlichen Metaphern**:
      * **Reise/Erkundung**: Führe das Publikum durch eine "Landschaft" von Ideen, zoome auf "Orte" (Steps), die Details enthalten.
      * **Das Innere eines Objekts**: Modelliere eine Maschine, ein Gehirn oder ein komplexes System und "fliege" zu den einzelnen Komponenten.
      * **Kosmos/Sonnensystem**: Planeten als Hauptthemen, Monde als Unterpunkte.
  * **Interaktive Infografiken**: Präsentiere Datenpunkte als Steps. Zoome und schwenke, um Beziehungen und Trends aufzuzeigen. Verlinke Steps, um alternative Analysen zu ermöglichen.
  * **Portfolio-Präsentationen**: Jedes deiner Projekte wird zu einer eigenen "Insel" oder einem eigenen "Raum", durch den du navigierst.
  * **Wissenslandkarten & Mindmaps**: Stelle komplexe Themengebiete und ihre Vernetzungen visuell dar. Ideal für Lehre und Wissensvermittlung.
  * **Virtuelle Touren und Ausstellungen**: Führe Benutzer durch virtuelle Räume, zeige Exponate (Bilder, Videos in Steps) aus verschiedenen Perspektiven.
  * **Spielerische Elemente**: Gestalte die Präsentation als eine Art "Point-and-Click"-Abenteuer, bei dem das Publikum den Pfad wählt.
  * **Ein-Seiten-Websites mit ZUI-Navigation**: Nutze `impress.js` als Basis für eine unkonventionelle Webseite.

**Inspiration finden**:

  * Die **offizielle `impress.js`-Demo** ([impress.js.org](https://impress.js.org/)) ist immer noch ein großartiger Startpunkt, um viele Features in Aktion zu sehen.
  * Durchsuche das Web nach "impress.js examples", "best impress.js presentations" oder schaue auf Plattformen wie CodePen oder GitHub nach Projekten, die `impress.js` verwenden.

### Wo man weitere Hilfe und Ressourcen findet (Stand: 15. Mai 2025)

  * **Offizielle Dokumentation im Repository**:
      * [`README.md`](https://www.google.com/search?q=%5Bhttps://github.com/impress/impress.js/blob/master/README.md%5D\(https://github.com/impress/impress.js/blob/master/README.md\)): Hauptübersicht.
      * [`GettingStarted.md`](https://www.google.com/search?q=%5Bhttps://github.com/impress/impress.js/blob/master/GettingStarted.md%5D\(https://github.com/impress/impress.js/blob/master/GettingStarted.md\)): Gute Anleitung für den Einstieg.
      * [`DOCUMENTATION.md`](https://www.google.com/search?q=%5Bhttps://github.com/impress/impress.js/blob/master/DOCUMENTATION.md%5D\(https://github.com/impress/impress.js/blob/master/DOCUMENTATION.md\)): Tiefergehende Erklärungen zu Konzepten.
      * `src/plugins/README.md` und die `README.md`-Dateien in den einzelnen Plugin-Verzeichnissen: Unverzichtbar für das Verständnis der Plugins.
  * **GitHub Repository**:
      * **Issues**: [github.com/impress/impress.js/issues](https://github.com/impress/impress.js/issues) – Durchsuche offene und geschlossene Issues, oft finden sich dort Lösungen für spezifische Probleme oder Diskussionen zu Features. Wenn du einen Bug findest oder eine gut recherchierte Frage hast, kannst du hier ein neues Issue erstellen.
      * **Discussions**: [github.com/impress/impress.js/discussions](https://www.google.com/search?q=https://github.com/impress/impress.js/discussions) – Für allgemeinere Fragen, Ideenaustausch und um Hilfe von der Community zu bekommen.
  * **Stack Overflow**: Eine riesige Wissensdatenbank. Suche mit dem Tag `[impress.js]` nach Fragen und Antworten: [stackoverflow.com/questions/tagged/impress.js](https://www.google.com/search?q=https://stackoverflow.com/questions/tagged/impress.js)
  * **Online-Tutorials und Artikel**: Suche nach aktuellen Tutorials. Beachte das Veröffentlichungsdatum, da sich Bibliotheken weiterentwickeln.
  * **Quellcode studieren**: Der Quellcode von `impress.js` selbst (`src/impress.js`) und seiner Plugins ist die ultimative Referenz. Er ist in der Regel gut kommentiert und kann helfen, das Verhalten im Detail zu verstehen.

### Zusammenfassung der Kernstärken von `impress.js`

  * **Revolutionäre nicht-lineare Präsentationen**: Befreit dich von der starren Abfolge traditioneller Slideshows und ermöglicht es, Geschichten dynamisch und flexibel zu erzählen.
  * **Visuell beeindruckende ZUI-Effekte**: Nutzt die volle Kraft moderner CSS3-Transformationen und -Transitionen, um ein fesselndes visuelles Erlebnis zu schaffen.
  * **Enorme kreative Freiheit**: Bietet eine "unendliche Leinwand" und Werkzeuge, um Inhalte auf einzigartige und einprägsame Weise zu visualisieren.
  * **Open Source und Community-getrieben**: Kostenlos verfügbar, anpassbar und durch die Beiträge der Community lebendig.
  * **Relativ leichtgewichtiger Kern**: Der Fokus liegt auf der Nutzung nativer Browser-Features (CSS, DOM-API), was es performant macht, wenn es richtig eingesetzt wird.
  * **Gute Browserunterstützung**: Läuft in allen modernen Desktop- und vielen mobilen Browsern, die die notwendigen CSS3-Features implementiert haben.

### Abschließende Worte

Du hast nun einen tiefen Einblick in die Welt von `impress.js` erhalten. Die wahre Meisterschaft kommt, wie bei jedem mächtigen Werkzeug, durch Übung und Experimentieren. Scheue dich nicht, die Grenzen auszuloten, kreativ zu werden und die hier vorgestellten Techniken und Prinzipien anzuwenden.

Erstelle Präsentationen, die nicht nur informieren, sondern auch inspirieren und im Gedächtnis bleiben. Viel Spaß und Erfolg bei deinen `impress.js`-Projekten\!
 
 
