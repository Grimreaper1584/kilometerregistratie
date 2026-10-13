# Kilometerregistratie

Een eenvoudige webapp om zakelijke kilometers per maand bij te houden en als CSV te exporteren (bijvoorbeeld voor je boekhouding of belastingaangifte als ZZP'er).

**Live:** https://grimreaper1584.github.io/kilometerregistratie/

## Gebruik

1. Kies bovenaan de maand (standaard de huidige maand).
2. Vul één keer onder **Instellingen** je **vertrekadres (thuis)** en de **vergoeding per km** in (standaard € 0,23). Het vertrekadres komt automatisch bij elke rit in de export.
3. Klik op **Rit toevoegen** en vul in:
   - **Datum** (verplicht). Een nieuwe rit krijgt automatisch de dag na de laatste rit.
   - **Plaats** en **Theater / locatie** (vrij invullen; eerder gebruikte waarden worden voorgesteld). Kies je een theater waar je al eens geweest bent, dan worden plaats en heen-km automatisch ingevuld.
   - **Heen (km)** (verplicht) en eventueel **Retour (km)**. De knop **Retour** zet de retour-km gelijk aan heen; nog een keer klikken haalt de retour weg.
   - Kilometers mogen met komma of punt (`12,5` of `12.5`).
4. Totaal km en bedrag per rit en per maand worden automatisch berekend.
5. Klik op **Exporteer naar Excel / Numbers** voor `kilometerregistratie-JJJJ-MM.xlsx`, opgemaakt zoals de bestaande Numbers-sheet: titel, vertrekadres, Datum · Plaats · Theater / locatie · Vertrekadres · Heen (km) · Retour (km) · Totaal (km) · Bedrag, met onderaan MAANDTOTAAL en het aantal ingevulde enkele ritten. Een platte CSV kan ook (`;`, komma als decimaalteken, UTF-8).

## Waar staat mijn data?

Er is geen server of account. Alles wordt opgeslagen in de browser (localStorage) op het apparaat dat je gebruikt:

- Data blijft bewaard als je de pagina sluit, maar is **niet** gedeeld tussen telefoon en laptop.
- Browsergeschiedenis/sitegegevens wissen of privémodus = data weg. **Exporteer daarom elke maand naar CSV** als back-up.
- Het tarief is één instelling voor alle maanden; bij een wijziging worden ook oude maanden met het nieuwe tarief berekend. Exporteer een maand dus vóór je het tarief aanpast.

## Techniek

Eén statisch bestand: `index.html` (HTML, CSS en JavaScript inline, geen dependencies of build stap). Gehost via GitHub Pages vanaf de `main` branch (root).
