# Klima-Velotour Paris

Private Fahrrad-Stadtführung durch Paris (halber Tag, Start am Hotel PiaPia + 8 Stationen) zu Klimaschutz, Klimaanpassung und nachhaltigem Wirtschaften — für eine Reise mit meinem Vater, Anfang September 2026.

Ein einziges self-contained `index.html` — kein Build-Schritt, keine Abhängigkeiten. Läuft direkt im Handy-Browser, auch wichtig, da die Seite unterwegs auf dem Velo genutzt wird.

## Live schalten (GitHub Pages)

1. Neues Repo auf GitHub erstellen (öffentlich — private Repos brauchen für kostenlose Pages einen bezahlten Plan, ist hier aber unkritisch, da keine sensiblen Inhalte).
2. Diesen Ordner (`index.html` + `README.md`) hineinpushen:
   ```bash
   git init
   git add index.html README.md
   git commit -m "Erste Version der Klima-Velotour Paris"
   git branch -M main
   git remote add origin https://github.com/<dein-username>/<repo-name>.git
   git push -u origin main
   ```
3. Auf GitHub: **Settings → Pages → Build and deployment → Source** = "Deploy from a branch", Branch = `main`, Ordner = `/ (root)`.
4. Nach ein bis zwei Minuten live unter `https://<dein-username>.github.io/<repo-name>/`.

## Checkliste vor der Reise

- [ ] **Petite Ceinture (Station 6)**: vermutlich nicht befahrbar innerhalb des Jardins — Velos am Eingang (34 Boulevard Kellermann oder Rue Damesme) abstellen, kurzes Stück zu Fuss
- [ ] **La Caverne (Station 8)**: Innenbereich vermutlich nur mit Anmeldung/Führung zugänglich — vorher klären, sonst reicht die Fassade
- [ ] **École Keller (Station 7)**: nur samstags 10–19 Uhr öffentlich zugänglich — Tourdatum darauf abstimmen
- [ ] Alle 6 eingebetteten Videos einmal kurz antesten (sind über die YouTube-oEmbed-API als existierend/einbettbar verifiziert, aber nie selbst abgespielt worden)
- [ ] Alle 7 eingebetteten Vorher/Nachher- und Einzelfotos einmal laden lassen — beim Testen wurde eines (Wikimedia Commons, Station 3 "Nachher") wiederholt mit HTTP 429 (Rate-Limit) blockiert; der Bildinhalt selbst wurde vorher visuell verifiziert, das Laden im Browser sollte aber trotzdem einmal bestätigt werden
- [ ] Mobile Daten: die Videos brauchen Internet — Route funktioniert aber auch ohne, alle Kerninhalte stehen als Text auf der Seite
- [ ] Bike-Route vorher einmal am Rechner durchklicken (Link "Ganze Route in Google Maps öffnen" oben auf der Seite)
- [ ] **Velo-Infrastruktur an zwei Stellen nicht verifiziert**: (1) Hotel → Station 1 (Rivoli, ~5-6 km quer durch die Stadt, neu dazugekommen, nie geprüft), (2) Station 5 → 7 (Bassin d'Austerlitz → Petite Ceinture → École Keller). Der vorgeplante Maps-Link nimmt irgendeine Route, nicht garantiert auf Velostrassen — an beiden Stellen am Tourtag live navigieren statt dem Link blind folgen. Strecken 1–5 und 7–8 (via Canal Saint-Martin/Boulevard Magenta) sind dagegen gut ausgebaut.
- [x] **Vélib'-Station am Hotel verifiziert (2026-08-28)**: heisst "Pyrénées - Avron", liegt laut offiziellem GBFS-Live-Feed (velib-metropole-opendata.smovengo.cloud) nur ~5 m von 73 Rue des Pyrénées entfernt, 32 Docks bestätigt, Station ist installiert und aktiv (`is_installed`/`is_renting` = 1). Bleibt trotzdem sinnvoll, die Radverfügbarkeit kurz vor Abfahrt in der App zu checken — die schwankt stündlich (beim Test: 0 Räder, aber 32 freie Docks).
- [ ] **Neu, Station 3 (Voie Georges Pompidou)**: Kartenpunkt "Pont Louis-Philippe" ist eine Näherung für den Startpunkt der autofreien Uferpromenade, nicht selbst vor Ort geprüft — sollte aber unkritisch sein, da die ganze Strecke Hôtel de Ville → Pont Marie ohnehin am Wasser entlangführt.
- [ ] Montmartre/Sacré-Cœur ist bewusst nicht mehr Teil der Route (Rue de Ravignan bis 13,6% Steigung, offiziell eine der zwei steilsten Veloachsen von Paris) — falls gewünscht, Velos am Fuss abschliessen und zu Fuss hoch

## Struktur

Jede Station: Kartenlink → Kontext-Text → Video oder Vorher/Nachher-Fotos (wo vorhanden). Bewusst schlank gehalten, keine Diskussionsfragen-Prompts mehr — die Gespräche ergeben sich unterwegs von selbst. Themen farblich codiert: grün = Klimaschutz, blau = Klimaanpassung, orange = nachhaltiges Wirtschaften.

Vorher/Nachher-Fotos (Stationen 1, 2, 3) stammen aus frei lizenzierten Quellen (Wikimedia Commons, CC BY/CC BY-SA) oder von cdn.paris.fr (Ville de Paris, offizielle Pressefotos) — keine Bloomberg/Getty-Bilder, da deren Fotos redaktionell lizenziert sind. Station 7 (École Keller) hat ein echtes Foto dieser Schule, aber kein Vorher-Bild. Für die Stationen 5, 6 und 8 wurde kein brauchbares freies Vorher/Nachher-Material gefunden — dort bleibt es bei Text/Video.

## Station 3: Voie Georges Pompidou (neu, 2026-08-28)

Ergänzt nach Lektüre von Bloomberg "This Paris Tour Reveals How Hidalgo Made City Greener, More Car-Free" (2026-03-20) und einem Substack-Artikel des Urban Cycling Institute. Die ehemalige Seine-Uferschnellstrasse (43'000 Autos/Tag bis 2016/17) liegt genau auf dem Weg zwischen Station 2 (Hôtel de Ville) und Station 4 (Seine bei Notre-Dame) — kein Umweg. Kartenpunkt Pont Louis-Philippe ist eine Näherung, nicht selbst vor Ort geprüft.

Bastille (im selben Bloomberg-Artikel als weiteres Vorher/Nachher-Beispiel genannt) wurde bewusst **nicht** aufgenommen: liegt nicht auf dem direkten Weg zwischen Station 5 (Bassin d'Austerlitz) und Station 7 (École Keller) und hätte einen zusätzlichen Umweg auf einem ohnehin schon unsicheren Streckenabschnitt bedeutet.

## Station 7: Verbindung zur 15-Minuten-Stadt (2026-08-28)

École Keller ist jetzt explizit mit dem 15-Minuten-Stadt-Konzept aus dem Hintergrund-Abschnitt verknüpft, inkl. Video-Ausschnitt (start=920&end=1027, ca. 15:20–17:07) aus derselben DW-REV-Dokumentation. Timestamp gefunden via yt-dlp-Transkript (automatische deutsche Untertitel) — Carlos Moreno erklärt dort das Konzept und benennt selbst die Ungleichheit (manche brauchen eine Stunde statt 15 Minuten), was gut zur Kritik-Box im Hintergrund-Abschnitt passt.

## Quellen

Recherchiert Ende Juli/Anfang August 2026, siehe Chatverlauf für Einzel-Quellen (Ville de Paris, FRANCE 24, Brut, Le Nouvel Obs, INRAE-Kritik an der Miyawaki-Methode via tela-botanica.org/enlargeyourparis.fr, Mairie du 13e zur Petite Ceinture, Bloomberg CityLab und reporterre.net zur Voie Georges Pompidou).
