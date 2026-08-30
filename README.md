# Klima-Velotour Paris

Private Fahrrad-Stadtführung durch Paris (halber Tag, Start am Hotel PiaPia + 10 Stationen, plus eine reine Info-Erwähnung ohne Halt) zu Klimaschutz, Klimaanpassung und nachhaltigem Wirtschaften — für eine Reise Anfang September 2026.

`index.html` ist self-contained bis auf zwei lokale Bilder (kein Build-Schritt, keine externen Abhängigkeiten ausser YouTube-Embeds und den beiden Station-10-Fotos `flocon_before.png`/`flocon_after.png`) und läuft direkt im Handy-Browser. Dazu kommt `karte-vegan-bier.html`, eine separate Leaflet/OpenStreetMap-Karte mit veganen Restaurants und Bierlokalen (braucht Internet für Kartenkacheln) — beide Seiten verlinken sich gegenseitig.

> **Zur Stationen-Nummerierung**: Die Nummern haben sich über mehrere Sessions mehrfach verschoben (zuletzt am 2026-08-30 durch die neue Station 1, die Verschiebung der Petite-Ceinture-Station auf Platz 2, und danach auch von Bassin d'Austerlitz auf Platz 3). Alle älteren, datierten Changelog-Einträge weiter unten verwenden jeweils die zu ihrem Zeitpunkt gültige Nummerierung, nicht die aktuelle — nur Checkliste, Struktur-Abschnitt und Überblick oben sind auf dem aktuellen Stand.

## Live schalten (GitHub Pages)

1. Neues Repo auf GitHub erstellen (öffentlich — private Repos brauchen für kostenlose Pages einen bezahlten Plan, ist hier aber unkritisch, da keine sensiblen Inhalte).
2. Diesen Ordner (`index.html`, `README.md`, `karte-vegan-bier.html`, `flocon_before.png`, `flocon_after.png`) hineinpushen:
   ```bash
   git init
   git add index.html README.md karte-vegan-bier.html flocon_before.png flocon_after.png
   git commit -m "Erste Version der Klima-Velotour Paris"
   git branch -M main
   git remote add origin https://github.com/<dein-username>/<repo-name>.git
   git push -u origin main
   ```
3. Auf GitHub: **Settings → Pages → Build and deployment → Source** = "Deploy from a branch", Branch = `main`, Ordner = `/ (root)`.
4. Nach ein bis zwei Minuten live unter `https://<dein-username>.github.io/<repo-name>/`.

## Checkliste vor der Reise

- [ ] **Petite Ceinture 13e (Station 2)**: vermutlich nicht befahrbar innerhalb des Jardins — Velos am Eingang (34 Boulevard Kellermann oder 60 Rue Damesme) abstellen, kurzes Stück zu Fuss
- [ ] **La Recyclerie (Station 9)**: Öffnungszeiten/Programm (Restaurant, Ferme, Werkstatt) vorher auf larecyclerie.com checken, nicht alles ist immer gleichzeitig zugänglich
- [ ] **École Keller (Station 8)**: nur samstags 10–19 Uhr öffentlich zugänglich — Tourdatum darauf abstimmen
- [ ] **Square Charles Péguy (Station 1)**: Öffnungszeiten im September laut Stadt Paris Mo–Fr 8–19:30, Sa/So 9–19:30 Uhr — für den Tourstart am Nachmittag unkritisch, aber gegenchecken
- [ ] Alle 7 eingebetteten Videos einmal kurz antesten (sind über die YouTube-oEmbed-API als existierend/einbettbar verifiziert, aber nie selbst abgespielt worden)
- [ ] Alle 7 eingebetteten Vorher/Nachher- und Einzelfotos einmal laden lassen — beim Testen wurde eines (Wikimedia Commons, Station 6 "Nachher") wiederholt mit HTTP 429 (Rate-Limit) blockiert; der Bildinhalt selbst wurde vorher visuell verifiziert, das Laden im Browser sollte aber trotzdem einmal bestätigt werden
- [ ] Mobile Daten: die Videos brauchen Internet — Route funktioniert aber auch ohne, alle Kerninhalte stehen als Text auf der Seite
- [ ] Bike-Route vorher einmal am Rechner durchklicken (Link "Ganze Route in Google Maps öffnen" oben auf der Seite)
- [x] **Velo-Infrastruktur segmentweise geprüft (2026-08-30, via Websuche zu Pariser Radwegen)** — Gesamtbild: die Tour liegt über weite Strecken auf offiziellen Pariser Rad-Hauptachsen, nur noch ein Abschnitt ist wirklich unsicher:
  - Hotel → Station 1 (Charles Péguy, 20e→12e, ~2–3 km): nicht einzeln geprüft, aber vermutlich unproblematisch — Cours de Vincennes/Avenue du Trône (direkte Verbindung Nation→Bel-Air) gehört laut Setec-Referenzliste zu den bereits realisierten Pariser Radwegprojekten.
  - Station 1 → 2 (Charles Péguy → Petite Ceinture/Kellermann, via Boulevards des Maréchaux): **gut** — liegt auf der Linie v10 (benannt "Petite Ceinture") des Réseau Vélo Île-de-France (früher RER Vélo), durchgehender Radweg. Einzige bekannte Lücke ist weit entfernt bei der Pont du Garigliano im Westen, betrifft uns nicht.
  - Station 2 → 3 (Kellermann → Bassin d'Austerlitz, quer durch den 13e): **gemischt** — Boulevard Vincent-Auriol hat einen Radweg (aus einem Bürgerhaushalts-Projekt), die naheliegendere Avenue des Gobelins gilt laut Anwohner-Radinitiative (MDB Paris 13) weiterhin als "fahrradfeindlich". Route deshalb explizit über Boulevard Vincent-Auriol geführt (neuer Wegpunkt im Maps-Link).
  - Station 3 → 4 (Bassin d'Austerlitz → Rivoli via Sorbonne/Quartier Latin): **gut** — Boulevard Saint-Michel hat einen frisch gebauten, geschützten Zweirichtungs-Radweg (Bauphasen-PDF der Stadt Paris), explizit auch im Abschnitt Rue des Écoles/Sorbonne. Boulevard Sébastopol/Saint-Michel ist eine der vier grossen Nord-Süd-Radachsen von Paris.
  - Station 4–7 (Rivoli → Forêt urbaine → Voie Georges Pompidou → Seine): **gut**, wie bisher — liegt auf den beiden anderen der vier Pariser Rad-Hauptachsen (Rivoli Ost-West, Seine-Kais beidseitig).
  - Station 7 → 8 (Seine/Notre-Dame → École Keller, 4e→11e, neue Verbindung seit der Umstellung von Bassin d'Austerlitz): **teilweise unsicher** — Rue Saint-Antoine hat seit 2017 einen Zweirichtungs-Radweg bis Place de la Bastille (neuer Wegpunkt im Maps-Link); von dort weiter über Rue de la Roquette, wo laut Paris en Selle (Stand Juni 2026) eine "vélorue" erst geplant/im Bau ist — Fertigstellung bis September 2026 nicht garantiert. **Bleibt die grösste offene Unsicherheit der Tour.**
  - Station 8 → 9 (École Keller → La Recyclerie, via Canal Saint-Martin/Boulevard Magenta): **gut**, wie bisher — Boulevard Magenta (Barbès–République) ist einer der meistgenutzten Radwege von Paris, seit 2020 durchgehend grün markiert; Canal-Saint-Martin-Promenade ist die vierte der vier Pariser Rad-Hauptachsen.
  
  Der Maps-Link nimmt trotzdem irgendeine von Google vorgeschlagene Route — an der Roquette/Bastille-Stelle und generell wegen Baustellen am Tourtag live navigieren.
- [ ] **Neu, Station 9 → 10 → Ausklang (alle im 18e, rund um Ornano/Jules Joffrin/Château Rouge)**: Distanzen zwischen La Recyclerie, Rue Ferdinand-Flocon, Urban Greener und Le Supercoin sind grob geschätzt, nicht kartografisch nachgemessen — sollten aber alle im selben kleinen Quartier liegen, kein grosser Umweg zu erwarten.
- [x] **Vélib'-Station am Hotel verifiziert (2026-08-28)**: heisst "Pyrénées - Avron", liegt laut offiziellem GBFS-Live-Feed (velib-metropole-opendata.smovengo.cloud) nur ~5 m von 73 Rue des Pyrénées entfernt, 32 Docks bestätigt, Station ist installiert und aktiv (`is_installed`/`is_renting` = 1). Bleibt trotzdem sinnvoll, die Radverfügbarkeit kurz vor Abfahrt in der App zu checken — die schwankt stündlich (beim Test: 0 Räder, aber 32 freie Docks).
- [ ] **Neu, Station 6 (Voie Georges Pompidou)**: Kartenpunkt "Pont Louis-Philippe" ist eine Näherung für den Startpunkt der autofreien Uferpromenade, nicht selbst vor Ort geprüft — sollte aber unkritisch sein, da die ganze Strecke Hôtel de Ville → Pont Marie ohnehin am Wasser entlangführt.
- [ ] Montmartre/Sacré-Cœur ist bewusst nicht mehr Teil der Route (Rue de Ravignan bis 13,6% Steigung, offiziell eine der zwei steilsten Veloachsen von Paris) — falls gewünscht, Velos am Fuss abschliessen und zu Fuss hoch

## Struktur

Jede Station: Kartenlink → Kontext-Text → Video oder Vorher/Nachher-Fotos (wo vorhanden). Themen farblich codiert: grün = Klimaschutz, blau = Klimaanpassung, orange = nachhaltiges Wirtschaften. Seit 2026-08-30 gibt es an zwei Stellen (Hintergrund, Ausklang) gezielt gesetzte Diskussionsboxen (türkis, "💬") zu Gentrifizierung/Mietsteigerung und der "Ist es genug?"-Frage — auf expliziten Wunsch, als bewusste Ausnahme von der vorherigen Entscheidung gegen Diskussionsfragen-Prompts. Eine zwischenzeitlich bei École Keller zusätzlich gesetzte "Geprüft"-Box und Diskussionsbox wurden noch am selben Tag wieder entfernt — ihr Inhalt (Rue Keller ist keine "rue aux écoles") lebt jetzt implizit im Kontrast zu Station 10 weiter. Drei weitere orange "Zum Nachdenken"-Boxen (Miyawaki-Kritik, Voie-Georges-Pompidou-Kontroverse, Montmartre-Hinweis) wurden ebenfalls auf Wunsch entfernt; übrig sind nur noch die Hintergrund-Box "Wer zahlt für die Verkehrswende?" und die "Ungeprüft"-Box im Start-Abschnitt.

Vorher/Nachher-Fotos (Stationen 4 Rivoli, 5 Forêt urbaine, 6 Voie Georges Pompidou, 10 Rue Ferdinand-Flocon) stammen aus frei lizenzierten Quellen (Wikimedia Commons, CC BY/CC BY-SA) oder von der Stadt Paris (offizielle Pressefotos) — keine Bloomberg/Getty-Bilder, da deren Fotos redaktionell lizenziert sind. Station 8 (École Keller) hat ein echtes Foto dieser Schule, aber kein Vorher-Bild. Für die Stationen 1 (Charles Péguy), 2 (Petite Ceinture 13e), 3 (Bassin d'Austerlitz), 9 (La Recyclerie) und die Info-Erwähnung La Caverne wurde kein brauchbares freies Vorher/Nachher-Material gefunden — dort bleibt es bei Text/Video bzw. reinem Text.

Station 10 (Rue Ferdinand-Flocon) ist ein Sonderfall: Die beiden Bilder (`flocon_before.png`, `flocon_after.png`) liegen als lokale Dateien im Projektordner statt extern verlinkt zu sein (dadurch beim `git add` und Pages-Deploy nicht vergessen — `.gitignore` schliesst nur `*.pdf` aus, PNGs sind nicht betroffen). Das Vorher-Bild ist ein Google-Street-View-Screenshot inkl. sichtbarer Bedienelemente (Kompass, Zoom, Mini-Karte unten links) — optisch nicht so sauber wie die anderen Vorher-Bilder, aber vom Nutzer bewusst so bereitgestellt. Das Nachher-Bild ist ein offizielles Ville-de-Paris-Pressefoto (Guillaume Bontemps).

## Station 3: Voie Georges Pompidou (neu, 2026-08-28)

Ergänzt nach Lektüre von Bloomberg "This Paris Tour Reveals How Hidalgo Made City Greener, More Car-Free" (2026-03-20) und einem Substack-Artikel des Urban Cycling Institute. Die ehemalige Seine-Uferschnellstrasse (43'000 Autos/Tag bis 2016/17) liegt genau auf dem Weg zwischen Station 2 (Hôtel de Ville) und Station 4 (Seine bei Notre-Dame) — kein Umweg. Kartenpunkt Pont Louis-Philippe ist eine Näherung, nicht selbst vor Ort geprüft.

Bastille (im selben Bloomberg-Artikel als weiteres Vorher/Nachher-Beispiel genannt) wurde bewusst **nicht** aufgenommen: liegt nicht auf dem direkten Weg zwischen Station 5 (Bassin d'Austerlitz) und Station 7 (École Keller) und hätte einen zusätzlichen Umweg auf einem ohnehin schon unsicheren Streckenabschnitt bedeutet.

## Station 7: Verbindung zur 15-Minuten-Stadt (2026-08-28)

École Keller ist jetzt explizit mit dem 15-Minuten-Stadt-Konzept aus dem Hintergrund-Abschnitt verknüpft, inkl. Video-Ausschnitt (start=920&end=1027, ca. 15:20–17:07) aus derselben DW-REV-Dokumentation. Timestamp gefunden via yt-dlp-Transkript (automatische deutsche Untertitel) — Carlos Moreno erklärt dort das Konzept und benennt selbst die Ungleichheit (manche brauchen eine Stunde statt 15 Minuten), was gut zur Kritik-Box im Hintergrund-Abschnitt passt.

## Station 8: La Recyclerie (neu, 2026-08-28)

Google Maps zeigt beim Öffnen des "Ganze Route"-Links automatisch La Recyclerie und Paname Brewing Company als hervorgehobene Orte entlang der Strecke an (Googles eigene POI-Vorschläge, nicht von uns gesetzt). La Recyclerie — ein altes Bahnhofsgebäude der Petite Ceinture (Gare d'Ornano), seit 2014 zu Restaurant/Werkstatt/Stadtfarm umgebaut — passte inhaltlich zu gut, um es zu ignorieren: direkter Bezug zu Station 6 (dieselbe Bahnlinie), nur diesmal aktiv gestaltet statt sich selbst überlassen. Liegt mit ~1,25 km nur unwesentlich abseits der direkten Strecke Station 7 → La Caverne (Direktweg: ~4,8 km, mit Abstecher: ~5,4 km + 1,25 km). Paname Brewing Company (Canal de l'Ourcq, 19e) liegt dagegen ~3,8 km von Station 7 entfernt, klar ausserhalb der Route — kam stattdessen auf `karte-vegan-bier.html`.

## La Caverne: von Station 9 zurückgestuft auf reine Info (2026-08-28)

Auf Wunsch kein aktiver Halt mehr — der Abstecher (~1,25 km ab La Recyclerie) hätte die Tour unnötig verlängert. Bleibt als eigener Abschnitt "Nebenbei: La Caverne" ganz am Ende der Seite (nach dem Ausklang) stehen, mit Text/Video wie zuvor, aber ohne Nummerierung, ohne Platz in der Stationenzählung (zurück auf 8) und ohne Waypoint im "Ganze Route"-Link. Die Abschluss-Distanzen (Urban Greener, Le Supercoin) wurden entsprechend von "ab La Caverne" auf "ab La Recyclerie" umgerechnet, da das jetzt der letzte tatsächlich angefahrene Punkt vor dem Ausklang ist.

## Gentrifizierung/Mietsteigerung ergänzt (2026-08-30)

Auf Basis des Republik-Artikels "Au revoir, Paris" (Marie-José Kolly, 29.08.2026, PDF liegt im Ordner) drei Diskussionsboxen ergänzt:

- **Hintergrund-Abschnitt**: konkrete Zahl (Quadratmeterpreis rund um "rues aux écoles" +8% in 2 Jahren), Fallbeispiele aus dem Artikel (Nicolas/Montmartre, Morgane/herausgentrifiziert), Hidalgos eigene Antwort auf die Gentrifizierungsfrage im Interview, Diskussionsfragen dazu.
- **Station 7 (École Keller)**: Kontext zum "rues aux écoles"-Programm (>300 Strassen seit 2020, Stand September 2025 gut die Hälfte aller Kitas/Grundschulen) plus geprüfter Fakt — die Rue Keller selbst ist **nicht** auf der offiziellen Liste (paris.fr "Plus de 300 rues aux écoles" / Mairie du 11e); nächstgelegene gelistete Strasse ist der Passage des Taillandiers (~400–500 m, nicht selbst vor Ort verifiziert).
- **Ausklang**: Schlussdiskussion "Ist es genug?" mit den Kernzitaten aus dem Artikel (Hitzewelle-Zahlen, Hidalgos "Oui, bien sûr", Maëder Oliviers "jede Massnahme ist zu wenig").

## Station 9: Rue Ferdinand-Flocon, echte "rue aux écoles" (neu, 2026-08-30)

Auf Wunsch die "Geprüft"-Box (Rue Keller ist keine offizielle "rue aux écoles") und die zugehörige Diskussionsbox bei Station 7 wieder entfernt. Stattdessen eine neue **Station 9** eingefügt, die wirklich eine der über 300 offiziellen "rues aux écoles" zeigt: Rue Ferdinand-Flocon, 75018 — seit 1.9.2021 dauerhaft autofrei/begrünt, mit École maternelle (Nr. 3) und École élémentaire (Nr. 5) direkt an der Strasse, offiziell auf der Liste der Mairie du 18e (anders als Rue Keller beim 11e). Zufällig auch die Strasse aus dem Bild-Sujet der Republik-Reportage (Sacré-Cœur über begrünter Strasse).

Platzierung fürs Routing: direkt zwischen Station 8 (La Recyclerie, Boulevard Ornano) und dem Ausklang (Urban Greener/Le Supercoin) eingefügt — alle drei liegen im selben 18e-Cluster rund um Jules Joffrin/Château Rouge, dadurch kaum Umweg. Rue Ferdinand-Flocon liegt ausserdem sehr nah am ohnehin gesetzten Google-Maps-Zielpunkt "Place Jules Joffrin". Als neuer Waypoint in den "Ganze Route"-Link aufgenommen, Stationenzahl in Titel/Überblick von acht auf neun erhöht.

Achtung Nummerierungs-Historie: Der Slot "Station 9" hiess einmal (28.08.) La Caverne, wurde dann zur reinen Info ohne Nummer zurückgestuft (siehe Abschnitt oben) — die "9" ist jetzt für einen komplett anderen, tatsächlich angefahrenen Ort neu vergeben. La Caverne bleibt unverändert die unnummerierte Info-Erwähnung ganz am Schluss.

## Orange Kritik-Boxen bei Station 2, 3 und Ausklang entfernt (2026-08-30)

Auf Wunsch drei der ursprünglichen orangen "Zum Nachdenken"-Boxen gelöscht: INRAE-Kritik an der Miyawaki-Methode (Station 2), Kontroverse um die Voie Georges Pompidou (Station 3), Hinweis zu Montmartre/Sacré-Cœur (Ausklang). Übrig bleiben nur noch die Hintergrund-Box "Wer zahlt für die Verkehrswende?" und die "Ungeprüft"-Box zur Strecke Hotel → Station 1 — beide nicht explizit zum Löschen genannt. Der Montmartre-Steigungshinweis (13,6%) bleibt als Info in der Checkliste oben erhalten, auch ohne eigene Box auf der Seite.

## Petite Ceinture ausgebaut + neue Station 1: Square Charles Péguy (2026-08-30)

Auf Basis von zwei Blogartikeln (paris-blog.org, "Die Petite Ceinture" Teil 1 und 2, Februar/März 2020) die Petite-Ceinture-Station im 13e (damals Station 6, heute **Station 7**) inhaltlich ausgebaut: Eröffnungsjahr 2016 (drittes Teilstück nach 16e/2007 und 15e/2013), ehemaliges Bahnhofsareal Rungis (daher zusätzlich Rasen-/Spielflächen, nicht nur Gleise), 500 m Länge begrenzt durch zwei Tunnel, ein zweiter nicht-öffentlicher Gemeinschaftsgarten direkt daneben, plus das Infotafel-Quiz (gesuchtes Tier: Wildschwein). Adresse präzisiert auf 60 Rue Damesme mit Metro/Tram-Anschluss.

Ausserdem geprüft, ob laut denselben Artikeln weitere Stationen sinnvoll wären — insbesondere die im Chat explizit genannten Gemeinschaftsgärten am Square Charles Péguy (12e). Ergebnis: ja, als neue **Station 1**, gleich nach dem Start eingefügt (alle bisherigen Stationen 1–9 wurden entsprechend zu 2–10, siehe Hinweis-Box ganz oben in diesem Dokument). Inhalt: Gemeinschaftsgärten der Vereinigung "Graine de Partage" direkt neben den Gleisen (21 Rue Rottembourg, 75012), seit 2008 ein 200 m Lehrpfad mit drei Vegetationsstufen, Ecojardin-Label — alles über die offizielle paris.fr-Seite zu Square Charles Péguy verifiziert (aktueller und detaillierter als der elf Jahre alte Blogartikel). Dazu ein optionaler Hinweis auf den nahen, nicht in die Route aufgenommenen Abschnitt Villa du Bel Air/Rue des Meuniers (1670 m, verbindet zur Coulée verte René-Dumont/Bois de Vincennes).

Begründung für die Platzierung direkt nach dem Start: (1) inhaltlich die dritte, deutlich gegensätzliche Spielart derselben Ringbahn — grassroots-organisiert statt der Natur überlassen (Station 7) oder professionell gestaltet (Station 9) —, ein Kontrast, den die Tour jetzt explizit an drei Stellen aufbaut; (2) geografisch in der Nähe des Hotels (20e/12e-Grenze bei Nation/Vincennes, laut Websuche ca. 2-3 km, nicht kartografisch nachgemessen), wodurch die ohnehin lange, ungeprüfte Direktstrecke Hotel→Rivoli (~5-6 km) in zwei besser planbare Etappen zerlegt wird, auch wenn das in der Summe vermutlich 1-2 km länger ist als der direkte Weg. Diese Distanzschätzungen sind nicht kartografisch verifiziert — am Tourtag live navigieren, siehe Checkliste oben.

## Reihenfolge geändert: Petite Ceinture direkt hinter Station 1 (2026-08-30, abends)

Auf Wunsch umgestellt: Station "Petite Ceinture (13e)" — bis dahin Station 7, zwischen Bassin d'Austerlitz und École Keller — wandert direkt hinter die neue Station 1 (Square Charles Péguy) und wird damit selbst zu **Station 2**. Alle dazwischenliegenden Stationen (vormals Rivoli 2, Forêt urbaine 3, Voie Georges Pompidou 4, Seine 5, Bassin d'Austerlitz 6) rücken um eins nach hinten (jetzt 3–7). École Keller (8), La Recyclerie (9) und Rue Ferdinand-Flocon (10) bleiben unverändert, da sie hinter dem verschobenen Block liegen. Google-Maps-Waypoints und Ungeprüft-Box im Start-Abschnitt entsprechend angepasst.

Vorher explizit geprüft: Lässt sich zwischen Station 1 (12e, nahe Bois de Vincennes) und der Petite-Ceinture-Station im 13e (Boulevard Kellermann, nahe Porte d'Italie) ein Stück auf der stillgelegten Bahntrasse selbst laufen, z. B. Richtung Porte de Choisy? Laut offizieller Mairie-du-13e-Seite und dem Status-Update der Association Sauvegarde Petite Ceinture (ASPCRF, Dezember 2024): **Nein.** Die Abschnitte im 13e (Avenue d'Italie/Choisy, Boulevard Masséna/Porte de Vitry, Kellermann/Poterne des Peupliers) sind explizit nicht miteinander verbunden ("pas nécessairement connectés entre eux"), der einzige mögliche Verbindungspunkt (ein Tunnel bei den Gobelins) ist "noch in Prüfung", und der nächstgelegene neue Abschnitt (Rue de Patay → Gare Masséna) öffnet laut Mairie du 13e erst im Oktober 2026 — nach der Reise. Auch geografisch liegt zwischen Station 1 (12e) und der Petite-Ceinture-13e-Station die Seine-Querung der Ringbahn, die nicht für Fussgänger/Velos geöffnet ist. Die Verbindung Station 1 → 2 läuft deshalb ganz normal auf der Strasse, am ehesten entlang der Boulevards des Maréchaux (Poniatowski → Kellermann) — passenderweise derselben Route, die historisch dem Festungsgürtel folgte, der schon im Hintergrund-Abschnitt der Tour erwähnt wird.

Bewusst nicht umgesetzt (Stand 30.08., abends): die Alternative, auch Bassin d'Austerlitz (ebenfalls 13e) mit in den Block vorzuziehen — das hätte eine grössere Kaskade an Umnummerierungen ausgelöst und wurde per Nachfrage explizit nicht gewählt. **Update, noch selben Abend**: doch umgesetzt, siehe nächster Abschnitt.

## Bassin d'Austerlitz zu Station 3, via Sorbonne Université zu Rivoli (2026-08-30, spätabends)

Die zuvor bewusst zurückgestellte Option doch noch umgesetzt: **Bassin d'Austerlitz** — bis dahin Station 7, zwischen Seine/Notre-Dame und École Keller — wandert direkt hinter Station 2 (Petite Ceinture) und wird zu **Station 3**. Damit stehen jetzt alle drei 12e/13e-Stopps (Charles Péguy, Petite Ceinture, Bassin d'Austerlitz) am Stück am Anfang der Tour, bevor es in den 4e-Cluster geht. Rivoli, Forêt urbaine, Voie Georges Pompidou und Seine bleiben in ihrer bisherigen Reihenfolge, rücken aber von 3–6 auf 4–7. École Keller (8), La Recyclerie (9) und Rue Ferdinand-Flocon (10) bleiben unverändert.

Auf expliziten Wunsch führt die Strecke von Station 3 (Bassin d'Austerlitz, Square Marie-Curie) zu Station 4 (Rivoli) **via Sorbonne Université**: geografisch naheliegend, da Square Marie-Curie direkt neben dem Jussieu-Campus der Sorbonne liegt — ein kurzer Abstecher durchs Quartier Latin, bevor die Route wieder an die Seine trifft. Als Google-Maps-Waypoint "Sorbonne Université, 75005 Paris" ergänzt, im Fliesstext von Station 3 kurz erwähnt.

Nebeneffekt für die Streckenbeurteilung: Die vorher als unsicher markierte Verbindung Bassin d'Austerlitz → Petite Ceinture → École Keller existiert in dieser Form nicht mehr (beide Stationen sind jetzt vor dem 4e-Cluster). Stattdessen entsteht eine **neue, nie eingeschätzte** direkte Verbindung Seine/Notre-Dame (Station 7) → École Keller (Station 8, 4e → 11e) — in der Checkliste oben ergänzt. Die einst als "gut ausgebaut" bekannte Kette Rivoli → Forêt urbaine → Voie Georges Pompidou → Seine bleibt dagegen in ihrer ursprünglichen Reihenfolge erhalten und somit weiterhin gültig.

## Velo-Infrastruktur der ganzen Route geprüft (2026-08-30, nachts)

Auf Wunsch die gesamte Tourführung gegen echte Pariser Fahrradrouten geprüft, nicht nur einzelne Stellen. Kernbefund: Die Tour verläuft über weite Strecken auf den vier grossen strukturierenden Rad-Hauptachsen von Paris (Rivoli Ost-West, Seine-Kais beidseitig, Boulevard Sébastopol/Saint-Michel Nord-Süd, Canal-Saint-Martin-Promenade) sowie auf der Linie v10 des Réseau Vélo Île-de-France (Boulevards des Maréchaux) — deutlich besser abgesichert, als die bisherigen "ungeprüft"-Warnungen vermuten liessen. Details und Einstufung pro Teilstück siehe Checkliste oben (jetzt mit Quellenangaben, Häkchen gesetzt).

Zwei konkrete Korrekturen an der Streckenführung: (1) Station 2→3 (Kellermann→Bassin d'Austerlitz) soll über **Boulevard Vincent-Auriol** laufen, nicht über die naheliegendere, aber laut Anwohner-Radinitiative MDB Paris 13 weiterhin fahrradfeindliche Avenue des Gobelins — als neuer Wegpunkt im Maps-Link ergänzt. (2) Station 7→8 (Seine→École Keller) läuft über **Rue Saint-Antoine → Place de la Bastille → Rue de la Roquette** — der erste Teil hat seit 2017 einen Radweg, der Roquette-Teil ist als "vélorue" laut paris-en-selle.fr (Stand Juni 2026) aber erst im Bau; als neuer Wegpunkt "Place de la Bastille" ergänzt, bleibt aber die einzige noch wirklich unsichere Stelle der ganzen Tour.

Nicht selbst vor Ort getestet, nur über Websuche recherchiert (Presseartikel, Mairie-Seiten, Radinitiativen wie Mieux se Déplacer à Bicyclette und Paris en Selle, sowie die offizielle Réseau-Vélo-Île-de-France-Seite) — keine Garantie für den exakten Zustand am Tourtag, Baustellen ändern sich laufend.

## Quellen

Recherchiert Ende Juli/Anfang August 2026, siehe Chatverlauf für Einzel-Quellen (Ville de Paris, FRANCE 24, Brut, Le Nouvel Obs, INRAE-Kritik an der Miyawaki-Methode via tela-botanica.org/enlargeyourparis.fr, Mairie du 13e zur Petite Ceinture, Bloomberg CityLab und reporterre.net zur Voie Georges Pompidou). Ergänzt am 29./30.08.2026 um Republik, "Au revoir, Paris" (Kolly, 2026), paris.fr/Mairie du 11e/Mairie du 18e zum "rues aux écoles"-Programm, education.gouv.fr zu den Schulen an der Rue Ferdinand-Flocon, sowie paris-blog.org ("Die Petite Ceinture", Teil 1+2, 2020) und die offizielle paris.fr-Seite zu Square Charles Péguy für die neue Station 1 und den Ausbau der Petite-Ceinture-Station. Für die Konnektivitätsfrage (Porte de Choisy) zusätzlich mairie13.paris.fr und petiteceinture.org/ASPCRF (Statusbericht Dezember 2024). Für die Velo-Infrastruktur-Prüfung (30.08.2026) zusätzlich: rerv.fr und Wikipedia zum Réseau Vélo Île-de-France, mdb-idf.org (Mieux se Déplacer à Bicyclette, u. a. zur Avenue des Gobelins und den Boulevards des Maréchaux), mairie11.paris.fr/mairie12.paris.fr zu Boulevard Voltaire und Rue du Faubourg Saint-Antoine, parisenselle.fr zur "vélorue" Rue de la Roquette, cdn.paris.fr (Bauphasen-PDF Boulevard Saint-Michel), mairie10.paris.fr zu Boulevard Magenta, sowie parisjetaime.com zu den vier Pariser Rad-Hauptachsen.
