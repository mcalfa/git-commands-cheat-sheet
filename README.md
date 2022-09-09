# 1. Git - Client Preprocessing

## Git Version checken

```bash
git --version
```

<br>

## Git installieren

- ### Mit HomeBrew installieren (Mac)

  ```bash
  brew install git
  ```

- ### Mit Git Installer installieren (Mac + Win)
  - #### [Git Download Seite](https://git-scm.com/downloads)

<br>
<br>
<br>

# 2. Git - Credentials von GitHub holen

1. Auf www.github.de einloggen
2. Profile / Settings
3. Developer Settings
4. Personal Access Token
5. Neuen Token erstellen
6. An einem SICHEREN ORT ABSPEICHERN

<br>
<br>
<br>

# 3. Git CLI

| Schritt | CLI Befehl       | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ------- | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1       | `$ git init`     | Ein lokaler Ordner wird zu einem Git Repository indem ein verstecktes Verzeichnis .git hinzugefügt wird. Dieser Befehl muss beim Projektstart nur einmal ausgeführt werden und ist solange gültig, solange das .git Verzeichnis besteht."                                                                                                                                                                                                                                                                                                                                |
| 2       | `$ git config`   | Username und Usermail lokal im Repository hinterlegen <br> `git config --local user.name "John Doe"` <br> `git config --local user.email "john@doe.de"` <br><br> Username und Usermail global am Git-Client hinterlegen <br> `git config --global user.name "John Doe"` <br> `git config --global user.email "john@doe.de"`                                                                                                                                                                                                                                              |
| 3       | `$ git clone`    | Erzeugt eine lokale Kopie eines bestehenden remote Repository's von einem Git-Server (z.B. GitHub, GitLab & Co.) <br> `git clone https://github.com/stefan-lippl/cheat-sheet-git-commands.git`                                                                                                                                                                                                                                                                                                                                                                           |
| 4       | `$ git status`   | Zeigt die Datein an, welche geändert wurden                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| 5       | `$ git diff`     | Zeigt die direkte Änderung in der Datei                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| 6       | `$ git ignore`   | Git ignoriert Files / Ordner. Mit echo > .gitignore wird das versteckte file erzeugt. <br> Danach können bestimmte Argumente in das File geschrieben werden. Dabei gibt es verschiedene Schreibweisen für unterschiedliche Use-Cases: <br><br> 1) Bestimmtes File ignorieren <br> &nbsp; &nbsp; `beispiel_file.py` <br> 2) Bestimmten Dateityp ignorieren <br>&nbsp; &nbsp; `*.py` <br>3) Kompletten Ordner ignorieren <br> &nbsp; &nbsp; `privater_code/`                                                                                                               |
| 7       | `$ git add`      | Änderungen zum Staging Bereich hinzufügen. <br><br> Einzelnes File der Staging Area hinzufügen: <br> `git add example_file.py` <br><br> Alle Änderungen der Staging Area hinzufügen: <br> `git add .`                                                                                                                                                                                                                                                                                                                                                                    |
| 8       | `$ git restore`  | Änderungen vom Staging Bereich entfernen. Einzelnes File der Staging Area hinzufügen: <br> `git restore --staged example_file.py` <br><br> Alle Änderungen der Staging Area hinzufügen: <br> `git restore --staged .`                                                                                                                                                                                                                                                                                                                                                    |
| 9       | `$ git commit`   | Änderungen dem lokalen Repository hinzufügen. <br> `git commit -m "Aussagekräftige Commit-Message mit max. 50 Zeichen, was geändert wurde."` <br> Das `-m` symbolisiert hierbei, dass die Commit-Message direkt angefügt wird und der Commit-Editor sich nicht öffnen muss.                                                                                                                                                                                                                                                                                              |
| 10      | `$ git log`      | Gibt eine Übersicht der einzelnen Commits zurück mit Informationen wie: <br> - Commit-Hashadresse <br> - Autor <br> - E-Mail <br> - Datum und <br> - Commit-Message                                                                                                                                                                                                                                                                                                                                                                                                      |
| 11      | `$ git show`     | Liefert detaillierte Informationen über den letzten Commit. Funktioniert wie git diff, nur auf Commit-Ebene. Zeigt sowohl die geänderten Dateien als auch die Stellen der Datei an, welche geändert wurden. <br> Soll nicht der letzte, sondern ein bestimmter Commit betrachtet werden, kann dem Befehl die Commit-Hashadresse noch angehängt werden, welche über git log in Erfahrung gebracht werden kann z.B. <br> `git show 73af80a8a2c922d8f0a55435a177c91b868eb99d`                                                                                               |
| 12      | `$ git reset`    | Damit kann der letzte Commit aus dem lokalen Repository gelöscht werden um Fehler in den Änderungen zu korrigieren. <br> `git reset --soft HEAD^` <br><br> Dabei geht HEAD^ einen Schritt zurück HEAD^^ geht 2 Committs zurück, usw.)                                                                                                                                                                                                                                                                                                                                    |
| 13      | `$ git branch`   | Eine Übersicht aller Branches anzeigen lassen: <br> `git branch` <br><br>Eine Kopie des aktuellen Branches für ein neues Feature erstellen <br> `git branch <neuer-branch-name>` <br><br> Einen nicht mehr benötigten Branch "soft" löschen <br> `git branch -d <branch-name>` <br><br> Einen nicht mehr benötigten Branch "hard" löschen <br> `git branch -D <branch-name>` <br><br> ACHTUNG: Die Kopie wird immer von dem Branch erstellt, in dem man sich gerade befindet. <br> Einen Branch umbenennen indem man sich befindet: <br> `branch -m <neuer-branch-name>` |
| 14      | `$ git checkout` | Damit kann zwischen einzelnen Branches gewechselt werden. Z.B. befindet man sich im main Branch und will in den Branch "feature1" auschecken: <br> `git checkout feature1` <br><br> Man kann auch direkt einen neuen Branch mit checkout erstellen und sofort in diesen auschecken: <br> `git checkout -b <neuer-branch-name>` <br><br> Einen bestimmten Branch kopieren (in dem man sich nicht befindet): <br> `git checkout -b ＜neuer-branch-name＞ ＜existierender-branch-name＞`                                                                                    |
| 15      | `$ git push`     | Änderungen des lokalen Repositorys zum remote Server pushen. Niemals in den Master-Branch pushen sondern immer in einen Feature-Branch: <br> `git push -u origin <feature-branch-name>` <br><br> DENN, einzelne Branches können später dem Master-Branch hinzugefügt werden, nachdem ein oder mehrere Kollegen den Code überprüft haben. Dadurch kann Code der in Production läuft nicht abstürzen, wenn sich versehentliche Bugs eingeschlichen haben.                                                                                                                  |
| 16      | `$ git merge`    | Ein bestimmten Branch in einen anderen Branch migrieren. Im Zielbranch wird folgender Befehl verwendet: <br> `git merge --no-ff <feature-branch-name>`                                                                                                                                                                                                                                                                                                                                                                                                                   |
| 17      | `$ git pull`     | Änderungen des remote Repositorys dem lokalen Repository hinzufügen in Anbetracht des aktuellen Branches. Zum Beispiel den main-Branch aktualisieren: <br> `git pull origin main` <br><br> Einen Feature-Branch namens feature1 aktualisieren (muss im remote Repository verfügbar sein) <br> `git pull origin feature1`                                                                                                                          
