# CSGO Data Analysis

*Mission Statement:* Es sollen FACEIT Spieler des Spiels CSGO gefunden werden, welche schon bald professionell spielen könnten. Dazu sollen bestehende Datensätze genutzt und neue generiert werden, worauf mit Methoden des maschinellen Lernens ein Ranking erstellt werden soll.

## Über die professionelle CSGO Szene

Counter Strike Global Offensive (CSGO) ist das bekannteste und meist-gespielteste Computerspiel der Welt. CS:GO ist ein taktischer Shooter, bei dem zwei Teams, Counter Terrorist (CT) und Terrorist (T), über eine Höchstdauer von 30 Runden spielen, wobei jede Runde 1 Minute und 55 Sekunden dauert. Jedes Team besteht aus 5 Spielern (insgesamt 10), und das erste Team, das 16 Runden erreicht, gewinnt das Spiel. Zu Beginn spielt ein Team als CT und das andere als T. Nach 15 gespielten Runden tauschen die Teams die Seiten. Es gibt 7 verschiedene Karten, auf denen ein Spiel gespielt werden kann. Als Terrorist gewinnt man eine Runde, indem man entweder die Bombe platziert und dafür sorgt, dass sie explodiert, oder indem man das andere Team eliminiert. Als CT gewinnt man eine Runde, indem man entweder das andere Team ausschaltet oder die Bombe entschärft, sollte sie platziert worden sein.

Aufgrund der sehr competetiven Natur des Spiels gibt es ebenfalls eine sehr große professielle E-Sport Szene des Spiels. Dort treten professionelle Teams auf verschiedenen Events gegeneinander an. Diese Teams nehmen Spieler unter Vertrag wenn diese auf Junior-Turnieren o.ä. positiv auffallen. Dieses Projekt soll Spieler-Scouts dabei unterstützen vielversprechende neue Kandidaten zu finden.

Eine gute Anlaufstelle dazu ist FACEIT. FACEIT ist eine Platform auf der Spieler CSGO aufgrund besserer Implementierung des Matching-Algorithmus sehr viel competetiver spielen als über das normale Spiel. FACEIT stellt zusätzlich auch eine API zur Verfügung welche Zugriff auf historische Spiele, Statistiken der Spieler und weitere Daten gibt.

## Definition eines guten Spielers

In der Praxis erweist es sich sowohl in privaten Freundeskreisen als auch in der professionellen Szene als schwierig die Kompetenz und Leistungsstärke eines Spielers mit anderen zu Vergleichen. Aufgrund der Komplexität des Spiels entwickelten sich über die Jahre eine Reihe an verschiedenen Spielweisen und Rollen innerhalb eines Teams. Weiterhin spielen auch Out-of-Game Eigenschaften wie Kommunikation im Team eine wichtige Rolle. Es gibt somit keine einheitliche Metrik zur Bewertung von Spielern. Da diese Arbeit lediglich rudimentäre Statistiken zu den Spielern nutzt ist es nicht möglich die eben beschriebenen wichtigen Attribute eines guten Spielers zu erfassen.

## Projektplan

Das Projekt ist über folgende 5 Notebooks aufgeteilt:

1. **Data Aquisition**: Hier werden über die FACEIT-API Spieler-Statisiken heruntergeladen und zu einem einheitlichen Datensatz zusammengefasst
2. **Data Cleaning**: Hier wird der im ersten Schritt erstellte Datensatz genauer analysiert und basierend aus diesen Erkenntnissen gesäubert
3. **Classification mit SciKit-Learn**: Hier wird der Datensatz genutzt um verschiedene von SciKit-Learn vorimplementierte Modelle zu trainieren
4. **Classification mit PyTorch**: Hier wird ein neuronales Netz mit dem Datensatz trainiert, sowie die Modelle aus dem dritten Schritt mit diesem Verglichen
5. **Anwendung**: Hier wird schlussendlich das beste Modell auf den Datensatz angewandt um mögliche professionelle Spieler zu finden

Es wird versucht anhand einer Grundwahrheit - einer Liste an bereites professionellen Spielern - eine Kennlinie zwischen eben diesen professionellen Spielern und dem Rest zu zeichnen. Basierend auf dieser Kennlinie sollen darauf potentielle professionelle Spieler erkannt werden.

## Environment Setup

Um das Python-Environment aufzusetzen wird empfohlen [Poetry](https://python-poetry.org/) zu benutzen:

```sh
poetry install
```

Alternativ kann auch aus der `requirements.txt` ein Environment generiert werden. **Bitte das System-Environment beachten, mit welcher die `requirements.txt` erstellt wurde:**

- Python==3.9.12
- WSL2 Ubuntu
- CUDA disabled

Um CUDA zu aktivieren muss PyTorch entsprechend mit `cudatoolkit` installiert werden.
