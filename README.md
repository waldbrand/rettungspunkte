# Rettungspunkte

## WFS zu Rettungspunkten

Über das Geoportal Brandenburg bzw. den Landesbetrieb Forst lässt sich zwar der
WFS finden, aber ein Download der Daten scheint gelinde gesagt versteckt.

Folgende Links lassen sich finden bzw. ableiten:
* https://geoportal.brandenburg.de/gs-json/xml?fileid=B66323D5-E1CB-4FAB-B52E-BEF33D5C792C
* https://www.brandenburg-forst.de/geoserver/inspire/wms?request=GetCapabilities&service=WFS
* https://www.brandenburg-forst.de/geoserver/inspire/wms?request=DescribeFeatureType&service=WFS&Version=2.0.0
* https://www.brandenburg-forst.de/geoserver/inspire/wms?request=GetFeature&SERVICE=WFS&VERSION=2.0.0&outputformat=csv&typeNames=Rettungspunkte

Das liefert erstmal nur die ersten 100 Punkte, das Paging konnte ich erstmal
nicht bedienen.

## Inspire

Über die [Seite von Inspire
selbst](https://inspire-geoportal.ec.europa.eu/results.html?country=de&view=details&theme=none)
lässt sich über das Suchfeld mittels Suchbegriff "Rettungspunkte" der Datensatz
auch finden. Dort gibt es den Bereich "Download Options", welcher dankenswerter
Weise auf eine [Seite beim Landesbetrieb
Forst](http://www.brandenburg-forst.de/inspire/dls/fuek_rp/) verweist auf dem
die Daten tatsächlich einfach herunter geladen werden können, allerdings nur als
GML.

Selbst wenn als Ausgabeformat `gpkg` gewählt wird, werden nur 100 Einträge
geliefert, auch dann wenn zusätzlich noch z.B. `count=101` als Parameter mitgegeben
wird:
https://www.brandenburg-forst.de/geoserver/inspire/wms?request=GetFeature&SERVICE=WFS&VERSION=2.0.0&outputformat=gpkg&typeNames=Rettungspunkte&count=101

Ich habe mir nun beholfen, indem ich den WFS in QGIS als Ebene eingefügt habe
und dann von dort aus als Geopackage gespeichert habe.
