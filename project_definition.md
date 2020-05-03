# AI-based Retail Product Checkout

## Motivation

Welches Angebot hat mein lokaler Supermarkt? Was gibt es beim Haushaltwarenladen um die Ecke? 
Wir wollen KI-Methoden anwenden um automatisch Produkte in Warenkörben und/oder Supermarktregalen zu erkennen und eindeutig einem Produkt zuzuordnen. 

![](https://miro.medium.com/max/9792/0*6QW9G6q0pNSTz6AR)

## Zielstellung

Anhand eines existieren Trainingsdatensatzes (http://grozi.calit2.net/grozi.html) mit 120 gelabelten Produkten sollen Modelle zur Klassifikation und Segementierung von Produkten entwickelt werden.
Der Datensatz enthält für 120 Produkte Trainngsdaten (inVitro) die für jedes Produkt Aufnahmen verschiedener Richtung und Qualität enthalten.

Ein gelabelter Datensatz von Videoframes (inSitu) enthält pro Produkt ca 30 Videoframes die mit einer Handykamera aufgezeichnet wurden.
Zusätzlich enthält der Datensatz Videoaufnahmen von Supermarktregalen inkl. der Zuordnung sichtbarer Produkte.

In einem ersten Schritt soll aus den 120 gelabelten Bildern (inVitro) ein Modell trainiert werden das die Produkte (inVitro) erkennen/klassifizieren kann.
Dazu können bestehende vortrainierte Netzwerke zur Bildklassifikation (z.B. VGG16, ResNet, Inception) wiederverwendet und angepasst werden.

Die Bilder im inVitro-Datensatz sind bereits händisch aus Videoaufnahmen von Supermarktregalen extrahiert worden.
In einem zweiten Schritt sollen nun Methoden zur Segmentierung der Videoaufnahmen gesucht und evaluiert werden mit denen ein Datensatz - ähnlich zu den gegebenen inVitro-Bildern automatisch erstellt werden könnte.

In einem dritten (optionalen) Schritt könnten die entwickelten Modelle für einen weiteren Datensatz (https://rpc-dataset.github.io) angewendet werden.
Hier muß jedoch ein komplexeres Problem, nämlich die automatische Erkennung von Produkten im Warenkorb gelöst werden. 
Ein existierender gelabelter Datensatz aus China soll dazu genutzt werden um das Problem des Checkouts im Supermarkt zu automatisieren. Der Datensätz enthält für eine Vielzahl von Produkten Aufnahmen aus verschiedenen Blickwinkeln. Diese Produkte sollen dann in verschieden befüllten Warenkörben identifiziert werden. 
Die Milch im Beispiel
![](https://rpc-dataset.github.io/imgs/rpc-dataset.png)

soll folglich in den gegebenen Warenkörben gefunden werden bzw. soll für einen gegebene Warenkorb die Liste der enthaltenen Produkte ausgegeben werden.
![](https://rpc-dataset.github.io/imgs/test.png)

Dazu sind verschiedene Arbeitsschritte notwendig. 
Zunächste müssen die Daten geladen und strukturiert werden.
Für die Entwicklung eines Modells müssen die Produkte im Warenkorb segmentiert, und für jedes Produkt eine Zuordnung getroffen werden. 

Zu verwendende Technologien:
- Tensorflow 2.x
- Keras

## Arbeitspakete

### 1. Datenextraktion & Lösungsskizze
- Die Grozi-120-Daten müssen zur Verarbeitung in Keras in Trainings und Testdaten stukturiert werden. 
- Entsprechend der Aufgabenteile 2 und 3 müssen ebenfalls Daten strukturiert und importiert werden.
Für die Gesamtlösung ist eine Lösungsskizze anzufertigen die die verwendeten Modelle zur Klassifikation und Segmentierung sowie eventuell verwendete Quellen für code-fragmente benennt.

### 2. Modellbildung
- Basierend auf der Lösungsskizze sind die ML-Verfahren zu implementieren. 
- Die Lösungsskizze ist entsprechend zu aktualisieren.

### 3. Evaluierung
- Das umgesetzte Verfahren ist hinsichtlich der Vorhersagequalität zu beurteilen. Hierzu eignen sich die Metriken Recall, Precision und F-Measure.
- Es ist zu untersuchen, inwieweit die Aufteilung von Trainings- und Testdaten, deren Umfang, Datengeneratoren sowie verschiedene Parameter die Vorhersagequalität beeinflussen.
- Die Ergebnisse sollen entsprechnend ausgewertet und für einzelne Probleme Lösungsvorschläge untersucht werden.

### 4. Vortrag
- Ausarbeit einer 10-minütigen Präsentation, in welcher die Aufgabenstellung, die Lösungsskizze (kurze Beschreibung des Algorithmus/Architektur, sowie Nennung der verwendeten Bibliotheken) und die Ergebnisse der Evaluierung dargestellt werden. 


## Literatur/Datasets

http://grozi.calit2.net
http://www.michelemerler.com/papers/grozi_cvprw07.pdf
https://rpc-dataset.github.io
