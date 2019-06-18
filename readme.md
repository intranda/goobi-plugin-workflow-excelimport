# Goobi Workflow Plugin: Excel Import

This is the Goobi Plugin to import Excel files into Goobi including detailed validation messages.

## Plugin details

More information about the functionality of this plugin and the complete documentation can be found in the central documentation area at https://docs.intranda.com

Detail | Description
--- | ---
**Plugin identifier**       | plugin_intranda_workflow_excelimport
**Plugin type**             | Workflow plugin
**Documentation (German)**  | - still to be written -
**Documentation (English)** | - still to be translated -

## Installation
Neben der Config müssen noch die Dateien `plugin_intranda_workflow_excelimport_ISO3166-1.txt` und `plugin_intranda_workflow_excelimport_ISO639-2.txt` in `/opt/digiverso/config` liegen oder der pfad der in der Config auf sie zeigt angepasst werden.

Die `ruleset.xml` ist konfiguriert um importieren und anzeigen der Testdatei zu ermöglichen, allerdings noch keinen export.
Vorgangsvorlage, mit der die Vorgänge erzeugt werden muss diesen Regelsatz konfiguriert haben.

Es fehlt noch:
  - Validierung Feld 10/11 (min 1 muss Inhalt haben), Feld 5a/5d (post bzw. email adresse)
  - Import Feld 14a/14b/14c (Problem mit mehreren Spalten mit gleichem Header)
  - Aufspalten von Feld 19a/19b/19c/19d/25/12 an "; "
  - Erfolgsmeldung nach Anlegen der Vorgänge
  - Fehlende Messages: Responsible Editor: "Choose user" + "No step with configured name found", Validierungs Zusammenfassung
  - Updaten der Validierungs Resultate, falls eine 2. Datei hochgeladen wird

## Funktionserklärung
Nachdem eine Excel Datei hochgeladen wurde wird sie direkt validiert.
Nachdem die Validierung abgeschlossen ist (kann einige Sekunden dauern) wird links das Ergebnis und rechts einige Einstellungsmöglichkeiten eingeblendet.
  - Batch name: batch mit diesem Namen wird neu angelegt und alle erzeugten Vorgänge werden ihm hinzugefügt
  - Manual metadata checking needed: falls kein Haken gesetzt ist, wird der Schritt der in der Plugin config unter `<qaStepName>` eingetragen ist per name im ausgewählten Template gesucht und bei der Vorgangserzeugung entfernt.
  - Responsible Editor: Liste aller Personen die dem Schritt unter `<qaStepName>` zugewiesen sind, wird ein Nutzer ausgewählt wird der Schritt bei der Vorgangserzeugung so angepasst das nur noch dieser Nutzer ihm zugewiesen ist. Falls das unten ausgewählte Template keinen Schritt mit entsprechendem Namen enthält kann kein Nutzer ausgewählt werden.
  - Workflow to use: das Vorgangstemplate, nachdem die Vorgänge angelegt werden

Darunter findet sich noch eine Zusammenfassung der Validierung, falls es Mängel gibt.

## Goobi details

Goobi workflow is an open source web application to manage small and large digitisation projects mostly in cultural heritage institutions all around the world. More information about Goobi can be found here:

Detail | Description
--- | ---
**Goobi web site**  | https://www.goobi.io
**Twitter**         | https://twitter.com/goobi
**Goobi community** | https://community.goobi.io

## Development

This plugin was developed by intranda. If you have any issues, feedback, question or if you are looking for more information about Goobi workflow, Goobi viewer and all our other developments that are used in digitisation projects please get in touch with us.  

Contact | Details
--- | ---
**Company name**  | intranda GmbH
**Address**       | Bertha-von-Suttner-Str. 9, 37085 Göttingen, Germany
**Web site**      | https://www.intranda.com
**Twitter**       | https://twitter.com/intranda