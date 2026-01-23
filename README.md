# 📂 Time & Space - System Dokumentation

> **Status:** LIVE 🟢
> **URL:** https://timeandspace.online
> **Zweck:** Statische Landingpage / Funnel für System-Analysen.

---

## 🧠 Warum dieses Setup? (Entscheidungsprotokoll)

Wir haben uns gegen Baukästen (Wix/Strato) und gegen Netlify entschieden. Hier ist der Grund:

### 1. Warum GitHub? (Das "Lager")
* **Was es ist:** Ein Ort, an dem der Programmcode (Dateien) sicher gespeichert wird.
* **Warum wir es nutzen:**
    * **Versicherung:** Wenn ich am Computer etwas lösche, ist es hier noch da.
    * **Versionierung:** Ich kann sehen, was ich vor 2 Wochen geändert habe.
    * **Industrie-Standard:** Jede moderne KI versteht GitHub-Strukturen perfekt.

### 2. Warum GitHub Pages? (Der "Server")
* **Was es ist:** Ein kostenloser Dienst von GitHub, der HTML-Dateien ins Internet stellt.
* **Warum nicht Strato Hosting?** Strato verlangt für einfaches Hosting monatliche Gebühren. GitHub Pages ist dauerhaft kostenlos und schneller.
* **Warum nicht Netlify?** Wir hatten einen "False Positive" Spam-Alarm wegen VPN-Nutzung (CyberGhost). GitHub ist robuster und sperrt nicht sofort bei VPN-Nutzung.

---

## 🏗 Die Architektur (Das "Haus")

Dieses Projekt ist eine **statische Website** (HTML/CSS).
Es gibt **kein Backend**, keine Datenbank und kein Wordpress auf der Hauptdomain.

### Die Komponenten
* **Domain:** Strato (`timeandspace.online`).
    * *DNS:* A-Record zeigt auf GitHub IP `185.199.108.153`.
* **Domain:** Strato (`timeandspace.online`).
    * *DNS:* A-Record zeigt auf GitHub IP `185.199.108.153`.
* **Content (Die Dateien):**
    * `index.html`: Die Hauptseite (Startseite).
    * `style.css`: Das Design (Terminal-Look, Neon-Pink #FF1493).
    * `logo.png`: Das Logo (freigestellt via remove.bg).
* **Rechtliches (Legal Pages):**
    * `impressum.html`: Anbieterkennzeichnung (Link im Footer).
    * `datenschutz.html`: Datenschutzerklärung (Link im Footer).
    * *Hinweis:* Diese Seiten nutzen denselben CSS-Style, sind aber eigenständige Dateien.
* **Interaktion:**
    * Das Audit-Formular kommt von **[Tally.so](https://tally.so)** (als iFrame eingebettet).
* **Interaktion:**
    * Das Audit-Formular kommt von **[Tally.so](https://tally.so)**.
    * Es ist per `<iframe>` eingebettet. Änderungen mache ich NUR bei Tally.

### Die Subdomains (Die Blogs)
Meine Blogs laufen **unabhängig** von diesem Code auf Ghost:
* `explore.timeandspace.online` (Ghost Blog 1)
* `beyond.timeandspace.online` (Ghost Blog 2)
* *Hinweis:* Diese laufen über CNAME-Records bei Strato direkt zu Ghost.

---

## 🛠 Workflow (Wie arbeite ich hier?)

### Szenario A: Text/Design ändern
1.  Datei (`index.html` oder `style.css`) auf dem Laptop ändern.
2.  Lokal im Browser testen.
3.  Datei hier bei GitHub hochladen ("Add file" -> "Upload").
4.  **Warten:** Es dauert ca. 1-2 Minuten, bis die Änderung live ist ("Bauarbeiter-Pause").

### Szenario B: Formular ändern
1.  Einloggen bei [Tally.so](https://tally.so) j.mei... 123...
2.  Ändern & "Publish" klicken.
3.  **Nichts hochladen!** Die Website aktualisiert sich von selbst.

### Szenario C: Neues Logo
1.  Logo freistellen (z.B. remove.bg).
2.  Datei exakt `logo.png` nennen.
3.  Hier hochladen und überschreiben.

---

## 🤖 Anweisung für KI-Assistenten

*Wenn ich (der User) Fragen zu diesem Repo stelle:*
1.  Dies ist eine reine HTML/CSS Seite (Static Site). Schlage keine React/Node.js/Wordpress Lösungen vor.
2.  Das Design ist "Minimalist Dark Terminal". Halte CSS-Vorschläge in diesem Stil.
3.  Verstehe, dass die Blogs (`explore`/`beyond`) NICHT in diesem Repo liegen.
