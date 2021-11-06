## Inspiration
Wir wollten herausfinden, welche Faktoren einen wie starken Einfluss auf den Mietpreis für Wohnungen in der Stadt St. Gallen haben. Aus diesen Erkenntnissen wollten wir dann ein Modell für die Vorhersage von Mietpreisen aus den relevanten Faktoren konstruieren.

## What it does
Das erstellte Modell kann aus den Faktoren Wohnfläche, Baujahr und Anzahl nicht-Lebensmittelläden in einem 500m Radius um die Wohnung den Mietpreis einer Wohnung mit einem Fehler von ca. 400 Fr. vorhersagen.

## How we built it
Das Modell basiert auf ordinary least squares linearer Regression. Die Trainingsdaten wurden von [Cividi](https://github.com/cividi/st-gallen-urban-indicators/blob/main/data/price-monitoring/price-monitoring-extended.csv) übernommen und durch eigens beschafften Daten ergänzt. Es wurden folgende Daten pro Wohnung ergänzt:
- Anzahl Supermärkte im 500m Radius
- Anzahl Erholungsorte im 500m Radius
- Anzahl nicht-Lebensmittelläden im 500m Radius
- Distanz zum nächsten Bahnhof
- Distanz zum Hauptbahnhof
- Höhe der Wohnung (m. ü. M.)

Bei allen beschafften Daten wurde analysiert, ob sie einen signifikanten Einfluss auf den Mietpreis haben. Falls ein signifikanter Einfluss vorhanden war, wurde das Attribut in das Trainingsset aufgenommen.

## Challenges we ran into
Das zur Verfügung gestellte Datenset ist zu klein, um es gewinnbringend auf komplexere Machine Learning Modelle wie bspw. KNN Regression oder Decision Tree Regression anzuwenden. 

## Accomplishments that we're proud of
wir sind stolz darauf, dass wir sehr viele Faktoren in das bestehende Datenset integrieren konnten. 

## What we learned
- Bei geringer Datenqualität kann es schwierig sein korrekte Einflussfaktoren für die Mietpreise zu ermitteln.
- Geodaten von OSM können mittels Overpass Turbo einfach extrahiert werden
- Bevor man Modelle traininert sollten die gelabelten Daten inspiziert werden, um einen Überblick zu erhalten.