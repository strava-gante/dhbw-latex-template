# dhbw-latex-template
LaTeX template for project papers, bacherlor theses or other scientific papers at DHBW Stuttgart.

Erstellt auf Basis einer Vorlage von Dr. Julian Reichwald und Prof. Dr. Jörg Baumgart.

*ACHTUNG: Für das Erstellen des Literaturverzeichnisses wird das modernere Paket biblatex in Kombination mit biber verwendet - nicht mehr das ältere BibTex! Bitte stellen Sie ggf. Ihre TeX-Umgebung entsprechend ein (z.B. TeXStudio: Einstellungen --> Erzeugen --> Standard Bibliographieprogramm: biber)*


Gebrauchsanleitung
==================

Übersicht über die Vorlage
--------------------------

Die Vorlage wurde im UTF-8 Encoding erstellt. Sollten daher z.B. Umlaute in Ihrem LaTeX-Editor nicht korrekt dargestellt werden, überprüfen Sie bitte die Encoding-Einstellungen des Editors. In seltenen Fällen müssen Sie die Vorlage danach noch einmal neu in den Editor einbinden. Die Vorlage beinhaltet die folgenden aufgelisteten Dateien:

  `main.tex`                   Die Hauptdatei. Alle anderen Dateien werden von dieser Datei eingezogen.
  
  `abstract.tex`               Die Kurzfassung der Arbeit.
  
  `acronyms.tex`               Definition von Abkürzungen.
  
  `declarationonhonours.tex`   Ehrenwörtliche Erklärung.
  
  `glossary.tex`               Glossar.
  
  `nondisclosurenotice.tex`    Sperrvermerk.
 
  `symbols.tex`                Definition von Symbolen.
  
  `titlepage.tex`              Titelseite der Arbeit.
  
  `code.tex`                   Konfigurationseinstellungen von Code Listings.
  
  `config.tex`                 Konfigurationseinstellungen der einzelnen Pakete.
  
  `settings.tex`               Persönliche Daten der Arbeit.
  
  `01Introduction.tex`         Diese Anleitung.
  
  `bibliography.bib`           Die Literaturdatenbank – hier können Sie die verwendete Literatur einpflegen.

Es werden – unter anderem – die folgenden Zusatzpakete von dieser Vorlage eingezogen und sollten daher in aktuellen Versionen installiert sein:

-   `KOMA-Script` bzw. die Dokumentenklasse `scrreprt`
-   `hyperref` für PDF-Informationen und Links
-   `babel` für länderspezifische Einstellungen
-   `csquotes` für sprachabhängige Anführungszeichen (Befehl: `enquote`)
-   `acronym` für das Erstellen des Abkürzungsverzeichnisses
-   `booktabs` für das typografisch schöne Setzen von Tabellen
-   `listings` für schöne Quelltexte
-   `algorithm` für schöne Algorithmen
-   `bibltatex` und `biber` für die Erstellung des Literaturverzeichnisses.

Alle Konfigurationen dieser Vorlage können in der Datei `config.tex` eingesehen und ggf. verändert werden. Bitte schauen Sie sich die entsprechenden Dokumentationen der Pakete an (<https://www.ctan.org>), um deren Verwendung und Möglichkeiten jenseits der hier gezeigten Beispiele zu erlernen.

Übersetzung von LaTeX-Dateien
-----------------------------

Die Übersetzung von LaTeX-Dateien erfolgt in mehreren Schritten und unter der Zuhilfenahme unterschiedlicher Programme. Das Hauptdokument (hier die Datei `main.tex`) wird mittels `pdflatex` zu einem PDF übersetzt. Ggf. ist eine mehrfache Übersetzung notwendig, um z.B. das Inhaltsverzeichnis korrekt darzustellen.

Für die Einbindung des Literaturverzeichnisses wird nicht mehr das ältere `bibtex`, sondern das neuere `biber` in Kombination mit `biblatex` verwendet. Bitte stellen Sie Ihren LaTeX-Editor so ein, dass die Verwendung von Biber beim Übersetzungsprozess erfolgt.

Verwendung von Akronymen
------------------------

Akronyme müssen in der Datei `acronyms.tex` definiert werden (schauen Sie sich hierzu bitte die entsprechende Paket-Dokumentation an!) Ein definiertes Akronym kann dann mit dem Befehl `ac` verwenden. Die Aufnahme eines verwendeten Akronyms in das Abkürzungsverzeichnis erfolgt automatisch.

Zitieren von Quellen
--------------------

Mit dem Befehl `autocite` kann zitiert werden. Sollen mehrere Referenzen auf einmal gesetzt werden, können Sie dies mit dem Befehl `autocites` erreichen. Wird `autocite` konsequent verwendet, kann in der Datei `config.tex` der Zitationsstil umgeschaltet werden, ohne dass im Text Veränderungen vorgenommen werden müssen. Vorkonfigurierte Stile sind Alphabetic, Harvard, Fußnotenzitat, IEEE, und APA-Style. Die Übernahme der Quellen in das Literaturverzeichnis erfolgt automatisch. Ein Beispiel für eine Online-Quelle ist ebenfalls enthalten.
Soll einer Abbildung eine Quellenangabe zugefügt werden, bietet es sich an, diese direkt in der jeweiligen Abbildungsbeschriftung zu hinterlegen. Hierfür kann der Befehl `cite` verwendet werden, um eine ungewollte Fußnote zu vermeiden.

Text in Anführungszeichen
-------------------------

Soll ein Text in Anführungszeichen gesetzt werden, kann dies über den Befehl `enquote` “so erreicht werden”. Die Anführungszeichen ändern sich automatisch auf die jeweiligen Länderspezifika, wenn die Spracheinstellung des `babel`-Pakets geändert wird. Voreinstellung ist die amerikanische Verwendung von Anführungszeichen.

Beispiele
---------

### Unterabschnitte

Es gibt neben `chapter` auch noch `section`, `subsection`, `subsubsection` etc. Eine zu starke Untergliederung des Textes sollte jedoch vermieden werden (z.B. ein Abschnitt 3.4.2.5.3).

### Tabellen und Abbildungen

Tabellen und Abbildungen sind sogenannte *Floating Objects*, d.h. LaTeX setzt diese Objekte an Positionen, die satztechnisch geeignet sind. Daher kann es vorkommen, dass Tabellen oder Abbildungen auf einer anderen Seite erscheinen, die dann referenziert werden müssen. Hier ein Beispiel dafür:

LaTeX  kümmert sich darum, wo die Abbildungen gesetzt werden und passt den Text der Referenz entsprechend an. Soll nur die Nummerierung in den Text geschrieben werden, dann kann der Befehl `ref` verwendet werden. Abbildungen sollten – falls möglich – als Vektor-PDF eingebunden werden, da die diese dann beliebig skalieren können.

### Listings

Das Einbinden eines Listings mit der entsprechenden Umgebung ist auch kein Problem, wie man in Listing [lst:helloworld] sehen kann. Schauen Sie sich hierzu das `listings`-Paket an!

    public static void main(String args[]) {
       System.out.println("Hello World!");
    }

### Mathematische Formeln

Auch mathematische Ausdrücke können mit LaTeX  sehr gut gesetzt werden, wie man anhand der Gleichung [eqn:e2] sehen kann – konsultieren Sie hierzu bitte entsprechende Dokumentationen, die Online zur Verfügung stehen.

```f(x)=x^2$$```

### Algorithmen

Algorithmen können als Pseudocodes dargestellt und referenziert werden, wie z.B. in Algorithmus [alg:euclid] – sogar bis auf Zeilennummern. Schauen Sie sich hierzu bitte das Paket `algorithmicx` an.

### Glossar

Der wird automatisch erzeugt und zeigt alle referenzierten Glossareinträge an. Um einen neuen Glossareintrag zu erstellen verwendet man den Befehl
`newglossaryentry{<label>}{<settings>}`.

Ein erstellter Glossareintrag kann mit folgenden befehlen referenziert werden:

  `gls{<label>}`     Referenziert den angegebenen Begriff und erstellt einen Link zum Glossareintrag.
  `glspl{<label>}`   Referenziert den Plural des angegebenen Begriffs falls vorhanden und erstellt einen Link zum Glossareintrag.
  `Gls{<label>}`     Referenziert den angegebenen Begriff mit großem Anfangsbuchstaben und erstellt einen Link zum Glossareintrag
  `Glspl{<label>}`   Referenziert den Plural des angegebenen Begriffs mit großem Anfangsbuchstaben falls vorhanden und erstellt einen Link zum Glossareintrag.
