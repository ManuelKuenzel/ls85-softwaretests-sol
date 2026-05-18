## Aufgabe 5 – Transfer: Testen bewerten und empfehlen 🔴

a) Argumentation für systematisches Testen
Das bisher nichts passiert ist, ist leider keine Garantie für die Zukunft, denn vollständiges Testen ist unmöglich und Software wird immer komplexer.
Wenn wir nicht systematisch testen, riskieren wir unentdeckte Softwarefehler, die im schlimmsten Fall existenzbedrohend sind – wie damals beim Absturz der Ariane-5-Rakete 1996, bei der ein einfacher Softwarefehler beim Konvertieren einer Zahl einen Schaden von 370 Millionen Dollar verursachte.
Durch frühzeitiges Testen finden wir Fehler dort, wo sie entstehen. Das spart enorm viel Zeit und Geld, da Fehlerkosten im Laufe der Entwicklung exponentiell steigen.
Zudem wissen wir durch das Prinzip des Defect Clustering, dass sich die meisten Bugs in wenigen, komplexen Modulen häufen, weshalb wir unsere Testaufwände dort sehr effizient bündeln können.
Systematisches Testen ist also keine Zeitverschwendung, sondern unsere Versicherung für stabile Software, zufriedene Kunden und den Schutz unseres Rufs.

b) Fehler-Analyse für die Urlaubsfunktion

Szenario: berechne_urlaubstage(eintrittsdatum, arbeitstage_pro_woche)

Error (Menschlicher Fehler): Der Entwickler hat bei der Berechnung des anteiligen Urlaubs für das Einstiegsjahr die gesetzliche Rundungsregel (ab 0,5 Tagen wird aufgerundet) falsch verstanden oder schlicht vergessen, diese im Code zu berücksichtigen.

Defect (Defekt / Bug im Code): Im Code fehlt die kaufmännische Rundungsfunktion bzw. Bedingung (z. B. math.ceil()), sodass Python die Nachkommastellen beim Umwandeln in eine Ganzzahl einfach abschneidet (int(Urlaubstage)).

Failure (Fehlwirkung für den Nutzer): Ein Mitarbeiter, der im Juli anfängt und dem rechnerisch 12,5 Urlaubstage zustehen würden, sieht auf seiner Abrechnung plötzlich nur noch 12 statt der gesetzlich vorgeschriebenen 13 Tage.

c) Bewertung von Prinzip 7: "Keine Fehler = Gutes System"

Selbst wenn die Funktion berechne_urlaubstage von der IT mathematisch absolut perfekt programmiert wurde, zu 100 % fehlerfrei läuft und alle automatisierten Unit-Tests fehlerfrei besteht, sagt das noch nichts über den eigentlichen Nutzen aus.

Wenn die Software in der Praxis die echten Anforderungen der Personalabteilung nicht abbilden kann, ist sie trotz "Null Fehlern" wertlos. Das wäre in diesem Fall zum Beispiel so, wenn die Funktion:

- Keine Sonderregelungen für Schwerbehinderte, Mutterschutz oder Tarifverträge beherrscht.

- Keine Logik besitzt, um Resturlaub korrekt in das neue Jahr zu übertragen.

- Eine Benutzeroberfläche hat, die für die Mitarbeiter der HR-Abteilung so kompliziert ist, dass sie Fehlbedienungen provoziert.

## Tandem-Aufgabe 👥

Ein menschlicher Denkfehler (Error) führt im Code zu einer fehlerhaften Zeile (Bug/Defect), die beim Ausführen der Software zu einem sichtbaren Versagen (Failure) führt.
