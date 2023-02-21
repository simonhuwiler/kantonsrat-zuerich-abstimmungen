# Abstimmungen des Zürcher Kantonsrats von 2013 - 2020

## Was ist hier zu finden
Die maschinenlesbaren Ergebnisse (fast) aller Abstimmungen im Kantonsrat, jeweils mit Kantonsrätin/Kantonsrat und Partei.

## Woher stammen die Daten?
Der Kantonsrat veröffentlicht die Ergebnisse als PDF. Diese PDFs wurden als CSV exportiert.

## Wieso nur bis 2020?
Die Daten ab dem Lockdown 2020 bis zum neuen Provisorium im 2023 sind nicht brauchbar. Der Zählcomputer im Messeprovisorium lieferte zwar ein korrektes Endergebnis, jedoch hat er die detaillierten Resultate falsch zugeordnet. Das hat der Export ergeben und das bestätigen auch die Parlamentsdienste. Sie raten davon ab, die PDFs während der Coronazeit zu nutzen. Ab der neuen Legislatur im Bullinger-Provisorium (8. Mai 2023) soll eine ordentliche API zur Verfügung stehen.

## Was fehlt sonst noch?
Einzelne PDFs wurden eingescannt und sind maschinell nicht lesbar. Diese wurden nicht exportiert. Dies sind alle Abstimmungen an folgenden Tagen:
* `2013-05-13`
* `2013-06-17`
* `2013-06-24`
* `2014-03-31`
* `2014-05-05`
* `2015-12-07`
* `2016-09-26`
* `2016-10-24`
* `2016-12-12`
* `2017-03-13`
* `2019-01-14`
* `2019-05-20`
* `2019-12-09`
* `2020-03-02`

Zusätzlich folgende PDFs (`eDocumentID`). Manche sind auch in den oben erwähnten Tagen enthalten.

**OCR-Files**
* `2475cb15a8344f13bf06af57d8df7b6a-332`
* `825bb07a708d484e9aab0122374c96ee-332`
* `1a43a208b59c4665850ad4a13b874dc2-332`
* `7e5e5927378f436cab9d081c424005a7-332`
* `a396a35da60c4676a6e2c84fe3466e33-332`
* `6ec31a40559a450f8eba896e79ad4ce0-332`
* `f6d286de8a444d9694b1da17c5f6cbaf-332`
* `da0fb4f0ee094b6bb06b0509d4c202cb-332`
* `f6e78363414143989fadb00a4c850671-332`
* `53cdf71cb40949718f526ac334503659-332`
* `58217f34333b4ad099eba69e6689a757-332`
* `128740aaa08641cb818671086ba12407-332`
* `2ec3fefeef264dddbe5547ac7ce17861-332`
* `65b9abd5722b4304a7465253b0fe7cd1-332`
* `8fde45cf78614f1dba2c5ff1754729d5-332`
* `d8d1ac4c117845c49cd123933bac2bfc-332`
* `d4e664fd33cf4f09a51339c4a6705cf6-332`
* `60c47b4f4f1e4e939bfe245774d12044-332`
* `ca6cfe86b160424ea068599ce9a89de9-332`
* `48cd67a42b2b42ac97065313a4bc4435-332`
* `e7fcb1a2105a47eeab8f51a4706c424a-332`
* `97af4b09426f41c3940981500450dabc-332`
* `1514c9f2c9e84aeaae22f981e03b6acd-332`

**Fehlerhafter Zeichensatz**
* `4266a27393644bd48c311bd9692ead59-332`
* `9ba073ed8e9a4d12b993fe8b4ce961d6-332`
* `774d77917a6245a6adce75b6458532b0-332`
* `75702d2259c44ebc850b21967696ebf7-332`

**Komische Formate**
* `3dda293d605e4a62b7c4331824ebca95-332`
* `cdfb9a82b24145ed8faf017771d9c9da-332`
* `607a463667bb411495b49245cfffbafe-332`

**Falsch benannt**
* `4398af876b1249acab10d9a50a93b6f1-332`
* `77663a0de59f4458bc670cad3f1f0beb-332`

## Welche Daten liegen wo?
* [export/Jahre/](export/Jahre/): Enthält für jedes Jahr sämtliche Abstimmungen und Stimmen. **Das, wo nach du wohl suchst**. Datenstruktur siehe unten
* [export/abstimmungen.csv](export/abstimmungen.csv): Metadaten über die Abstimmungen. Ist ebenfalls in den Abstimmungsresultaten oben enthalten
* [export/eDocuments](export/eDocuments): Enthält einzelne Abstimmungen als PDF. Dies sind die Originaldateien
* [export/eDocumentsCSV](export/eDocumentsCSV): Enthält einzelne Abstimmungen als CSV, exportiert aus PDF
* [export/GESCHAEFT](export/GESCHAEFT): Alle Geschäfte als XML, direkt exportiert aus der Kantonsrats-API

## Datenstruktur
Die einzelnen Abstimmungen liegen im Ordner [export/Jahre/](export/Jahre/). Das CSV enthält folgende Spalten:

| Name | Datentyp | Beschreibung |
|------|----------|--------------|
|platz|`str`|Platznummer des Regierungsrates. Kann variieren. Besser nicht verwenden|
|nachname|`str`|Nachname der Regierungsrätin/Regierungsrat|
|vorname|`str`|Vorname der Regierungsrätin/Regierungsrat|
|partei|`str`|Partei der Regierungsrätin/Regierungsrat|
|stimme|`enum`|Wie die Person gestimmt hat: `JA` = Ja, `NEIN` = Nein, `ENTHALTEN` = Enthalten, `--` = abwesend|
|KRNr|`str`|Interne (?) Nummer, oft leer|
|VorlageNr|`str`|Nummer des Geschäfts|
|Titel|`str`|Name des Geschäfts, über das abgestimmt wurde|
|Geschaeftsart|`enum`|Geschäftsart, `Parlamentarische Initiative`, `Motion`, etc.|
|AblaufschrittTyp|`enum`|Wo das Geschäft steht. Meist `Zustimmung` oder `Ablehnung`|
|DokumentTitel|`str`|Titel des exportierten Abstimmungs-PDF|
|eDocumentFileName|`str`|Dateiname des exportierten Abstimmungs-PDF. Entspricht jedoch nicht dem Dateinamen, wie er hier vorliegt|
|eDocumentID|`str`|Eindeutige ID des PDF, respektive CSV. ID stammt aus der API des Kantonsrat. Entspricht auch dem Namen des PDFs.|
|Version|`int`|Welche Revision das Dokument aufweist. Wurde jeweils nur die letzte Version verwendet|
|Sitzungsdatum|`date`|Wann die Abstimmung stattfand|
|url|`string`|Adresse zum Abstimmungs-PDF|

## Logik des Exports
Die Export-Scripte liegen im Ordner [/scr/](src/). Der Export funktioniert wie folgt:

### 1. Geschäfte exportieren, Abstimmungen identifizieren (`0_export_documents.ipynb`)
Alle Geschäfte werden aus der Kantonsrats-API exportiert und als XML im Ordner `GESCHAEFT` abgelegt. In diesen Geschäften werden nun Abstimmungsergebnisse identifiziert. Diese sind nicht speziell getagt, sondern müssen per Texterkennung gesucht werden. Gesucht wird:

* `AR` (=Abstimmungsresultat). Alle Resultate ab 2020
* `Abstimmungsresultat`. Ältere Dokumente
* `Schlussabstimmung`. Manche sind aber auch so benannt...

Alle Abstimmungen werden in der Datei [export/abstimmungen.csv](export/abstimmungen.csv) gespeichert. Danach werden die einzelnen PDFs heruntergeladen und im Ordner [export/eDocuments](export/eDocuments) abgelegt.

### 2. PDF extrahieren (`1_extract_pdfs.ipynb`)
Alle PDFs werden mit Tabula exportiert. Dazu stehen verschiedene Templates zur Verfügung, die nacheinander durchprobiert werden, bis 180 Stimmen exportiert wurden. An einzelnen Tagen jedoch bestand der Kantonsrat temporär nur aus 179 Rätinnen und Räten, dies wird ebenfalls beachtet.

Das exportierte CSV wird im Ordner [export/eDocumentsCSV](export/eDocumentsCSV) gespeichert.

### 3. Dateien pro Jahr zusammenführen (`2_combine_results.ipynb`)
Schliesslich werden alle Abstimmungen mit Metadaten angereichert, pro Jahr zusammengefasst und unter [export/Jahre](export/Jahre) abgespeichert.

## Kontakt
[@simonhuwiler](https://www.nzz.ch/impressum/simon-huwiler-shu-ld.1650592)