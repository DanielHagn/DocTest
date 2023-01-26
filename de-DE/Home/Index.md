# Markdown: Syntax

**Anmerkung:** Dieses Dokument ist selbst in Markdown geschrieben; Sie
Sie können [die Quelle dafür sehen, indem Sie '.text' zur URL hinzufügen](/projects/markdown/syntax.text).

----

## Überblick

### Änderungen zu Version 0.0.1

* Es gab keine Änderungen zur Version 0.0.1

### Philosophie

Markdown soll so einfach zu lesen und zu schreiben sein, wie es möglich ist.

Die Lesbarkeit wird jedoch über alles gestellt. Ein Markdown-formatiertes
formatierte Dokument sollte als reiner Text veröffentlicht werden können, ohne dass es aussieht
ohne dass es so aussieht, als ob es mit Tags oder Formatierungsanweisungen versehen worden wäre. Während
Markdown-Syntax von mehreren bestehenden Text-zu-HTML-Filtern beeinflusst wurde
Filter - einschließlich [Setext](http://docutils.sourceforge.net/mirror/setext.html), [atx](http://www.aaronsw.com/2002/atx/), [Textile](http://textism.com/tools/textile/), [reStructuredText](http://docutils.sourceforge.net/rst.html),
[Grutatext](http://www.triptico.com/software/grutatxt.html), und [EtText](http://ettext.taint.org/doc/) -- die größte Quelle der Inspiration für
Inspiration für die Markdown-Syntax ist das Format von Klartext-E-Mails.

## Blockelemente

### Absätze und Zeilenumbrüche

A paragraph is simply one or more consecutive lines of text, separated
by one or more blank lines. (A blank line is any line that looks like a
blank line -- a line containing nothing but spaces or tabs is considered
blank.) Normal paragraphs should not be indented with spaces or tabs.

The implication of the "one or more consecutive lines of text" rule is
that Markdown supports "hard-wrapped" text paragraphs. This differs
significantly from most other text-to-HTML formatters (including Movable
Type's "Convert Line Breaks" option) which translate every line break
character in a paragraph into a `<br />` tag.

When you *do* want to insert a `<br />` break tag using Markdown, you
end a line with two or more spaces, then type return.

### Headers

Markdown supports two styles of headers, [Setext] [1] and [atx] [2].

Optionally, you may "close" atx-style headers. This is purely
cosmetic -- you can use this if you think it looks better. Die
schließenden Hashes müssen nicht einmal mit der Anzahl der Hashes übereinstimmen
die zum Öffnen des Headers verwendet wurden. (Die Anzahl der öffnenden Hashes
bestimmt die Ebene der Kopfzeile.)

### Blockzitate

Markdown verwendet `>`-Zeichen im E-Mail-Stil für Blockzitate. Wenn Sie
mit dem Zitieren von Textpassagen in einer E-Mail vertraut sind, dann wissen Sie
wissen Sie, wie man ein Blockzitat in Markdown erstellt. Es sieht am besten aus, wenn du den Text fest
den Text hart umbrechen und ein `>` vor jede Zeile setzen:

> Dies ist ein Blockquote mit zwei Absätzen. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
> 
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.

Markdown erlaubt es Ihnen, faul zu sein und das ">" nur vor die erste Zeile eines
Zeile eines fest umschlossenen Absatzes zu setzen:

> Dies ist ein Blockquote mit zwei Absätzen. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.

Blockquotes können verschachtelt werden (d.h. ein Blockquote in einem Blockquote), indem
zusätzliche Ebenen von `>` hinzufügen:

> Dies ist die erste Ebene der Anführungszeichen.
>
> > Dies ist ein verschachteltes Blockquote.
>
> Zurück zur ersten Ebene.

Blockquotes können andere Markdown-Elemente enthalten, darunter Überschriften, Listen
und Code-Blöcke:

> ## Dies ist eine Überschrift.
> 
> 1. dies ist das erste Listenelement.
> 2.   Dies ist der zweite Listenpunkt.
> 
> Hier ist ein Beispielcode:
> 
> return shell_exec("echo $input | $markdown_script");

Jeder anständige Texteditor sollte das Zitieren im E-Mail-Stil leicht machen. Für
BBEdit können Sie beispielsweise eine Auswahl treffen und im Menü Text die Option Anführungszeichen erhöhen
Quote Level aus dem Textmenü wählen.

### Listen

Markdown unterstützt geordnete (nummerierte) und nicht geordnete (Aufzählungslisten) Listen.

Ungeordnete Listen verwenden Sternchen, Pluszeichen und Bindestriche -- austauschbar
-- als Listenmarkierungen:

* Rot
* Grün
* Blau

ist äquivalent zu

+ Rot
+ Grün
+ Blau

und:

- Rot
- Grün
- Blau

In geordneten Listen werden Zahlen, gefolgt von Punkten, verwendet:

1.  Vogel
2.  McHale
3.  Parish

Es ist wichtig zu beachten, dass die tatsächlichen Zahlen, die Sie zur Markierung der
Liste verwenden, keinen Einfluss auf die HTML-Ausgabe von Markdown haben. Die HTML
die Markdown aus der obigen Liste erzeugt, ist:

Wenn Sie stattdessen die Liste in Markdown wie folgt schreiben würden:

1.  Vogel
1.  McHale
1.  Parish

oder sogar:

3. Vogel
1. McHale
8. Pfarrei

würden Sie genau die gleiche HTML-Ausgabe erhalten. Der Punkt ist, wenn Sie das wollen,
können Sie Ordnungszahlen in Ihren geordneten Markdown-Listen verwenden, so dass
die Zahlen in Ihrem Quelltext mit den Zahlen in Ihrem veröffentlichten HTML übereinstimmen.
Aber wenn Sie faul sein wollen, müssen Sie das nicht.

Damit Listen schön aussehen, können Sie Elemente mit hängenden Einzügen umbrechen:

* Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
* Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
    Suspendisse id sem consectetuer libero luctus adipiscing.

Aber wenn Sie faul sein wollen, müssen Sie das nicht:

* Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
viverra nec, fringilla in, laoreet vitae, risus.
* Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
Suspendisse id sem consectetuer libero luctus adipiscing.

Listenelemente können aus mehreren Absätzen bestehen. Jeder nachfolgende
Absatz eines Listeneintrags muss entweder um 4 Leerzeichen
oder um einen Tabulator:

1.  Dies ist ein Listenelement mit zwei Absätzen. Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

    Vestibulum enim wisi, viverra nec, fringilla in, laoreet
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sit amet velit.

2.  Suspendisse id sem consectetuer libero luctus adipiscing.

Es sieht schön aus, wenn Sie jede Zeile der folgenden Absätze einrücken
Absätzen einrückst, aber auch hier erlaubt dir Markdown, faul zu sein
faul sein:

* Dies ist ein Listenelement mit zwei Absätzen.

    Dies ist der zweite Absatz des Listeneintrags. Sie müssen
müssen nur die erste Zeile einrücken. Lorem ipsum dolor
sit amet, consectetuer adipiscing elit.

* Ein weiterer Punkt in derselben Liste.

Um ein Blockquote innerhalb eines Listenelements zu setzen, müssen die `>`
Begrenzungszeichen eingerückt werden:

* Ein Listenelement mit einem Blockquote:

    > Dies ist ein Blockquote
    > innerhalb eines Listenelements.

Um einen Codeblock innerhalb eines Listenelements zu platzieren, muss der Codeblock
muss der Codeblock *zweimal* eingerückt werden - 8 Leerzeichen oder zwei Tabulatoren:

* Ein Listenelement mit einem Codeblock:

        <Code kommt hier hin>

