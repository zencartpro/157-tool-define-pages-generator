# 157-tool-define-pages-generator
Define Pages Generator (Windows) für Zen Cart deutsch

Wenn die mitgelieferten Inhaltsseiten unter Tools > Seiteneditor nicht ausreichen, kann man leicht weitere eigene Seiten hinzufügen, die dann unter Tools > Seiteneditor editierbar sind.

In diesem Beispiel wird eine neue Define Page namens Beispielseite angelegt, die dann im Shop mit folgendem Link erreichbar sein wird:
meinshop.de/index.php?main_page=beispielseite

Um eine neue Define Page anzulegen, sind immer folgende Dateien erforderlich:
(DEINTEMPLATE steht dabei für den Namen des im Shop aktiven Templates)

* includes/extra_datafiles/beispielseite_filenames.php
* includes/languages/german/DEINTEMPLATE/beispielseite.php
* includes/languages/german/extra_definitions/DEINTEMPLATE/beispielseite.php
* includes/languages/german/html_includes/define_beispielseite.php
* includes/languages/german/html_includes/DEINTEMPLATE/define_beispielseite.php
* includes/languages/english/DEINTEMPLATE/beispielseite.php
* includes/languages/english/extra_definitions/DEINTEMPLATE/beispielseite.php
* includes/languages/english/html_includes/define_beispielseite.php
* includes/languages/english/html_includes/DEINTEMPLATE/define_beispielseite.php
* includes/modules/pages/beispielseite/header_php.php
* includes/templates/DEINTEMPLATE/templates/tpl_beispielseite_default.php

Nach diesem Prinzip können leicht beliebige neue Seiten erstellt werden,
Soll die Seite z.B. Batterieverordnung heißen, dann die entsprechenden Namen der Dateien und die enthaltenen Konstanten entsprechend ändern.

Um sich die Arbeit zu erleichtern kann unter Windows dieser "Define Pages Generator" verwendet werden, der die benötigten Dateien automatisch generiert.
Dieses Tool generiert dabei nur die englischen Sprachfiles, die entsprechenden deutschen müssen manuell ergänzt werden. 
