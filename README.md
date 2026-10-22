# regelrecht-corpus-example

Voorbeeldregelwerken voor [RegelRecht](https://github.com/NederlandseDigitaleDienst/regelrecht): een klein aantal wetten met een machineversie (`machine_readable`) en scenario's, zodat iemand zonder account in de editor kan zien hoe een verrijkt regelwerk eruitziet en werkt.

**Deze regelwerken zijn voorbeelden en niet vastgesteld.** De machineversie laat zien hoe een wet uitgevoerd kan worden; de wettekst blijft leidend. De editor toont daarom bij elk regelwerk uit deze repository een melding die dat zegt.

## Hoe deze repository in de editor verschijnt

Het register van de editor (`corpus-registry.yaml` in de regelrecht-repository) noemt deze repository als bron, naast de centrale corpus:

- met `load_all: true`, zodat de publieke bibliotheek (Corpus juris) elk regelwerk hieruit laadt;
- met een hogere prioriteit dan de centrale corpus, zodat bij een versie met dezelfde datum het verrijkte regelwerk wint.

Is de centrale versie nieuwer, dan toont Corpus juris die als huidige versie en meldt het dat een andere versie een machineversie heeft. Houd de versies hier dus bij.

## Directorystructuur

Dezelfde indeling als de centrale corpus:

```
regulation/nl/{laag}/{slug}/{ingangsdatum}.yaml
regulation/nl/{laag}/{slug}/scenarios/{naam}.feature
annotations/{slug}/annotations.yaml
```

| Onderdeel | Beschrijving | Voorbeeld |
|-----------|--------------|-----------|
| `laag` | Regelgevingslaag | `wet`, `amvb`, `ministeriele_regeling` |
| `slug` | De `$id` van het regelwerk | `wet_op_de_zorgtoeslag` |
| `ingangsdatum` | Datum waarop deze versie ingaat (`YYYY-MM-DD`) | `2025-01-01` |

## Een regelwerk toevoegen

Regelwerken komen hier met de hand in, via de editor:

1. Maak in de editor een traject op deze repository: repo-eigenaar `NederlandseDigitaleDienst`, repo `regelrecht-corpus-example`, basisbranch `main`, subpad `regulation/nl`.
2. Voeg het regelwerk aan het traject toe met **Regelwerk toevoegen** en schrijf de machineversie en de scenario's in de editor.
3. De editor bewaart op de trajectbranch en opent een pull request naar `main`. Na de merge staat het regelwerk in Corpus juris.

Loop je daarbij tegen iets aan dat de editor nog niet kan, leg het dan vast als issue in de regelrecht-repository.
