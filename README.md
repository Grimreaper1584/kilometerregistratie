# Kilometerregistratie

Een eenvoudige webapp om zakelijke kilometers per maand bij te houden en als CSV te exporteren (bijvoorbeeld voor je boekhouding of belastingaangifte als ZZP'er).

**Live:** https://grimreaper1584.github.io/kilometerregistratie/

## Gebruik

1. Kies bovenaan de maand (standaard de huidige maand).
2. Klik op **Rit toevoegen** en vul datum en kilometers in (verplicht). Vertrekadres, bestemmingsadres en klant zijn optioneel.
   - Een nieuwe rit krijgt automatisch de dag na de laatste rit als datum.
   - **Retour** maakt direct de terugrit aan: zelfde datum, klant en km, met de adressen omgedraaid.
   - Kilometers mogen met komma of punt (`12,5` of `12.5`).
3. Het bedrag per rit en de totalen worden automatisch berekend.
4. Onder **Instellingen** pas je de vergoeding per km aan (standaard € 0,23). Alle bedragen worden direct opnieuw berekend.
5. Klik op **Exporteer naar CSV** voor een bestand `kilometerregistratie-JJJJ-MM.csv` dat direct goed opent in Nederlandse Excel (`;` als scheidingsteken, komma als decimaalteken, UTF-8).
6. **Maand legen** (onderaan) verwijdert alle ritten van de gekozen maand, na bevestiging. Andere maanden en het tarief blijven staan. Heb je de maand nog niet geëxporteerd, dan krijg je een extra waarschuwing.

## Waar staat mijn data?

Er is geen server of account. Alles wordt opgeslagen in de browser (localStorage) op het apparaat dat je gebruikt:

- Data blijft bewaard als je de pagina sluit, maar is **niet** gedeeld tussen telefoon en laptop.
- Browsergeschiedenis/sitegegevens wissen of privémodus = data weg. **Exporteer daarom elke maand naar CSV** als back-up.
- Het tarief is één instelling voor alle maanden; bij een wijziging worden ook oude maanden met het nieuwe tarief berekend. Exporteer een maand dus vóór je het tarief aanpast.

## Techniek

Eén statisch bestand: `index.html` (HTML, CSS en JavaScript inline, geen dependencies of build stap). Gehost via GitHub Pages vanaf de `main` branch (root).
