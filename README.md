# Servant
Let servant do the annoying tasks for you.

Servant should be a alternative to Hazle or Maid written in golang.

## Route
Ich möchte hier ein Programm entwickeln das Dateien anhand verschiedener Reglen verwaltet.
Das Programm läuft als deamon und schaut an definierten Orten nach Änderungen.
Sobald sich etwas geändert hat wird die Datei anhand der Definierten regeln verarbeitet.

## Regeln
* Dateiname durch Regex
* Dateiendung (Filetype)
* Zeitstempel
* Größe
* ID3 Tags
* Video Formats (use ffmpeg)

## Actionen
* Move
* Delete
* Unzip
* Copy
* Sync
* Rename

## Funktionen
* watche() - Überwachung von Dateien/Ordner

### Setup

Rules.conf
```json
{
movepdf: {
  filetype: pdf
  action: move
  target: /path/to/pdf/folder
  }
music: {
  filetype: mp3,aac
  action: move
  option: id3 
  taget: /path/to/mp3/artist/album/title-artist.filetype
  }
}
```
Config.conf
```json
{
download: {
  watch: /path/to/folder
  rules: movepdf,music
  }
}
```
