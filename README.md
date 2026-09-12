# Klima-Velotour Paris

Private Fahrrad-Stadtführung durch Paris (halber Tag, Start am Hotel PiaPia + 10 Stationen, plus eine reine Info-Erwähnung ohne Halt) zu Klimaschutz, Klimaanpassung und nachhaltigem Wirtschaften — für eine Reise Anfang September 2026.

`index.html` ist self-contained bis auf zwei lokale Bilder (kein Build-Schritt, keine externen Abhängigkeiten ausser YouTube-Embeds und den beiden Station-9-Fotos `flocon_before.png`/`flocon_after.png`) und läuft direkt im Handy-Browser. Dazu kommen zwei separate Leaflet/OpenStreetMap-Karten (brauchen Internet für Kartenkacheln), beide mit `index.html` gegenseitig verlinkt: `karte-vegan-bier.html` (vegane Restaurants und Bierlokale) und `karte-uebersicht.html` (alle 10 Stationen + Start/Ausklang auf einer Karte, mit verbindender Linie und Popup-Links zurück zur jeweiligen Station).

> **Zur Stationen-Nummerierung**: Die Nummern haben sich über viele Sessions immer wieder verschoben. **Aktueller Stand (2026-09-12, mehrfach am selben Tag geändert):** 1 Tour de la Biodiversité, 2 Petite Ceinture (13e), 3 École Damesme, 4 Bassin d'Austerlitz, 5 Rue de Rivoli, 6 Forêt urbaine Hôtel de Ville, 7 Voie Georges Pompidou, 8 Seine bei Notre-Dame, 9 Rue Ferdinand-Flocon, 10 La Recyclerie, danach Ausklang "Pétanque et Bière" bei BarOurcq. Frühere Stände hatten zusätzlich oder stattdessen: Square Charles Péguy (früher Station 1, ganz gestrichen), École Keller (früher Station 8, ganz gestrichen), Bassin d'Austerlitz zeitweise ganz ersetzt durch die Tour de la Biodiversité (beide sind jetzt getrennte Stationen), sowie einen Ausklang "Vegan & Bier" statt "Pétanque et Bière". Die vollständige Historie steht in den datierten Changelog-Abschnitten weiter unten — diese verwenden jeweils die zu ihrem Zeitpunkt gültige Nummerierung, nicht die aktuelle. Nur Checkliste, Struktur-Abschnitt und Überblick oben sind auf dem aktuellen Stand.

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

- [ ] **Petite Ceinture 13e (Station 2)**: vermutlich nicht befahrbar innerhalb des Jardins — Velos bei der Place Jean Delay abstellen, rund 200 m zu Fuss über die Rue de l'Interne-Loeb zum Eingang an der Rue Damesme
- [ ] **La Recyclerie (Station 10)**: Öffnungszeiten/Programm (Restaurant, Ferme, Werkstatt) vorher auf larecyclerie.com checken, nicht alles ist immer gleichzeitig zugänglich
- [ ] Alle 7 eingebetteten Videos einmal kurz antesten (sind über die YouTube-oEmbed-API als existierend/einbettbar verifiziert, aber nie selbst abgespielt worden)
- [ ] Alle 7 eingebetteten Vorher/Nachher- und Einzelfotos einmal laden lassen — beim Testen wurde eines (Wikimedia Commons, Station 6 "Nachher") wiederholt mit HTTP 429 (Rate-Limit) blockiert; der Bildinhalt selbst wurde vorher visuell verifiziert, das Laden im Browser sollte aber trotzdem einmal bestätigt werden
- [ ] Mobile Daten: die Videos brauchen Internet — Route funktioniert aber auch ohne, alle Kerninhalte stehen als Text auf der Seite
- [ ] Bike-Route vorher einmal am Rechner durchklicken (Link "Ganze Route in Google Maps öffnen" oben auf der Seite)
- [ ] **Velo-Infrastruktur, Stand 2026-09-12** (die ursprüngliche Prüfung vom 2026-08-30 bezog sich auf eine seither mehrfach umgebaute Stationsreihenfolge und ist nicht mehr zuverlässig, siehe Nummerierungs-Hinweis ganz oben; hier neu zusammengefasst, teils nicht neu recherchiert):
  - Hotel → Station 1 (Tour de la Biodiversité, 20e→13e) und Station 1→2 (Tour de la Biodiversité → Petite Ceinture, quer durch den 13e von Ost nach West): beide neu in dieser Reihenfolge und nicht im Detail geprüft — vor Ort live navigieren.
  - Station 2→3 (Petite Ceinture → École Damesme): dicht beieinander im selben 13e-Cluster (Kellermann/Damesme), kein Umweg.
  - Station 2/3→4 (weiter Richtung Bassin d'Austerlitz): lieber über Boulevard Vincent-Auriol als über die Avenue des Gobelins — Letztere gilt laut Anwohner-Radinitiative (MDB Paris 13) weiterhin als fahrradfeindlich.
  - Station 4→5 (Bassin d'Austerlitz → Rivoli, via Sorbonne/Quartier Latin): **gut** — Boulevard Saint-Michel hat dort einen frisch gebauten, geschützten Zweirichtungs-Radweg (Bauphasen-PDF der Stadt Paris), eine der vier grossen Nord-Süd-Radachsen von Paris.
  - Station 5–8 (Rivoli → Forêt urbaine → Voie Georges Pompidou → Seine): **gut**, wie bisher — liegt auf den beiden anderen der vier Pariser Rad-Hauptachsen (Rivoli Ost-West, Seine-Kais beidseitig).
  - Station 8→9 (Seine → Rue Ferdinand-Flocon, 4e→18e): vom Nutzer korrigierte Wegführung (2026-09-12) über Place de la Bastille, Boulevard Richard-Lenoir und Rue des Récollets — vorgegeben, nicht selbst mit Quellen geprüft.
  - Station 9→10 (Rue Ferdinand-Flocon → La Recyclerie): kurz, beide im selben 18e-Cluster rund um Ornano/Jules Joffrin/Château Rouge — Distanz grob geschätzt, nicht kartografisch nachgemessen.
  - Station 10 → Ausklang (La Recyclerie, 18e → BarOurcq, 19e, Canal de l'Ourcq): vom Nutzer korrigierte Wegführung (2026-09-12) über Boulevard Barbès und Boulevard de la Chapelle — vorgegeben, nicht selbst mit Quellen geprüft. Grösster Einzelsprung der ganzen Tour, rund 15–20 Minuten Velo.
  
  Der Maps-Link nimmt trotzdem irgendeine von Google vorgeschlagene Route — generell wegen Baustellen am Tourtag live navigieren.
- [x] **Vélib'-Station am Hotel verifiziert (2026-08-28)**: heisst "Pyrénées - Avron", liegt laut offiziellem GBFS-Live-Feed (velib-metropole-opendata.smovengo.cloud) nur ~5 m von 73 Rue des Pyrénées entfernt, 32 Docks bestätigt, Station ist installiert und aktiv (`is_installed`/`is_renting` = 1). Bleibt trotzdem sinnvoll, die Radverfügbarkeit kurz vor Abfahrt in der App zu checken — die schwankt stündlich (beim Test: 0 Räder, aber 32 freie Docks).
- [ ] **Neu, Station 6 (Voie Georges Pompidou)**: Kartenpunkt "Pont Louis-Philippe" ist eine Näherung für den Startpunkt der autofreien Uferpromenade, nicht selbst vor Ort geprüft — sollte aber unkritisch sein, da die ganze Strecke Hôtel de Ville → Pont Marie ohnehin am Wasser entlangführt.
- [ ] Montmartre/Sacré-Cœur ist bewusst nicht mehr Teil der Route (Rue de Ravignan bis 13,6% Steigung, offiziell eine der zwei steilsten Veloachsen von Paris) — falls gewünscht, Velos am Fuss abschliessen und zu Fuss hoch

## Struktur

Jede Station: Kartenlink → Kontext-Text → Video oder Vorher/Nachher-Fotos (wo vorhanden). Themen farblich codiert: grün = Klimaschutz, blau = Klimaanpassung, orange = nachhaltiges Wirtschaften. Seit 2026-08-30 gibt es an zwei Stellen gezielt gesetzte Diskussionsboxen (türkis, "💬") zu Gentrifizierung/Mietsteigerung und der "Ist es genug?"-Frage — auf expliziten Wunsch, als bewusste Ausnahme von der vorherigen Entscheidung gegen Diskussionsfragen-Prompts. Die Gentrifizierungs-Box ("Grün macht teuer") sass ursprünglich im Hintergrund-Abschnitt, wurde am 2026-09-12 aber zu Station 2 (Petite Ceinture) verschoben — dort ist auf der Tour tatsächlich Zeit zum Diskutieren, im Hintergrund-Abschnitt (noch vor der Abfahrt) weniger. Die Schlussdiskussion "Ist es genug?" bleibt im Ausklang. Eine zwischenzeitlich bei École Keller zusätzlich gesetzte "Geprüft"-Box und Diskussionsbox wurden noch am selben Tag wieder entfernt — ihr Inhalt (Rue Keller ist keine "rue aux écoles") lebte danach implizit im Kontrast zur (damaligen) Station 10 weiter. Die École-Keller-Station selbst wurde am 2026-09-12 (nach der Reise) ganz gestrichen; die neue Station "École Damesme" wurde zunächst mit demselben "nicht jede Schulstrasse ist offiziell gelistet"-Gedanken geschrieben, bis sich noch am selben Tag herausstellte, dass Rue Damesme entgegen der ursprünglichen Prüfung (Mairie du 13e) laut offizieller Stadt-Paris-Liste ("57 nouvelles rues aux écoles") sehr wohl gelistet ist — der Text wurde entsprechend korrigiert (siehe Abschnitt "École Damesme-Korrektur" weiter unten). Drei weitere orange "Zum Nachdenken"-Boxen (Miyawaki-Kritik, Voie-Georges-Pompidou-Kontroverse, Montmartre-Hinweis) wurden ebenfalls auf Wunsch entfernt; übrig sind nur noch die Hintergrund-Box "Wer zahlt für die Verkehrswende?" und die "Ungeprüft"-Box im Start-Abschnitt.

Vorher/Nachher-Fotos (Stationen 5 Rivoli, 6 Forêt urbaine, 7 Voie Georges Pompidou, 9 Rue Ferdinand-Flocon) stammen aus frei lizenzierten Quellen (Wikimedia Commons, CC BY/CC BY-SA) oder von der Stadt Paris (offizielle Pressefotos) — keine Bloomberg/Getty-Bilder, da deren Fotos redaktionell lizenziert sind. Für die Stationen 1 (Tour de la Biodiversité, reiner Kurzhalt ohne Video/Foto), 2 (Petite Ceinture 13e), 3 (École Damesme, reiner Kurzhalt ohne Video/Foto), 4 (Bassin d'Austerlitz), 10 (La Recyclerie) und die Info-Erwähnung La Caverne wurde kein brauchbares freies Vorher/Nachher-Material gefunden bzw. bewusst keines gesucht — dort bleibt es bei Text/Video bzw. reinem Text.

Station 9 (Rue Ferdinand-Flocon) ist ein Sonderfall: Die beiden Bilder (`flocon_before.png`, `flocon_after.png`) liegen als lokale Dateien im Projektordner statt extern verlinkt zu sein (dadurch beim `git add` und Pages-Deploy nicht vergessen — `.gitignore` schliesst nur `*.pdf` aus, PNGs sind nicht betroffen). Das Vorher-Bild ist ein Google-Street-View-Screenshot inkl. sichtbarer Bedienelemente (Kompass, Zoom, Mini-Karte unten links) — optisch nicht so sauber wie die anderen Vorher-Bilder, aber vom Nutzer bewusst so bereitgestellt. Das Nachher-Bild ist ein offizielles Ville-de-Paris-Pressefoto (Guillaume Bontemps).

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

## Station 3 ersetzt: Bassin d'Austerlitz → Tour de la Biodiversité (2026-09-12, nach der Reise)

Auf Wunsch nach der eigentlichen Tour geändert (Revision für eine mögliche Wiederverwendung der Seite): Station 3 (Bassin d'Austerlitz, unterirdisches Regenwasser-Rückhaltebecken unter dem Square Marie-Curie) gestrichen, ersetzt durch einen bewusst kurzen Halt an der **Tour de la Biodiversité** (auch Tour M6B2 genannt), 1 Rue Albert Einstein, 75013 Paris — ganz in der Nähe, ebenfalls im Quartier Paris Rive Gauche/13e. 17-stöckiger Wohnturm von Architekt Édouard François: die Fassade ist mit röhrenartigen Elementen verkleidet, die wie Felsspalten funktionieren und in der Region gesammelte Wildpflanzen-Samen verwurzeln lassen — die Vegetation soll sich über Jahre von selbst über den Turm und in die Umgebung ausbreiten.

Auf ausdrücklichen Wunsch **ohne grosse Beschreibung**: kein Video, kein Vorher/Nachher-Foto, nur ein kurzer Absatz — die Station ist als reiner "kurz hinschauen"-Halt gedacht, kein inhaltlicher Schwerpunkt wie die anderen Stationen.

Folgeänderungen:
- Tag von "Klimaanpassung" (blau) auf "Klimaschutz" (grün) geändert, konsistent mit den anderen beiden Petite-Ceinture/Biodiversitäts-Stationen (1 und 2).
- Waypoint im "Ganze Route"-Maps-Link von "Square Marie Curie, 75013 Paris" auf "1 Rue Albert Einstein, 75013 Paris" geändert; der Zusatz-Waypoint "Sorbonne Université, 75005 Paris" entfernt, da der bisherige Abstecher via Quartier Latin/Sorbonne spezifisch mit der Nähe von Bassin d'Austerlitz zum Jussieu-Campus begründet war und auf die neue Station nicht mehr zutrifft.
- Die im August geprüfte Velo-Infrastruktur-Aussage zu Boulevard Saint-Michel (Station 3→4) galt für den Sorbonne-Abstecher und ist damit hinfällig — als "nicht mehr im Detail geprüft" markiert statt stillschweigend stehen gelassen.
- Überblick-Text (Start-Abschnitt) und Inhaltsverzeichnis entsprechend angepasst.
- Nicht angepasst, da rein historisch: die datierten Changelog-Einträge weiter unten, die sich auf die alte Reihenfolge/Bassin d'Austerlitz beziehen, behalten bewusst den zum jeweiligen Zeitpunkt gültigen Stand (siehe Nummerierungs-Hinweis ganz oben).

**Nachtrag, selben Tag:** Der Wegpunkt "Boulevard Vincent Auriol, 75013 Paris" (Station 2→3) im "Ganze Route"-Maps-Link entfernt — die unpräzise Adresse (ohne Hausnummer) liess Google Maps auf einen Punkt hinter der Métro-Station Nationale geocodieren, der für die Wegführung keinen Sinn ergab. Die Empfehlung, auf diesem Abschnitt Boulevard Vincent-Auriol statt der fahrradfeindlicheren Avenue des Gobelins zu nehmen, bleibt im Text bestehen, ist aber nicht mehr als Wegpunkt erzwungen — vor Ort selbst darauf achten.

**Nachtrag, selben Tag (2):** Halt-Standort von Station 2 (Petite Ceinture 13e) präzisiert: statt "34 Boulevard Kellermann" jetzt exakt Place Jean Delay (48.8233160055962, 2.354307815457442) — Velos dort abstellen, dann rund 200 m zu Fuss über die Rue de l'Interne-Loeb zum eigentlichen Eingang an der Rue Damesme/Jardin de la Poterne des Peupliers. Map-Button der Station und Wegpunkt im "Ganze Route"-Link entsprechend auf die Koordinaten geändert.

## École Keller gestrichen, neue Station 3: École Damesme (2026-09-12, nach der Reise)

Station "École Keller — Cour Oasis" (zuletzt Station 8, 4 Rue Keller, 75011 Paris) auf Wunsch komplett gestrichen: begrünter Schulhof, 15-Minuten-Stadt-Bogen und der "rues aux écoles"-Exkurs sind damit aus der Tour raus.

Dafür neue Station direkt nach der Petite Ceinture (Station 2) eingefügt, an den Koordinaten 48.82502321449237, 2.355381398187204 — das ist die **École élémentaire Damesme**, 5 Rue Damesme, unmittelbar neben dem Petite-Ceinture-Eingang. Vor dem Schreiben geprüft: laut offizieller Liste der Mairie du 13e ist die Rue Damesme **nicht** als "rue aux écoles" gelistet (gleicher Befund wie seinerzeit bei Rue Keller). Auf Wunsch ehrlich so benannt: die neue Station 3 macht genau diesen Punkt zum Inhalt (gewöhnliche Schulstrasse, kein Autoverkehrsverbot) und verweist auf die echte, offiziell gelistete "rue aux écoles" bei Station 10 (Rue Ferdinand-Flocon) — derselbe Kontrast wie zuvor bei École Keller, jetzt nur früher in der Tour platziert und ohne Bezug auf eine gelöschte Stationsnummer.

Nummern-Kaskade dadurch: durch die Einfügung rutschten die alten Stationen 3–7 (Tour de la Biodiversité, Rivoli, Forêt urbaine, Voie Georges Pompidou, Seine) um je eins auf 4–8; durch die gleichzeitige Streichung der alten Station 8 (École Keller) rutschten die alten Stationen 9–10 (La Recyclerie, Rue Ferdinand-Flocon) per saldo wieder auf ihre ursprüngliche Nummer zurück. Total bleiben es zehn Stationen.

Folgeänderungen:
- Tag der neuen Station 3: "Klimaanpassung" (blau), passend zum Thema Schulstrassen/Verkehrsberuhigung (wie bei Station 10).
- Station 10 (Rue Ferdinand-Flocon): Vergleichssatz "Anders als die Rue Keller bei Station 8..." entfernt, da er eine jetzt gelöschte Station beim Namen nannte. Beschreibt die Strasse jetzt eigenständig.
- Wegpunkt im "Ganze Route"-Maps-Link: "4 Rue Keller, 75011 Paris" entfernt, neuer Wegpunkt für die Koordinaten der École Damesme eingefügt (zwischen Petite Ceinture und Tour de la Biodiversité).
- **Zusätzlich entfernt:** der Wegpunkt "Place de la Bastille, 75004 Paris" — der sass nur dort, um die Strecke Seine → École Keller über die Rue-de-la-Roquette-"vélorue" zu führen. Ohne École-Keller-Halt ergibt der Umweg über Bastille/11e keinen Sinn mehr; die Strecke Seine → La Recyclerie läuft jetzt direkter, ist damit aber auch **nicht mehr im Detail auf Velo-Infrastruktur geprüft** (die früher recherchierten Befunde zu Rue Saint-Antoine/Bastille/Roquette und Boulevard Magenta bezogen sich auf den alten Umweg über College Keller und treffen auf die neue, direktere Strecke nicht mehr zu).
- Überblick-Text (Start-Abschnitt): "12e und 13e"-Satz um École Damesme ergänzt, Erwähnung des 11e (galt nur für École Keller) entfernt.
- Struktur-Abschnitt und Vorher/Nachher-Foto-Liste in diesem README entsprechend auf die neue Nummerierung angepasst.
- Nicht angepasst, da rein historisch: ältere Changelog-Einträge, die sich auf die alte Nummerierung/École Keller beziehen (siehe Nummerierungs-Hinweis ganz oben).

## Ausklang verlegt: Vegan & Bier → Pétanque et Bière bei BarOurcq (2026-09-12, selber Tag)

Auf Wunsch Stationen 9 und 10 getauscht: **Rue Ferdinand-Flocon ist jetzt Station 9**, **La Recyclerie jetzt Station 10** — damit bleibt La Recyclerie weiterhin die letzte tatsächlich angefahrene Station direkt vor dem Ausklang, nur die beiden Stationen davor haben die Plätze getauscht. Die beiden liegen ohnehin im selben 18e-Cluster (rund um Ornano/Jules Joffrin), der Tausch ändert an der grossen Linie der Route nichts.

Der Ausklang selbst wurde komplett ersetzt: statt "Vegan & Bier" (Urban Greener + Le Supercoin, beide nahe Rue Ferdinand-Flocon im 18e) jetzt **"Pétanque et Bière" bei BarOurcq**, 68 Quai de la Loire, 75019 Paris — direkt am Canal de l'Ourcq. Verifiziert: gratis Boule-Kugeln und Liegestühle für Konsumierende, bodenständige Bistroküche (Fish and Chips, Burger, Charcuterie), Öffnungszeiten Mi–So ab 15 Uhr (Quelle: Bar-Verzeichnisse/Tripadvisor, nicht offizielle Website — vor Ort nochmals prüfen).

Geografische Konsequenz, bewusst in Kauf genommen: BarOurcq liegt rund 4–5 km von La Recyclerie entfernt (19e statt 18e) — mit Abstand der grösste Einzelsprung der ganzen Tour, gegenüber vorher (Ausklang-Cafés nur ~1 km von Station 10 entfernt). Nicht kartografisch nachgemessen, als eigener Checklisten-Punkt oben ergänzt.

Folgeänderungen:
- Ziel-Adresse im "Ganze Route"-Maps-Link von "Place Jules Joffrin, 75018 Paris" auf "68 Quai de la Loire, 75019 Paris" (BarOurcq) geändert; Wegpunkt-Reihenfolge für Stationen 9/10 getauscht.
- TOC, Stationstitel/-nummern (h2, id, next-links) für die neuen Stationen 9 und 10 entsprechend getauscht.
- Cross-Referenzen auf die alte Nummerierung korrigiert: Start-Abschnitt ("...später bei Station 9" → "...Station 10"), Station 1 ("bei Station 9 baut sie es professionell zum Tiers-Lieu um" → "Station 10"), Station 3/École Damesme ("Beispiel folgt später bei Station 10" → "Station 9").
- Fussnote/Footer-Datum auf 2026-09-12 aktualisiert.
- Die "Schlussdiskussion: Ist es genug?"-Box im Ausklang bleibt inhaltlich unverändert — sie ist unabhängig vom konkreten Lokal.
- Nicht angepasst: `karte-vegan-bier.html` (die separate Vegan/Bier-Karte) — BarOurcq wurde dort nicht ergänzt, da nicht explizit gewünscht.

## Charles Péguy gestrichen, Bassin d'Austerlitz wieder eingefügt (2026-09-12, selber Tag, Korrektur)

Rückmeldung: Square Charles Péguy (damals Station 1) hätte gemäss dem Nutzer schon früher gestrichen werden sollen — das ergibt sich aus dieser Konversation nicht, wurde aber so umgesetzt. Gleichzeitig sollte Bassin d'Austerlitz (das am selben Tag zuvor explizit durch die Tour de la Biodiversité ersetzt worden war) **zusätzlich** zurückkommen, nicht die Tour de la Biodiversité ersetzen — auf Nachfrage geklärt.

**Charles Péguy (Gemeinschaftsgärten, 21 Rue Rottembourg, 75012) komplett gestrichen.** Petite Ceinture rückt dadurch von Station 2 auf Station 1 vor und eröffnet die Tour jetzt direkt. Der "drei Zustände der Petite Ceinture"-Bogen (Eigenregie bei Charles Péguy / Natur überlassen bei Petite Ceinture / professionell bei La Recyclerie) ist damit auf zwei Zustände geschrumpft; der Verweis darauf in La Recycleries Text wurde entsprechend gekürzt und die Stationsnummer korrigiert (Petite Ceinture ist jetzt 1, nicht mehr 2).

**Bassin d'Austerlitz als neue Station 4 wieder eingefügt**, mit dem ursprünglichen Inhalt (Regenwasser-Rückhaltebecken unter dem Square Marie-Curie, Video "la cathédrale souterraine") und dem ursprünglichen Sorbonne/Quartier-Latin-Übergang zu Rivoli — beides war beim Tausch gegen die Tour de la Biodiversité entfernt worden und ist jetzt wieder gültig, da Bassin d'Austerlitz geografisch sinnvoll direkt nach der Tour de la Biodiversité und vor Rivoli passt (Kellermann → École Damesme → Tour de la Biodiversité → Bassin d'Austerlitz/Jussieu → via Sorbonne → Rivoli, ohne grossen Umweg).

Numerierungs-Kaskade dadurch (Netto-Effekt: weiterhin zehn Stationen, minus Charles Péguy, plus Bassin d'Austerlitz):

| Alt (vor dieser Korrektur) | Neu |
|---|---|
| 1 Charles Péguy | *gestrichen* |
| 2 Petite Ceinture | 1 Petite Ceinture |
| 3 École Damesme | 2 École Damesme |
| 4 Tour de la Biodiversité | 3 Tour de la Biodiversité |
| *(nicht vorhanden)* | 4 Bassin d'Austerlitz *(neu eingefügt)* |
| 5–10 (Rivoli … La Recyclerie) | unverändert 5–10 |

Praktische Konsequenz: Stationen 5 bis 10 (Rivoli, Forêt urbaine, Voie Georges Pompidou, Seine, Rue Ferdinand-Flocon, La Recyclerie) behalten zufällig genau ihre bisherigen Nummern — nur die ersten vier Plätze haben sich geändert.

Folgeänderungen:
- Wegpunkt "21 Rue Rottembourg, 75012 Paris" (Charles Péguy) aus dem "Ganze Route"-Maps-Link entfernt; Wegpunkte "Square Marie Curie, 75013 Paris" und "Sorbonne Université, 75005 Paris" (Bassin d'Austerlitz + Sorbonne-Abstecher) wieder eingefügt, an der geografisch passenden Stelle zwischen Tour de la Biodiversité und Rivoli.
- Start-Abschnitt: "12e und 13e" auf nur noch "13e" korrigiert (Charles Péguy/Rottembourg war der einzige 12e-Punkt), Bassin d'Austerlitz zur Aufzählung der 13e-Stationen ergänzt.
- Velo-Infrastruktur-Box (Start-Abschnitt und README-Checkliste): komplett neu zusammengefasst, da mehrere Segment-Grenzen sich verschoben haben (Hotel→Station 1 jetzt ungeprüft statt vormals Charles-Péguy→Petite-Ceinture-Achse; Boulevard-Saint-Michel-Befund für Bassin d'Austerlitz→Rivoli wieder gültig).
- Nummerierungs-Hinweis ganz oben komplett neu geschrieben (statt fortlaufend anzuwachsen): nennt jetzt direkt den aktuellen Stand plus eine Kurzzusammenfassung früherer Zwischenstände, statt jede einzelne Zwischenverschiebung im Fliesstext nachzuerzählen.
- Nicht angepasst, da rein historisch: ältere Changelog-Einträge zu Charles Péguy und Bassin d'Austerlitz (z. B. "Petite Ceinture ausgebaut + neue Station 1: Square Charles Péguy", 2026-08-30) — sie beschreiben, was zum jeweiligen Zeitpunkt eingeführt wurde, nicht den heutigen Stand.

## Erste drei 13e-Stationen umsortiert (2026-09-12, selber Tag)

Auf Wunsch die Reihenfolge der ersten drei Stationen geändert: **Tour de la Biodiversité rückt auf Station 1 vor** (direkt ab dem Hotel), gefolgt von **Petite Ceinture (Station 2)** und **École Damesme (Station 3)**. Bassin d'Austerlitz bleibt unverändert Station 4, ebenso Stationen 5–10 danach.

| Alt | Neu |
|---|---|
| 1 Petite Ceinture | 2 Petite Ceinture |
| 2 École Damesme | 3 École Damesme |
| 3 Tour de la Biodiversité | 1 Tour de la Biodiversité |
| 4 Bassin d'Austerlitz | 4 Bassin d'Austerlitz (unverändert) |
| 5–10 | unverändert |

Geografisch bedeutet das: Hotel (20e) → Tour de la Biodiversité (13e, Ost, nahe BNF) → Petite Ceinture/École Damesme (13e, West, Kellermann/Damesme) → Bassin d'Austerlitz (13e, Nord, Jussieu) → weiter wie bisher via Sorbonne nach Rivoli. Damit quert die Route den 13e einmal zusätzlich von Ost nach West (Tour de la Biodiversité → Petite Ceinture) — spürbar, aber deutlich kleiner als der Seine-Umweg, der bei einem zuvor diskutierten, nicht umgesetzten Vorschlag entstanden wäre (Rivoli auf Platz 3 vorziehen, siehe vorheriger Diskussionspunkt in dieser Session, wurde verworfen).

Folgeänderungen:
- TOC, Wegpunkt-Reihenfolge im "Ganze Route"-Maps-Link (Tour de la Biodiversité jetzt vor Petite Ceinture/École Damesme) angepasst.
- Tour de la Biodiversité: kurze Eröffnungsformulierung ergänzt ("Der erste Halt, gleich zu Beginn nur ein kurzer..."), da sie jetzt tatsächlich die erste Station ist. Bleibt bewusst minimal (kein Video/Foto), wie ursprünglich gewünscht.
- Petite Ceinture: die frühere Eröffnungsformulierung ("Der erste Halt zeigt gleich...") entfernt, da sie nicht mehr die erste Station ist.
- La Recyclerie: Verweis "dieselbe stillgelegte Ringbahn wie bei Station 1" auf "Station 2" korrigiert (Petite Ceinture).
- Hintergrund-Abschnitt: Verweis "rues aux écoles, mehr dazu bei Station 8" (ein Überbleibsel von vor der École-Keller-Streichung, damals übersehen) korrigiert auf "Station 3 und 9".
- Velo-Infrastruktur-Box (Start-Abschnitt und README-Checkliste) neu zusammengefasst: Hotel→Station 1 und Station 1→2 sind jetzt die ungeprüften, neuen Abschnitte; die Vincent-Auriol-Empfehlung gilt jetzt für "Station 2/3→4".
- Nummerierungs-Hinweis ganz oben aktualisiert (Tour de la Biodiversité jetzt an erster Stelle).

## École Damesme-Korrektur: doch eine offizielle "rue aux écoles" (2026-09-12, selber Tag)

**Faktenkorrektur.** Die Prüfung für Station 3 (École Damesme) hatte sich auf die Seite `mairie13.paris.fr/pages/rues-aux-ecoles-13083` gestützt, die Rue Damesme nicht listete — daraus wurde geschlossen, die Strasse sei keine offizielle "rue aux écoles" (analog zum echten Befund bei Rue Keller/11e). Der Nutzer hat die vollständigere, offizielle Stadt-Paris-Quelle nachgereicht: `paris.fr/pages/57-nouvelles-rues-aux-ecoles-dans-paris-8197#arrondissement-13-vlx72` (verifiziert per Abruf) — dort ist **Rue Damesme** explizit für den 13e gelistet, Teil einer neueren Welle von 57 zusätzlichen Strassen. Die Mairie-du-13e-Seite war schlicht nicht vollständig/aktuell für diese Erweiterungswelle. Lehre: eine einzelne Bezirksseite reicht nicht als abschliessende Quelle für "ist X offiziell gelistet" — wo verfügbar, die zentrale Stadt-Paris-Übersichtsseite zuerst prüfen.

**Textänderung Station 3 (École Damesme):** von "ehrlicher Realitätscheck, nicht gelistet" umgeschrieben zu "tatsächlich offiziell gelistet, Teil der 57er-Welle". Die allgemeinen Programm-Fakten (>300 Strassen seit 2020, rund 100 davon entsiegelt/bepflanzt, Stand September 2025 gut die Hälfte aller Vorschulen/Grundschulen) wurden von Station 9 hierher vorgezogen, da Station 3 jetzt chronologisch die erste "rue aux écoles" der Tour ist.

**Textkürzung Station 9 (Rue Ferdinand-Flocon):** auf Wunsch gekürzt, da die allgemeine Programm-Einführung jetzt bei Station 3 steht. Bleibt: autofrei seit 1. September 2021, École maternelle (Nr. 3) und École élémentaire (Nr. 5) direkt an der Strasse, Sacré-Cœur-Blick, Bezug zur Republik-Reportage. Vorher/Nachher-Fotos (`flocon_before.png`/`flocon_after.png`) unverändert beibehalten, wie explizit gewünscht.

Folgeänderungen:
- TOC-Eintrag Station 3 von "eine ganz gewöhnliche Schulstrasse" auf "eine von über 300 rues aux écoles" korrigiert.
- Struktur-Abschnitt oben entsprechend präzisiert (Verweis auf diesen Korrektur-Abschnitt ergänzt statt den überholten Kontrast-Gedanken fortzuschreiben).
- Nicht angepasst, da rein historisch: der Abschnitt "École Keller gestrichen, neue Station 3: École Damesme" weiter oben beschreibt bewusst den (mittlerweile überholten) Stand zum Zeitpunkt seiner Entstehung, nicht den heutigen.

## Diskussionsbox "Grün macht teuer" zu Station 2 verschoben (2026-09-12, selber Tag)

Auf Wunsch die Diskussionsbox "💬 Diskussion: Grün macht teuer" (Gentrifizierung/Mietsteigerung, Republik-Zitate, drei Diskussionsfragen) vom Hintergrund-Abschnitt zu **Station 2 (Petite Ceinture)** verschoben — Begründung: dort hat die Gruppe tatsächlich Zeit zum Diskutieren, im Hintergrund-Abschnitt (noch am Hotel, vor der Abfahrt) eher nicht. Inhalt unverändert übernommen, nur die Verortung geändert; der Verweis "mehr dazu bei Station 3 und 9" im Boxtext bleibt gültig, unabhängig vom eigenen Standort der Box.

Der Hintergrund-Abschnitt behält seine übrigen Inhalte (Zitate, Chart, Gelbwesten-Vergleichspunkt, Leselinks) unverändert; nur die Box selbst wurde entfernt. Die Ausklang-Box "Ist es genug?" bleibt unverändert am Schluss der Tour.

Folgeänderung: Struktur-Abschnitt oben präzisiert (Box sitzt jetzt bei Station 2, nicht mehr im Hintergrund).

## Routenkorrektur ab Pont Marie (2026-09-12, selber Tag)

Auf Rückmeldung des Nutzers ("stimmt nicht") die Google-Maps-Wegführung ab Pont Marie (Station 8, Seine) korrigiert. Zwei Segmente betroffen:

**Station 8→9 (Seine → Rue Ferdinand-Flocon):** neuer Wegpunktzug über Place de la Bastille, Boulevard Richard-Lenoir und Rue des Récollets — vom Nutzer vorgegeben, als Wegpunkte im "Ganze Route"-Link ergänzt (`Place de la Bastille, 75011 Paris`, `Boulevard Richard-Lenoir, 75011 Paris`, `Rue des Récollets, 75010 Paris`).

**Station 10→Ausklang (La Recyclerie → BarOurcq):** neuer Wegpunktzug über Boulevard Barbès und Boulevard de la Chapelle — ebenfalls vom Nutzer vorgegeben, als Wegpunkte ergänzt (`Boulevard Barbès, 75018 Paris`, `Boulevard de la Chapelle, 75018 Paris`), platziert nach dem bestehenden Wegpunkt "83 Boulevard Ornano" (La Recyclerie) und vor dem Zielpunkt BarOurcq.

Beide Korrekturen sind vom Nutzer vor Ort/aus Ortskenntnis vorgegeben, nicht zusätzlich mit Websuche verifiziert — Checkliste und Start-Abschnitt entsprechend als "vorgegeben, nicht selbst geprüft" markiert statt der vorherigen unspezifischen "nicht im Detail geprüft"-Formulierung.

Folgeänderungen:
- Velo-Infrastruktur-Box im Start-Abschnitt (`index.html`) und Checkliste hier aktualisiert.
- Kein Stationswechsel, keine Umnummerierung — nur die Google-Maps-Wegpunkte zwischen bestehenden Stationen geändert.

## "Ganze Route"-Link durch Einzelstrecken pro Etappe ersetzt (2026-09-12, selber Tag, Korrektur)

**Ursache gefunden:** der Nutzer meldete "wird nicht korrekt abgebildet" für den grossen "Ganze Route"-Link. Recherche ergab: Googles `maps/dir/?api=1`-URL-Schema erlaubt laut offizieller Doku nur **9 Wegpunkte am Rechner und 3 auf dem Handy** zusätzlich zu Start/Ziel. Der bisherige Link hatte nach den heutigen Korrekturen 16 Wegpunkte — weit über beiden Limits, insbesondere für das Handy, auf dem diese Seite laut eigener Beschreibung ("läuft direkt im Handy-Browser") primär genutzt wird. Die vorherigen Änderungen an diesem Link (Wegpunkte hinzufügen/entfernen für Bassin d'Austerlitz, École Damesme, Barbès/Chapelle usw.) waren also von Anfang an auf ein grundsätzlich nicht tragfähiges Format aufgesattelt — das hätte früher auffallen sollen.

**Lösung:** der einzelne "Ganze Route"-Button im Überblick-Abschnitt entfernt, ersetzt durch eine kurze Erklärung. Stattdessen bekommt **jeder Übergang zwischen zwei Stationen (11 insgesamt: Hotel→1 bis Station 10→Ausklang) einen eigenen kleinen "🚴 Strecke zur nächsten Station"-Link** (auf Wunsch so benannt statt "Strecke hierher"), platziert direkt vor dem jeweiligen "Weiter zu Station …"-Pfeil. Jede Einzelstrecke hat höchstens 3 Wegpunkte (die meisten 0–1), bleibt also auch auf dem Handy zuverlässig innerhalb des Limits:

| Übergang | Wegpunkte |
|---|---|
| Hotel → 1 | keine |
| 1 → 2, 2 → 3 | keine |
| 3 → 4 | Boulevard Vincent-Auriol |
| 4 → 5 | Sorbonne Université |
| 5 → 6, 6 → 7, 7 → 8 | keine |
| 8 → 9 | Place de la Bastille, Boulevard Richard-Lenoir, Rue des Récollets (3, Handy-Maximum) |
| 9 → 10 | keine |
| 10 → Ausklang | Boulevard Barbès, Boulevard de la Chapelle |

Jede Station behält zusätzlich ihren eigenen, wegpunktfreien "📍 Auf Google Maps öffnen"-Pin-Link (unverändert, war nie vom Limit betroffen).

Folgeänderungen:
- Überblick-Abschnitt: Route-Button entfernt, durch Hinweistext auf die neuen Einzelstrecken-Links ersetzt.
- Lehre für künftige Änderungen: Wegpunkte nie mehr in einen einzigen "Ganze Route"-Link häufen — ab jetzt grundsätzlich pro Etappe verlinken.

## Neue Übersichtskarte ergänzt (2026-09-12, selber Tag)

Auf Wunsch ("zu Beginn möchte ich eine Übersicht der ganzen Strecke") eine dritte Seite `karte-uebersicht.html` gebaut, nach demselben Leaflet/OpenStreetMap-Muster wie `karte-vegan-bier.html`: alle 10 Stationen plus Start (Hotel) und Ausklang (BarOurcq) als nummerierte, farbcodierte Marker (grün/blau/orange nach Themen-Tag, grau für Start/Ziel), verbunden durch eine gestrichelte Linie in Tour-Reihenfolge, damit die grobe Form der Route auf einen Blick sichtbar ist. Jeder Marker hat ein Popup mit Name, Thema und einem Link zurück zur jeweiligen Station in `index.html` (`index.html#station-N`).

Koordinaten für Hotel, Rivoli, Hôtel de Ville, Pont Louis-Philippe, Pont Marie, Rue Ferdinand-Flocon, La Recyclerie und BarOurcq frisch per Nominatim/OpenStreetMap geocodiert (die anderen — Tour de la Biodiversité, Petite Ceinture, École Damesme, Bassin d'Austerlitz — waren bereits aus früheren Korrekturen exakt bekannt).

Bewusst keine echte Fahrrad-Routenführung (Linien folgen nicht den Strassen) — das ist eine reine Übersicht/Orientierungshilfe, keine Navigationskarte. Für die tatsächliche Strassenführung bleiben die einzelnen "🚴 Strecke zur nächsten Station"-Links pro Etappe massgeblich.

Folgeänderungen:
- `index.html`, Überblick-Abschnitt: neuer Button "🗺️ Routen-Übersicht ansehen" ganz oben, verlinkt auf `karte-uebersicht.html` (neuer Tab).
- Datei-Übersicht ganz oben in diesem README aktualisiert (jetzt zwei Zusatzkarten statt einer).

## Quellen

Recherchiert Ende Juli/Anfang August 2026, siehe Chatverlauf für Einzel-Quellen (Ville de Paris, FRANCE 24, Brut, Le Nouvel Obs, INRAE-Kritik an der Miyawaki-Methode via tela-botanica.org/enlargeyourparis.fr, Mairie du 13e zur Petite Ceinture, Bloomberg CityLab und reporterre.net zur Voie Georges Pompidou). Ergänzt am 29./30.08.2026 um Republik, "Au revoir, Paris" (Kolly, 2026), paris.fr/Mairie du 11e/Mairie du 18e zum "rues aux écoles"-Programm, education.gouv.fr zu den Schulen an der Rue Ferdinand-Flocon, sowie paris-blog.org ("Die Petite Ceinture", Teil 1+2, 2020) und die offizielle paris.fr-Seite zu Square Charles Péguy für die neue Station 1 und den Ausbau der Petite-Ceinture-Station. Für die Konnektivitätsfrage (Porte de Choisy) zusätzlich mairie13.paris.fr und petiteceinture.org/ASPCRF (Statusbericht Dezember 2024). Für die Velo-Infrastruktur-Prüfung (30.08.2026) zusätzlich: rerv.fr und Wikipedia zum Réseau Vélo Île-de-France, mdb-idf.org (Mieux se Déplacer à Bicyclette, u. a. zur Avenue des Gobelins und den Boulevards des Maréchaux), mairie11.paris.fr/mairie12.paris.fr zu Boulevard Voltaire und Rue du Faubourg Saint-Antoine, parisenselle.fr zur "vélorue" Rue de la Roquette, cdn.paris.fr (Bauphasen-PDF Boulevard Saint-Michel), mairie10.paris.fr zu Boulevard Magenta, sowie parisjetaime.com zu den vier Pariser Rad-Hauptachsen. Für die École-Damesme-Korrektur (12.09.2026) zusätzlich: paris.fr/pages/57-nouvelles-rues-aux-ecoles-dans-paris-8197 (vom Nutzer nachgereicht, per Abruf verifiziert). Für die Google-Maps-Wegpunkt-Limite (12.09.2026) zusätzlich: developers.google.com/maps/documentation/urls (offizielle Doku: 9 Wegpunkte am Rechner, 3 auf dem Handy für das `maps/dir/?api=1`-URL-Schema).
