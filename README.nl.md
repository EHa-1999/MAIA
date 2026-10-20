# MAIA

**Messaging Archive & Information Assistant.** Een demo van chatarchivering in XENA: chatberichten uit elk kanaal komen in hetzelfde register en dezelfde objectopslag, met de Office Assistent naast het gesprek.

MAIA hoort bij XENA, naast de demo van de opslag, MIRA (de assistent in het kantoorpakket), TINA (het zoekportaal voor de inwoner) en ELSA (e-mailarchivering).

> Een demo, geen product. Personen, organisaties, berichten, telefoonnummers en nummers zijn verzonnen. Productnamen staan er om herkenbaar te zijn; de demo is niet door de leveranciers gemaakt of goedgekeurd.

## Wat de demo laat zien

| Weergave | Wat je ziet |
|---|---|
| **Gesprekken** | Een chatomgeving met zeven kanalen: Nextcloud Talk, Element (MijnBureau), Tchap (LaSuite), Microsoft Teams, Slack, WhatsApp Business en Signal. Per bericht kies je zakelijk of persoonlijk, voor een selectie of via het contextmenu, en zie je of het in het archief staat. Bij zakelijk opent de Office Assistent de metagegevens en het anonimiseren. Het paneel toont verder per gesprek de klasse van het kanaal, de archiefdeelnemer, vastleggen van een selectie, koppelen aan zaak en dossier, een gewaarmerkt gespreksverslag en anonimiseren voor de Woo. |
| **Kanalen** | Vier klassen: A (eigen beheer), A′ (eigen beheer, end-to-end versleuteld), B (leverancier) en C (toestel). Per kanaal waar het origineel staat, hoe XENA het krijgt, hoe volledig en met welke bewijskracht. |
| **Architectuur** | Van werkplek via integratielaag en aanvoer per klasse naar de Nextcloud-stack van XENA, met de stappen per soort bericht. Productnamen zijn veralgemeniseerd. |
| **Techniek** | Wat elk kanaal levert, het objectmodel voor chatberichten, drie manieren voor een archiefdeelnemer en de open standaarden. |
| **Groeipad** | Zes stappen, van Teams afvangen als kopie tot chat aan de bron. |

Met de knoppen bovenaan spring je vooruit in de tijd om te zien wat er na tien dagen gebeurt.

## Uitgangspunten

- Het bericht is het informatieobject. Een gesprek is een subtype van map en bestaat als metagegeven in het register.
- Een ruimte of kanaal over werk is zakelijk. Een één-op-één-gesprek scheidt de medewerker zelf, binnen tien dagen; daarna geldt het als zakelijk.
- Verwijderen in een zakelijk gesprek haalt het bericht uit de chat, niet uit het archief. Een bewerking is een nieuwe versie.
- Breek nooit de versleuteling om te kunnen archiveren. In versleutelde Matrix-ruimtes doet een zichtbare archiefdeelnemer mee, met sleutels in de sleutelkluis van de gemeente. Op een toestel legt de medewerker zelf vast.
- Elke aanvoer eindigt in een WebDAV-schrijfactie in Nextcloud, die eerst het register bijwerkt. Het archief verhuist nooit; alleen de bron van de berichten verandert.

## Gebruik

Open `index.html` in een browser. Er is geen server nodig. Talen: Nederlands, Duits, Engels en Frans; `#de`, `#en` of `#fr` achter het adres kiest de taal voor die ene link.

## Bouwen

De bron staat in `src/demo.html`, de vertalingen in `i18n/<taal>.json` (sleutel is de Nederlandse tekst).

```
python3 build.py
```

schrijft `index.html` en `MAIA - v<N>.html`. Het versienummer staat in `VERSION`.

## Licentie

EUPL-1.2, zie `LICENSE`.
