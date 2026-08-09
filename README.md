# Launcher-Katalog

Die Spieleliste für den Launcher. Zwei Dinge liegen hier:

- **`games.json`** — welche Spiele es gibt, in welcher Version, wo sie liegen
- **Releases** — die Spiel-ZIPs selbst, als Release-Anhänge

Der Launcher liest diese Datei über ihre Raw-Adresse:

```
https://raw.githubusercontent.com/DEIN-NAME/launcher-katalog/main/games.json
```

## Bitte nicht von Hand bearbeiten

Version, Prüfsumme, Größe und Download-Adresse trägt das Skript im
Launcher-Projekt ein:

```
npm run publish-game -- --id <kennung> --version <x.y.z> --from <build-ordner>
```

Von Hand gepflegt werden nur Beschreibung, Bilder und Tags — die lässt das
Skript bewusst in Ruhe.

Falls du doch mal selbst hineinschreibst: **als UTF-8 ohne BOM speichern.**
Der Launcher schneidet die Markierung inzwischen zwar ab, aber sauber ist
sauber.
