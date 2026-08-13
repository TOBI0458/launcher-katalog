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

## Ein Spiel ankündigen, bevor es fertig ist

Lass `download` einfach weg. Der Launcher zeigt einen solchen Eintrag mit
**„Demnächst verfügbar"** an, statt einen Knopf anzubieten, der ins Leere
greift — und der Installer lehnt ihn zusätzlich ab, falls doch jemand daran
vorbeikommt.

```json
{
  "id": "hollow-halls",
  "title": "The Hollow Halls",
  "developer": "Tobias",
  "version": "0.1.0",
  "featured": true,
  "tags": ["Horror", "Ego-Perspektive"],
  "shortDescription": "…",
  "description": "…"
}
```

Es braucht kein zusätzliches Feld dafür, und das ist Absicht: Sobald
`publish-game` die Download-Adresse einträgt, wird von selbst ein
Installieren-Knopf daraus. Ein Merkmal, das man von Hand wieder entfernen
müsste, würde irgendwann vergessen.

Das setzt Ember **0.3.0** voraus. Ältere Fassungen zeigen bei so einem Eintrag
einen Installieren-Knopf, der mit einer Fehlermeldung abbricht.
