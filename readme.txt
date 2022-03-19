Define Pages Generator Version v0.3
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Author:  Brian Tyler
Contact: btyler@math.ucl.ac.uk
Purpose: DefinePagesGenerator for Windows XP takes the hassle out of creating 
         new define pages, by generating the core files neccesary for a define
         page to function and putting them in the correct ZenCart directory
         structure. This application is based on the About Us mod, which gives
         an example of how to create a new define page.
         
Note:    This application was written in VB.NET. I don't think that it needs
         the Visual Basic runtimes, but it defintely needs the .NET 2.0
         framework to be installed on your computer. This is a free Windows
         Update, however it is optional so you may not have it installed.
         
         If you get the error message:
         
         "The application failed to initialize properly (0xc0000135).
         Click on OK to terminate the application."
         
         Or a message saying that you don't have the .NET 2.x framework
         installed, then that means you dont have the .NET 2.x framework
         installed. To install it goto
         
         http://www.microsoft.com/downloads/details.aspx?familyid=0856eacb-4362-4b0d-8edd-aab15c5e04f5&displaylang=en
         
         Instructions on how to use the application are contained in the 
         application itself.
         
         Any other problems please email me.
         
         
         

Disclaimer:
I have done my best to ensure that this application is free of bugs and that
it will not harm your computer, but you use it entirely at your own risk. It
comes without any guarantee of usability or suitability for purpose.

You are free to use and distribute this application as you wish.




Wenn die mitgelieferten Inhaltsseiten unter Tools > Seiteneditor nicht ausreichen, kann man leicht weitere eigene Seiten hinzufügen, die dann unter Tools > Seiteneditor editierbar sind.

In diesem Beispiel wird eine neue Define Page namens Beispielseite angelegt, die dann im Shop mit folgendem Link erreichbar sein wird:
meinshop.de/index.php?main_page=beispielseite

Um eine neue Define Page anzulegen, sind immer folgende Dateien erforderlich:
(DEINTEMPLATE steht dabei für den Namen des im Shop aktiven Templates)

includes/extra_datafiles/beispielseite_filenames.php
includes/languages/german/DEINTEMPLATE/beispielseite.php
includes/languages/german/extra_definitions/DEINTEMPLATE/beispielseite.php
includes/languages/german/html_includes/define_beispielseite.php
includes/languages/german/html_includes/DEINTEMPLATE/define_beispielseite.php
includes/languages/english/DEINTEMPLATE/beispielseite.php
includes/languages/english/extra_definitions/DEINTEMPLATE/beispielseite.php
includes/languages/english/html_includes/define_beispielseite.php
includes/languages/english/html_includes/DEINTEMPLATE/define_beispielseite.php
includes/modules/pages/beispielseite/header_php.php
includes/templates/DEINTEMPLATE/templates/tpl_beispielseite_default.php

Um die Funktionalität zu nutzen, die neue Seite admingesteuert ein- und auschalten zu können, muss sie nun noch unter Konfiguration > Eigene Seiten hinzugefügt werden.
Dazu folgenden Befehl via phpMyAdmin einspielen:
Code:

INSERT IGNORE INTO configuration (configuration_title, configuration_key, configuration_value, configuration_description, configuration_group_id, sort_order, use_function, set_function) VALUES
('Define Beispielseite Status', 'DEFINE_BEISPIELSEITE_STATUS', '1', 'Enable the Defined Beispielseite Link/Text?0= Link ON, Define Text OFF1= Link ON, Define Text ON2= Link OFF, Define Text ON3= Link OFF, Define Text OFF', 25, 100, NULL, 'zen_cfg_select_option(array(0, 1, 2, 3), ');
INSERT IGNORE INTO configuration_language (configuration_title, configuration_key, configuration_language_id, configuration_description, last_modified, date_added) VALUES
('Beispielseite', 'DEFINE_BEISPIELSEITE_STATUS', 43, 'Den Inhalt für diese Seite können Sie über Tools->Seiteneditor bearbeiten.Zuständige Datei: define_beispielseite.phpBESCHREIBUNG:Link EIN bedeutet, dass der Link in der Infobox sichtbar ist.Text AUS bedeutet, dass der definierte Seitentext nicht eingeblendet wird.OPTIONEN:0= Link EIN, Text AUS1= Link EIN, Text EIN2= Link AUS, Text EIN3= Link AUS, Text AUS', now(), now());

Nach diesem Prinzip können leicht beliebige neue Seiten erstellt werden,
Soll die Seite z.B. Batterieverordnung heißen, dann die entsprechenden Namen der Dateien und die enthaltenen Konstanten entsprechend ändern.

Um sich die Arbeit zu erleichtern kann unter Windows dieser "Define Pages Generator" verwendet werden, der die benötigten Dateien automatisch generiert.
Dieses Tool generiert dabei nur die englischen Sprachfiles, die entsprechenden deutschen müssen manuell ergänzt werden. 

