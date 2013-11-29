# Die Python-Freundinnen erraten ein Datum

Penny war übelster Laune. Ihre Stimme zitterte, als sie ihrer besten Freundin Poppy ihr Herz ausschüttete.

"Es ist so unfair!" Sie begann zu schluchzen.

"Oh Süße", sagte Poppy, "ich mag es ja nicht sagen, aber du klingst wie der stereotype Teenager."

Penny lächelte schief und putzte sich die Nase. "Ich weiß", sagte sie. "Aber es ist war. Wieso kann ich nicht mit ihm gehen?"

Poppy seufzte. Pennys Mutter Ada hatte ihr verboten, diesen Jungen zu treffen - und das machte nichts als Ärger.

"Naja" erklärte sie "sie denkt, er ist zu alt für dich. Er ist schon fast erwachsen."

Penny rief wütend aus "Aber ich bin reifer als die meisten Erwachsenen. Die Hälfte von ihnen kann nicht mal einen Computer anschalten, geschweige denn ihn so gut programmieren wie ich!"

Das stimmte. Was Penny an Jahren fehlte, machte sie wett mit Talent. Niemand an ihrer Schule kam auch nur annäherend an sie heran, wenn es um Python ging. Selbst die Lehrer wandten sich an sie um Hilfe, wenn sie nicht mehr weiterkamen.

"Du willst nicht wirklich mit ihm ausgehen, oder?" fragte Poppy. "Er hat doch lauter Pickel."

Penny seufzte. "Nein. Nicht wirklich. Und er hat eine wirklich unangenehme Lache. Aber ich will das Recht haben, mit ihm auszugehen. Das ist es, was unfair ist."

"Warte mal..." Poppy dachte nach. Sie konnte zwar nicht so gut programmieren wie Penny, dafür ###hartnäckigkeit, querdenkerin, unorthodoxe Lösungen### "Das könnte wirklich unfair sein.."

Penny schaute von ihrem zerkrumpelten Taschentuch auf. "Ich weiß," sagte sie.

"Nein, ich meine buchstäblich ungerecht." Poppy hielt inne, sie wußte, dass sie sich hier auf gefährliches Pflaster begab. "Was ist der genaue Altersunterschied deiner Eltern?"

Pennys Augen begannen zu glitzern - nicht vor Tränen, sondern mit der Andeutung einer schelmischen Ideen. "Das finden wir raus," grinste sie. "Holen wir den Raspberry Pi""

## Die Differenz-Maschine

"Okay", sagte Penny und wischte ihre Nase am Ärmel ab. "Wie fangen wir an?"

So arbeiteten sie am besten - Penny saß im Schneidersitz vor dem Computer und hackte den Code ein, während Poppy im Zimmer herumwandelte und über ihre Probleme philosophierte.

"Zuerst" sagte Poppy. "Hat Python eine Möglichkeit, mit Datum und Uhrzeiten umzugehen?"

"Oh ja." und Penny begann zu tippen.

<pre lang="python">
from datetime import date
</pre>

"Im Prinzip alles, was man tun muss, ist Python gleich zu Beginn zu sagen, welche Spezialfunktionen wir benützen wollen. In diesem Fall gibt es eingebaute Funktionen namens 'datetime', aber wir wollen nur die, die mit Datumsangaben zu tun haben.

"Können wir das testen?" sagte Poppy vorsichtig. Sie wollte immer sicherstellen, dass alles funktionierte.

"Sicher!"

<pre lang="python">
print date.today()
</pre>

"Das sollte uns das Datum von heute anzeigen." Penny startete das Programm und wurde belohnt mit 

<pre>2014-03-24</pre>

"Hm," sagte Poppy. "Wieso ist das in so einer komischen Reihenfolge geschrieben?"

Penny liebte es, ihrer Freundin etwas zu erklären. Sie genoß ihren Gesichtsausdruck, wenn sie etwas kapierte.

"Die Amerikaner schreiben bei Daten den Monat zuerst - 12/11 heißt zum Beispiel 11. Dezember. Aber für Europäer bedeutet es 12. November. Um niemanden zu verwirren, schreiben die meisten Computer Daten als 'Jahr-Monat-Tag'."

"Oh, das klingt logisch. Also, das ist das Datum von heute - wie erzeugen wir ein bestimmtes Datum?"

"Ganz einfach," Pennys Hände tanzten über die Tastaur und erzeugten ein angenehmes Klackern.

<pre lang="python">
my_birthday = date(2000, 02, 29)
</pre>

"Wir erzeugen eine Variable und weisen ihr ein Datumsobjekt zu. Das ist alles."

"In Ordnung, wann ist der Geburtstag des Pickeljungen?"

"Als ob ich das wüßte!" rief Penny.

Poppy schaute sie scharf an und zählte innerlich bis zehn.

Penny gab auf als Poppy bei 7 war und flüsterte "15. Januar 1998."

"Urgh! Er ist letztes Jahrhundert geboren!"

"Halt die Klappe." Sie fügte die Variable hinzu.

<pre lang="python">
his_birthday = 
</pre>

#### Ergänze den Geburtstag des Jungen

"So, dein Geburtsdatum, sein Geburtsdatum. Wie bestimmen wir, wieviel älter er ist?"

Penny dachte eine Sekunde nach.

"Python is normalerweise richtig gut in Mathe. Was passiert, wenn wir..." Sie brach ab, versunken im Code.

#### Wie würdest du die Differenz aus zwei Daten ausrechnen?

Die Tastatur klackerte unter Pennys schnellem Tippen.

<pre lang="python">
difference = my_birthday - his_birthday
print "The difference is " + str(difference.days)
</pre>

"Der Unterschied ist wieder ein Datumsobjekt - und das können wir fragen, wieviele Tage es hat. Wir müssen Python aber sagen, dass es es in einen String - eine Zeichenkette - verwandeln soll, damit es richtig ausgedruckt wird."

Sie ließ das Programm laufen.

#### Was passiert, wenn du das Programm auf deinem Computer laufen lässt?

Poppy quietschte "Er ist uuuuralt!"

Penny funkelte sie an: "Es ist nur so schlimm aus, weil es in Tagen ausgegeben wird. Nicht in Jahren und Monaten."

Poppy lehnte sich zurück und zwirbelte eine Haarsträhne zwischen ihren Daumen. "Hm, ein Jahr hat 365 Tage..."

"Vergiss nicht die Schaltjahre", sagte Penny, die da sehr pingelig war. 

"Okay, 365 und ein Viertel."

"Gut, das ist einfach auszurechnen. Ich nehm die Zahl der Tage und teile sie durch 365,25."

<pre lang="python">
print difference.days / 365.25
</pre>

Penny musste zugeben, dass es nicht viel Unterschied machte. Es sah immer noch ziemlich übel aus.

Poppy grinste. "Okay, dann schauen wir mal, was es zu deinen Eltern sagt."

Penny zermarterte sich das Hirn. "Meine Mutter wurde am 17. Oktober 1975 geboren - und Papa am 24. Dezember 1972."

Sie gab die Daten ein.

Penny schnappte nach Luft. "Meine Eltern sind so scheinheilig!" Die beiden Mädchen kicherten.

Penny tätschelte ihren Raspberry Pi. "Dafür haben wir Computer - um komplizierte Dinge einfach zu machen!"

Sie wandte sich an ihre Freundin, "Machen wir deine Eltern als nächstes!"

Die Stimmung im Zimmer änderte sich sofort dramatisch. Poppys Erinnerungen an ihren Vater waren immer noch frisch und schmerzhaft.

"Pops", sagte Penny sanft.

"Nein, schon in Ordnung," sagte ihre Freundin mit Tränen in den Augen. "Aber ich denke, das ist genug programmiert für heute."

## Ein Mitternachtsalptraum

Es war fast Mitternacht, als Poppy aus dem Bett schlüpfte. Schnell schaltete sie ihr Telefon auf lautlos. Sie horchte, ob ihre Mutter den Wecker gehört hatte. Alles ruhig.

Poppy schlich zu ihrem Raspberry Pi und schaltete ihn an.

Sanft berührte sie die Tastatur und fügte eine kleine Änderung in den Python Code ein, den Penny vorher geschrieben hatte. Sie prüfte und prüfte nochmal den Code. Auf keinen Fall konnte sie sich Fehler erlauben.

Verstohlen sich umschauend, gab sie das heutige Datum ein - 24. März 2013.

Sie schloß die Augen, holte tief Atem und drückte die Enter-Taste.

Eine ganze Minute lang wagte sie nicht, die Augen zu öffnen. Sie wünschte es sich so dringend, aber wußte, dass das mehr Gefühle wecken würde, als sie verarbeiten konnte.

Schließlich nahm sie all ihren Mut zusammen und öffnete die Augen. Da, leuchtend auf dem kleinen Bildschirm waren die Worte, die alles real machten - und bei denen etwas in ihr starb. 

<pre>Dein Vater ist verschwunden seit: 101 Tagen.</pre>

#### Kannst du herausfinden, wann Poppys Vater verschwunden ist?

