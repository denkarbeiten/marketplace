---
name: unslop
description: Use when a German text for external readers (Angebot, Leadmagnet, Kundenmail, Website, Konzept, Skripttext, Kurs-Sprechtext) reads dumbed down or like generic marketing copy or a YouTube tutorial, with paraphrased technical terms, metaphors instead of statements, verbless staccato fragments, insider lines, invented presenter anecdotes or learner reassurance; also as the final pass before any text for third parties leaves the session. Triggers on /denkarbeit:unslop.
---

# unslop

## Zweck

Texte für Dritte entstehen in einem anderen Register als der Dialog: Die Gattungsvorlage „Marketingtext" bringt Umschreibungen, Bilder und Staccato mit, und das Lesermodell setzt den Adressaten zu tief an. Dieser Skill führt einen fertigen Text in das Register zurück, in dem der Dialog mit dem Auftraggeber steht, ohne Inhalt, Reihenfolge, Struktur oder Länge zu verändern.

Für Sprechtexte (Kurs, Erklärvideo) heißt die Gattungsvorlage „Tutorial": Sie bringt die Beichte der Sprecherin, die Beruhigung des Lerners und den Pseudo-Merksatz mit. Die Zielgruppe des Kurses ist kompetent und hat sich für die Tiefe entschieden; der Sprechtext erklärt ihr die Sache so, wie der Dialog sie dem Auftraggeber erklärt, in du-Anrede und gesprochenem Register. In einer Skript-Datei gelten als Text nur die Sprechtext-Zeilen; Regie (`==…==`), Artefakt-Listen, Prompts (`>`) und Trigger `[N]`/`[cap:…]` bleiben unberührt, die Trigger an ihrem Wort.

## Aufruf

- `/denkarbeit:unslop <pfad>`: normalisiert die Textblöcke der Datei an Ort und Stelle. Layoutangaben, Dateilisten, Frontmatter, Tabellen und Code bleiben unberührt; `updated` wird gesetzt, falls Frontmatter vorhanden.
- `/denkarbeit:unslop <pfad> temp`: schreibt die Fassung stattdessen in die `temp.md` des Ordners (vorhandener Inhalt wird überschrieben), die Quelle bleibt unverändert.
- `/denkarbeit:unslop` ohne Pfad: gilt für den letzten Text, den ich in dieser Session für Dritte geschrieben habe; die Fassung kommt in die Antwort.

## Der Text, der herauskommt

Jeder Absatz steht so, wie ich ihn dem Auftraggeber im Chat erklären würde, übertragen in die Anredeform des Dokuments. Konkret:

1. **Jeder Satz hat ein Verb und eine Aussage.** Fragmente werden zu Sätzen oder in den Satz davor gezogen. Der Rhythmus ist der einer Erklärung, nicht der einer Anzeige.
2. **Der Leser gilt als kompetent.** Gängige Fachbegriffe stehen als Begriff: API, Webhook, LLM, Agent, Repository, Cloud, Code, Deployment, Polling. Eine Umschreibung ersetzt den Begriff nur, wenn der Begriff im Deutschen keinen Namen hat.
3. **Ein Sachverhalt wird benannt, nicht bebildert.** Wo ein Bild steht (Tür, Fenster, Takt, kippen, hängen), steht danach der Sachverhalt, den es meinte.
4. **Werkzeuge und Produkte heißen beim Namen**, ohne Verniedlichung (kein „zusammenklicken", kein „Kästchen").
5. **Kein Satz, der den Leser zum Mitwisser macht**: keine Insider-Pointe, keine Ironie, kein Dialogrest.
6. **Die Wortregeln des Dokuments gelten weiter** (Anrede, Begriffsfestlegungen, Verbote), ebenso die Regeln der CLAUDE.md zu Gedankenstrich, „nicht X, sondern Y", Dreierfigur, Verstärkern und Schlusssatz.

Inhalt, Argumente, Zahlen, Reihenfolge und Zwischentitel bleiben; die Länge je Absatz weicht höchstens um ein Fünftel ab. Headlines werden nur angefasst, wenn sie eines der Muster tragen.

## Ablauf

1. **Lesen und messen.** Den gesamten Text einmal gegen die Fallenliste lesen und jede Fundstelle notieren (Muster, Zitat). Erst danach schreiben.
2. **Umformen**, Absatz für Absatz, nach dem Rezept oben, auch die Absätze ohne Fundstelle. Für jeden Absatz gilt die Probe: Würde ich das dem Auftraggeber so sagen? Ein Absatz bleibt nur wortgleich, wenn er die Probe besteht; die Fundstellenliste aus Schritt 1 ist Einstieg, nicht Grenze der Arbeit.
3. **Nachmessen.** Die Fassung ein zweites Mal gegen die Fallenliste lesen, jeden Absatz, auch die unveränderten. Reste werden behoben, nicht begründet.
4. **Schreiben** nach Aufrufart, dann **Ausweis** in der Antwort.

## Fallenliste

| Muster | Erkennen an |
|---|---|
| Umschreibung statt Begriff | „Schnittstelle, die …", „erfährt sofort, wenn …", „Sprachmodell", „im Takt einer Abfrage" |
| Bild statt Aussage | Tür, Fenster, Schallgrenze, kippen, hängen, Fleißarbeit, Lärm |
| Werbe-Staccato | verblose Fragmente („keinen Schritt weiter", „Fünfstellig, Wochen Wartezeit"), Kurzsatz-Kaskade am Absatzende |
| Verniedlichung | zusammenklicken, Kästchen, Baukasten, „ein Chat-Abo hier, ein Tool da". Begriffe des Dokuments (etwa „Baustein" als Produktvokabular) sind keine Verniedlichung und bleiben |
| Insider-Satz | Ironie, Pointe, Dialogrest („Wenn Sie uns anrufen, lernen Sie etwas") |
| CLAUDE.md-Muster | Gedankenstrich, „nicht X, sondern Y", Dreierfigur, Verstärker, aufwertender Schlusssatz |
| **Tutorial-Register** (Sprechtexte) | |
| Sprecher-Anekdote ohne Beleg | erfundene Biografie der Sprecherin zur Verbrüderung („habe ich selbst erst nach Monaten entdeckt", „ging mir am Anfang genauso") |
| Lerner-Beruhigung als Floskel | „du hast es vom ersten Tag", „das klingt technischer, als es gemeint ist", „da gibt es kein richtig und kein falsch", „keine Sorge" als Einschub in einem Sach-Beat. Bleibt, wo die Beruhigung der Inhalt des Beats ist (Zwischenstopp, Kontrollpunkt) |
| Pseudo-Merksatz | „Merk dir drei Worte", „ein Satz, den du dir mitnehmen solltest", Zahlwort-Formel ohne Inhalt |
| Wertung der eigenen Lektion | „der Grundsatz, der wichtiger ist als …", „der Moment, an dem die meisten scheitern", „Das ist nie hilfreich" als Schlusssatz |
| Verweis-Floskel | „dazu gleich mehr", „darauf kommen wir zurück" als Füller; ein Verweis bleibt, wenn er Kapitel oder Stelle nennt |

## Ausweis (Pflicht)

Die Antwort endet mit einer Tabelle: Muster, Fundstellen vorher, Fundstellen nachher. Nachher steht überall 0; wo nicht, nennt eine Zeile das Zitat und den Grund. Ohne Ausweis gilt der Lauf als nicht erfolgt.

## Grenzen

Der Skill verbessert keine Argumente, kürzt nicht, ergänzt nichts und prüft keine Fakten. Was inhaltlich falsch oder schwach ist, bleibt es und wird in der Antwort als Beobachtung genannt, nicht im Text geändert.
