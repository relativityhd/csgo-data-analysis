# CSGO Data Analysis

*Mission Statement:* Es sollen FACEIT Spieler des Spiels CSGO gefunden werden, welche schon bald professionell spielen könnten. Dazu sollen bestehende Datensätze genutzt und neue generiert werden, worauf mit Methoden des maschinellen Lernens ein Ranking erstellt werden soll.

## Über die professionelle CSGO Szene

Counter Strike Global Offensive (CSGO) ist das bekannteste und meist-gespielteste Computerspiel der Welt. CS:GO ist ein taktischer Shooter, bei dem zwei Teams, Counter Terrorist (CT) und Terrorist (T), über eine Höchstdauer von 30 Runden spielen, wobei jede Runde 1 Minute und 55 Sekunden dauert. Jedes Team besteht aus 5 Spielern (insgesamt 10), und das erste Team, das 16 Runden erreicht, gewinnt das Spiel. Zu Beginn spielt ein Team als CT und das andere als T. Nach 15 gespielten Runden tauschen die Teams die Seiten. Es gibt 7 verschiedene Karten, auf denen ein Spiel gespielt werden kann. Als Terrorist gewinnt man eine Runde, indem man entweder die Bombe platziert und dafür sorgt, dass sie explodiert, oder indem man das andere Team eliminiert. Als CT gewinnt man eine Runde, indem man entweder das andere Team ausschaltet oder die Bombe entschärft, sollte sie platziert worden sein.

Aufgrund der sehr competetiven Natur des Spiels gibt es ebenfalls eine sehr große professielle E-Sport Szene des Spiels. Dort treten professionelle Teams auf verschiedenen Events gegeneinander an. Diese Teams nehmen Spieler unter Vertrag wenn diese auf Junior-Turnieren o.ä. positiv auffallen. Dieses Projekt soll Spieler-Scouts dabei unterstützen vielversprechende neue Kandidaten zu finden.

Eine gute Anlaufstelle dazu ist FACEIT. FACEIT ist eine Platform auf der Spieler CSGO aufgrund besserer Implementierung des Matching-Algorithmus sehr viel competetiver spielen als über das normale Spiel. FACEIT stellt zusätzlich auch eine API zur Verfügung welche Zugriff auf historische Spiele, Statistiken der Spieler und weitere Daten gibt.

## Definition eines guten Spielers

In der Praxis erweist es sich sowohl in privaten Freundeskreisen als auch in der professionellen Szene als schwierig die Kompetenz und Leistungsstärke eines Spielers mit anderen zu Vergleichen. Aufgrund der Komplexität des Spiels entwickelten sich über die Jahre eine Reihe an verschiedenen Spielweisen und Rollen innerhalb eines Teams. Weiterhin spielen auch Out-of-Game Eigenschaften wie Kommunikation im Team eine wichtige Rolle. Es gibt somit keine einheitliche Metrik zur Bewertung von Spielern. Daher wird in dieser Arbeit der Erfolg eines Spielers gemessen, also seine Siegrate.

## Projektplan

Die Siegrate eines Spielers soll nicht über die reale Anzahl an gewonnenen Spielen erstellt werden sondern über die Statistiken seiner Spiele. Somit bezieht sich die Siegrate auf die Gewinn-Wahrscheinlichkeit eines Spielers basierend auf seinen Statistiken. Dies ermöglicht einen direkten Vergleich zwischen professionellen Spielern und bisher unprofessionellen.

Das soll wie folgt umgesetzt werden:

1. Eine Kennlinie basierend auf den Spielen von bereits professionellen Spielern soll gekennzeichnet werden. Diese soll aufzeigen auf welchem Niveau sich ein professioneller Spieler mindestens befinden sollte.
2. Die Spielerdatenbank von FACEIT soll dazu genutzt werden Spieler nahe oder sogar über dieser Kennlinie zu finden.

Zur Erstellung der Kennlinie werden FACEIT Spiele von professionellen Spielern ausgewertet und ein Modell trainiert welches die Siegrate eines Spielers Vorhersagen soll. Diese Siegrate stellt den Erfolg eines Spielers dar, basierend auf seinen Statistiken, somit also den (positiven) Einfluss der Spielern auf das Spiel.
Darauf wird dieses Modell genutzt um den Einfluss von unprofessionellen Spielern zu bewerten.

*Benötigte Datensätze:* Zum einen muss ein Datensatz angefertigt werden, welcher die Spiele von professionellen Spielern abbildet. Des weiteren muss zweiter Datensatz zur Anwendung des Modells angefertigt werden, bei welchem lediglich unprofessionelle Spieler berücksichtig werden.
