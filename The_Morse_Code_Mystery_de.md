# Das Geheimnis des Morse-Codes

## Strandgut

Die Wellen krachten wie wütend auf den Strand und der Regen schien von allen Seiten gleichzeitig zu kommen. Eine plötzliche Böe blies einen dünnes Rinnsal direkt in Poppys Kragen.

"Dieses Wetter ist beschissen" fauchte sie.

"Nur noch fünf Minuten," schrie Penny.

Poppy machte sich kleiner, so dass sie auf Augenhöhe mit ihrer Freundin Penny war. Penny war eh schon die kleinere der zwei, aber jetzt starrte sie gebückt in die Brandung.

"Penny, was machst du da? Es ist kalt, naß, und viel wichtiger noch" sie machte eine dramatische Pause, um ihren Worten mehr Nachdruck zu verleihen: "wir verpassen den "Marzipan Marathon" im Fernsehen!"

Ihre Freundin kicherte - sie konnten beide die Kochsendungen im Fernsehen nicht ausstehen, aber sie waren sich einig darin, dass etwas unheimlich zwanghaftes darin lag, einen Mann sein Körpergewicht in Kuchen essen zu sehen.

"Da" rief Penny und deutete auf ein Stück Ufer etwas entfernt. "Ich hab dir erzählt, dass hier lauter interessante Sachen angespült werden, wenn es stürmt. Pack es!"

Obwohl sie die ältere der zwei Freundinnen war, wurde Penny immer für Poppys jüngere Schwester gehalten. Daher genoß sie die Gelegenheit, einmal ihrer Freundin Befehle zuzubrüllen.

Poppy fischte das große blaue Tuch aus dem Wasser und drehte sich um. "Können wir jetzt bitte reingehen?" jammerte sie. "Es ist kalt und nass..."

Bevor sie den Satz zuende bringen konnte, rief Penny: "Schau, schau dir das Tuch an!"

Sie starrten beide das abgenutzten Leintuch an. Es war übersäht mit seltsamen weißen Zeichen.

"Gehen wir nach Hause und finden heraus, was das ist," sagte Poppy. Und damit fing sie an, zum Haus ihrer Mutter zu rennen.

"Genau das wollte ich gerade sagen!" rief Penny, als sie ihr langsam den Strand entlang hinterhertrottete.

## Pi Power

"Mögt ihr eine Suppe, Mädels?" fragte Poppys Mutter Ada. Sie war es gewöhnt, dass die beiden hereinstürmten und Hunger hatten.

"Keine Zeit, Ada, danke," sagte Penny atemlos. "Wir müssen herausfinden, was das ist."

"Hmmm, das sieht mir wie guter altmodischer Morse-Code aus," sagte Ada nach einem kurzen Blick auf das Tuch. "Wo um alles in der Welt habt ihr das gefunden?"

"Könnten wir ein bißchen Suppe mit Croutons haben? Und vielleicht Käse? Haben wir noch Chips?" rief Poppy als die Mädchen die Treppe raufsausten.

Sie schalteten den Raspberry Pi ein. Er war ein Geburtstagsgeschenk von Poppys Vater. Eines der wenigen Dinge, die ihr geblieben waren, um sich an ihn zu erinnern. Gerade als das Linux bootete, ließ ein Donnerschlag das ganze Hause erbeben. Die Lampen flackerten und gingen aus.

Eine Sekunde später gingen sie wieder an, was blieb, war ein seltsam verbrannter Geruch im Zimmer.

"Oh nein," stöhnte Penny, "der Router!"

Wo der Internet-Router gewesen war, befand sich nur noch ein Klumpen geschmolzenes Plastik und Metall.

Poppy sagte ein Wort, das, wenn es ihre Mutter gehört hätte, sofortigen Taschengeldentzug hervorgerufen hätte. "Wie sollen wir herausfinden, was Morse-Code ist, wenn wir nicht Online kommen?"

Die Mädchen saßen benommen da. Kein Internet. Kein Facebook. Und viel wichtiger noch, keine Wikipedia!

Sie schauten auf ihre Telefone, aber wie üblich war darauf kein Cent Guthaben mehr.

Poppy sah sich verlassen im Zimmer um. Der kleine Raum war das Arbeitszimmer von Poppys Vater gewesen, bevor er... Bevor eben. Sie ließ ihren Blick schweifen über die Regale, auf der Suche nach etwas, das helfen würde - selbst ein altmodisches Wählmodem wäre genug.

Penny zirpte plötzlich: "Pops, was ist diese Brockhaus Enyzklopädie?" Sie deutete auf eine eindrucksvolle Sammlung ledergebundener dicker Bände im Regal.

"Keine Ahnung," schniefte Poppy niedergeschlagen.

"Naja, ich weiß, die gehört deinem Vater, aber Enzyklopädie klingt ein bißchen wie Wikipedia und ich frage mich..."

"Na klar! Schnell, welcher der Bände hat ein 'M' aufgedruckt?" Poppy lächelte. Man sah sie selten lächeln zur Zeit und Penny genoß die Gelegenheit, ihre Freudin aufzumuntern.

Sie zogen den staubigen Band aus dem Regal und öffneten ihn auf gut Glück. 

"Wo ist die Suchfunktion bei diesem Ding?" witzelte Penny.

"Möbius, Mormon, Morse!"

Dort, auf einer ganzen Seite der Enzyklopädie, fanden sie eine Anleitung für Morse-Code.

Die Mädchen schalteten den Raspberry ein und warteten darauf, dass er bootete. 

"Die wichtigste Sache, die es beim Programmieren zu beachten gilt,"  imitierte Poppy Herrn Schneider, ihren unfassbar langweiligen Informatiklehrer.

"...ist Planung!" vollendete Penny den Satz ihrer Freundin.

"Wir wollen ein Programm, das uns jeweils einen Morse-Code-Buchstaben eintippen lässt und uns die deutsche Übersetzung zeigt."

Penny griff zur Tastatur. Ihr war schon klar, dass sie den Hauptteil der Tipperei erledigen würde während Poppy auf ihre Fehler hinwies. Herrn Schneider zufolge war dieses Konzept als "Pair Programming" bekannt. Sie hielt nicht viel davon.

"Als erstes", sagte Poppy, "lass uns ein Wörterbuch Deutsch/Morse Code anlegen."

Pennys Hände flogen über die Tastatur, als ihre Freundin ihr die Punkte und Striche aus dem Buch vorlas.

<pre lang="python">
morse = {  '.-'  :'A', '-...':'B', '-.-.':'C', '-..' :'D', '.'   :'E',
           '..-.':'F', '--.' :'G', '....':'H', '..'  :'I', '.---':'J'
        }
</pre>

#### Kannst du den Rest des Wörterbuchs selbst programmieren?

Poppy seufzte: "Warum zum Teufel richtest du die ganzen Buchstaben gleich aus?"

"Es hilft mir beim Denken," verteidigte sich Penny."Ich hab's nun ma gern ordentlich. Und Python kümmert es nicht, wie ich die Sachen formatiere."

"Okay, testen wir schnell, ob es funktioniert," sagte Poppy.

"Wir fordern den Benutzer auf, ein Morsezeichen einzugeben. Dann lässt es sich einfach im Wörterbuch nachschlagen, " sagte Penny.

<pre lang="python">
get_code = raw_input('Gib ein Morse-Zeichen ein ')
print morse[get_code]
</pre>

Sie ließ das Programm laufen. Wie erwartet, fragte es sie nach einem Zeichen. Sie gab die Folge ".-", drückte Enter und wurde mit einem leuchtenden "A" auf dem Bildschirm belohnt.

#### Macht dein Programm das Gleiche?

"Guter Anfang, " sagte Poppy. "Aber es wird eine Heidenarbeit, immer ein Morsezeichen einzutippen, dann Enter zu drücken und danach alle Buchstaben wieder zusammenzusetzen."

Penny dachte einen Moment nach. Sie wußte, dass ihr etwas besseres einfallen würde.

"Wie wäre es, wenn wir alle Zeichen einlesen und dann anhand der Leerzeichen aufteilen?" schlug sie vor. 

Poppy blickte verwirrt. "Was meinst du genau, Pen?"

Penny rief direkt Python auf um zu zeigen, was ihr vorschwebte.

<pre>
Python 2.7.3 (default, Aug  1 2012, 05:14:39) 
[GCC 4.6.3] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> </pre>

Am Prompt tippte sie:

<pre lang="python">
>>> "Das ist ein Test".split()
</pre>

"Wenn ich damit richtig liege, gibt uns die Split-Funktion eine Liste aller Wörter."

Sanft drückte sie auf Enter. 

<pre>['Das', 'ist', 'ein', 'Test']</pre>

"Yeah!" riefen die beiden Mädchen simultan.

"Damit haben wir also jedes Morsezeichen in einer Liste, dann wollen wir sie im Wörterbuch nachschlagen."

"Korrekt. Schickerweise ist es supereinfach etwas für jede Sache in einer Liste zu machen - schau,"

Penny tippte wieder direkt in die Python-Konsole.

<pre lang="python">
>>> list_of_words = "Dies ist ein Test".split()
>>> for item in list_of_words:
... print item
</pre>

Aber diesmal, als sie Enter drückte, erschien eine Fehlermeldung!

<pre>
  File "&lt;stdin&gt;", line 2
    print item
        ^
IndentationError: expected an indented block
</pre>

Diesmal war Penny mit Fluchen an der Reihe.

#### Kannst du herausfinden, was Penny und Poppy falsch gemacht haben?

"Wisch dir dieses Grinsen vom Gesicht! Ja, Leerzeichen und Einrückung sind wichtig in Python. Aber generell ist es in Ordnung, wenn ich meinen Code so formatiere, wie ich es mag."

Sie versuchte es nochmal und haute dabei so hart auf die Leertaste, wie diese es gerade noch aushielt.

<pre lang="python">
>>> list_of_words = "Dies ist ein Test".split()
>>> for item in list_of_words:
...    print item
</pre>

Diesal war das Ergebnis deutlich zufriedenstellender.
<pre>
... 
Dies
ist
ein
Test
>>> 
</pre>

"Geht ja." murmelte Poppy vor sich hin. Schnell tauschten sie die letzten Zeilen ihres Programms aus, sodass da nun folgendes stand:

<pre lang="python">
get_code = raw_input('Gib ein Morse-Zeichen ein ')

code_list = get_code.split()

for item in code_list:
   print morse[item]
</pre>

"Ok," sagte Penny, "jetzt lass mal sehen, was dieses mysteriöse blaue Tuch zu bedeuten hat..."

<pre>... --- ... ... -.-. .... .. ..-. ..-. -... .-. ..- . -.-. .... .. --. . .-. .- ..- ..-. .. -. ... . .-..</pre>

Sie prüften nochmal und nochmal, was sie eingetippt hatten.

"Bereit?" fragte Poppy.

"Los," sagte Penny und drückte Enter.

####  Kannst du das Morse-Code-Räsel lösen?

## Die Retterinen des Tages

"Gut gemacht," sagte die Bürgermeisterin. "Ohne eure Hilfe wäre dieser Segler ganz schön lange festgesessen."

Penny und Poppy grinsten. Alles war in so einem Rausch passiert, von Laufenlassen ihres Programms zum Herbeischreiben von Poppys Mutter, zum Alarmieren der Küstenwache, bis zum Verfolgen wie der schiffbrüchige Segler gerettet wurde. Sie waren vom Fernsehen interviewt worden und der Clip hatte hunderte von YouTube-Likes.

Es gab sogar eine Facebook-Seite mit Danksagungen!

Die Bürgermeisterin hatte beschlossen, dass solche feinen engagierten Bürgerinnen eine Belohnung verdienten - und hatte sie ins Rathaus eingeladen.

"Wer hätte gedacht, dass zwei Mädchen Morse-Code kennen?" sagte die Bürgermeisterin. "Habt ihr das in der Schule gelernt?"

Poppy fixierte sie mit eisernem Blick. "Nein. Das haben wir uns selbst beigebracht."

Die Bürgermeisterin linste über ihre Brille. "Aber ihr hattet doch sicher Hilfe von jemand? Einem älteren Bruder vielleicht?"

Poppy kannte Pennys Gesichtsausdruck und antwortete, bevor ihre Freundin die Beherrschung verlor. "Sie werden feststellen," sagte sie zuckersüß, "dass **Frauen** keine Hilfe von **Jungen** brauchen!

Poppy fühlte, dass Penny ihre Hand nahm. Sie fing an zu glucksen, als ihre Hand in festen, aber genauen Abständen gedrückt wurde.

<pre>-.. .- .-. ..- -- -... .. ... - -.. ..- -- . .. -. . -... . ... - . ..-. .-. . ..- -. -.. .. -.</pre>

