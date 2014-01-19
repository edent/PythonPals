# Die Python-Freundinnen und der Briefstau

Poppys Mutter Ada war **nicht** erfreut.

"Das interessiert mich nicht," schrie sie ins Telefon, "Wieso ist es immer ich, die es wieder einrenken muss?"

Sie tobte weiter. Penny und Poppy saßen im Wohnzimmer. Obwohl der Fernseher auf voller Lautstärke lief, konnten sie Teile der Unterhaltung mithören.

Plötzlich ging die Tür auf und Ada stürmte herein. "Was macht ihr zwei gerade?" fragte sie.

"Nur Fernsehen," sagte Poppy. "Es ist die Folge, wo sie..." aber bevor sie ihren Satz noch zu Ende bringen konnte, unterbrach ihre Mutter sie.

"Nichts also. Dann könnt ihr euch nützlich machen."

"Aber Mama!"

"Aber nix. Ich muss in die Stadt um... also in die Stadt. Ich habe keine Zeit, diese ganzen Dankesbriefe zu tippen. Das müsst ihr machen."

Penny strahlte die Mutter ihrer Freundin an. "Kein Problem, machen wir doch gerne!"

"Gut, das wäre also geklärt. Und bitte habt sie fertig, bis ich wieder da bin. Ich muss sie losschicken und ich..." sie sah aus als wäre sie den Tränen nahe.

"Keine Sorge, Mama, wir machen sie fertig. Versprochen!"

Ada versuchte zu lächeln, küsste ihre Tochter auf die Stirn und ging, ohne noch etwas zu sagen.

Penny wandte sich an ihre Freundin und sagte: "Dann mal los!"

Sie liefen in Adas Arbeitszimmer. Es war spärlich eingerichtet, aber auf dem Schreibtisch stapelten sich die Papiere. An der Ecke stand eine Vase voll lang vertrockneter Blumen.

"Worum geht es eigentlich, Poppy?" fragte Penny.

"Es gibt richtig eklige Krankheiten und Mama sammelt Spenden damit junge Frauen gesund bleiben. Also, wo hat meine Mutter Stifte und Papier?"

Penny sah Poppy scharf an, als ob sie sie gerade zu einem Marathon oder einer ähnlich sinnfreien Sportart aufgefordert hätte.

"Du willst das nicht etwa alles von Hand schreiben?" fragte sie. Sie holte den Raspberry Pi aus ihrem weißblauen Schulrucksack und legte ihn auf den Tisch.

Poppy reichte Penny einen USB-Stick, der sich unter einem Stapel Zeitungsauschnitte versteckt hatte. "Die Spender sollten alle hier drauf sein."  

Penny steckte den USB-Stick in den Raspberry Pi und klickte herum, bis sie die Datei gefunden hatte.

"Aha, da ist sie ja!" sagte sie triumphierend. "Lass sie mich schnell öffnen."

Einen Moment später erschien der Text auf dem Bildschirm. Er enthielt die Namen aller Spender und wieviel sie gespendet hatten.

<pre>Anna 2.50
Beth 5.93
Cath 23.50
Dom 15
Erik 3.14
...
</pre>
([Du kannst diese Datei hier herunter laden](https://github.com/edent/PythonPals/blob/master/donors.txt))

Die Datei scrollte und scrollte. 

Poppy kreischte: "Das sind ja hunderte! Das haben wir nie im Leben fertig, bis meine Mutter zurück kommt. Nicht mal du tippst so schnell."

"Poppy," sagte Penny. "Ich will ja nicht gemein sein, aber manchmal stehst du echt auf der Leitung." Laut und ganz langsam sagte sie "Wir haben einen Computer, du Nuß! Wir lassen den Pi für uns die Arbeit erledigen."

Poppy schaute bedröppelt. "Oh...ja. Vermutlich können wir das mit Python in ein paar Minuten schaffen."

"Miss Poppy, damit haben Sie den Nagel auf den Kopf getroffen," sagte Penny geziert.

Als sie fertig gelacht hatten, hockte sich Penny mit angezogenen Beinen auf einen Stuhl. Poppy kletterte aufs Fensterbrett, um gleichzeitig auf den Bildschirm und ihre Freundin zu sehen.

Poppy fing an: "Nun, teilen wir das Ganze mal auf in leicht handlebare Teile. Wir haben eine Datei mit Namen und Geldbeträgen, korrekt?"

"Korrekt."

"Okay, dann wollen wir jeweils eine Zeile dieser Datei lesen und dann einen Brief mit diesen Infos erzeugen."

"Das sollte ziemlich einfach sein, Poppy." Penny knackte mit den Fingern und fing an zu tippen. Sie fühlte sich am besten, wenn ihre Finger über eine Tastatur flogen. Während sie tippte, redete sie.

"Eine Datei zu öffnen braucht nur eine Zeile Code. Du sagst Python, wo die Datei ist und ob wir sie lesen oder reinschreiben wollen."

<pre lang="python">
textfile = open('donors.txt', 'r')
</pre>

Sie speicherte das Programm und starte es. Die Datei erschien in der Konsole.

"Großartig," grinste Poppy. "Teil Eins erledigt. Jede Zeile enthält nur den Namen der Person und wieviel sie gespendet hat, richtig?"

"Yup. Also können wir die Datei Zeile für Zeile lesen und dann mit jeder Zeile etwas tun. Schau!"

Sie löschte ihren Code und fing nochmal an

<pre lang="python">
textfile = open('donors.txt', 'r')
lines = textfile.readlines()

for line in lines:
   chunks = line.split()
   spender_name = chunks[0]
   spender_betrag = chunks[1]
   print spender_name
</pre>



"So", sagte sie. "Wir öffnen die Datei. Wir holen uns jede Zeile. Wir teilen die Zeile am Leerzeichen auf. Von diesen zwei Teilen nennen wir den ersten spender_name und den zweiten spender_betrag. Nur um sicherzugehen, drucken wir noch den Namen des Spenders."

Ihre Finger schwebten über der Tastatur. Gerade als sie wieder das Programm starten wollte, unterbrach Poppy sie.

"Halt mal. Warum ist spender_name Teil Null? Sollte das nicht Eins - und der Betrag Zwei sein?"

"Ja," sagte Penny. "In Python - und den meisten anderen Programmiersprachen - fangen Listen bei 0 an."

"Das ist ja doof," sagte Poppy.

"Man gewöhnt sich dran."

"Aber was ist der Witz dran?"

"Denk mal an Jahre. Wir sind jetzt im zweiten Jahrtausend. Das erste Jahr des zweiten Jahrtausend war 2000. Das zweite Jahr war 2001, das dritte 2002 und so weiter."

"Oh!" sagte Poppy, als ihr ein Licht aufging. "Das ergibt Sinn..."

"Wie ich sagte, man gewöhnt sich dran. Jetzt, wo waren wir?"

"Wir wollten so etwas schreiben wie "Liebe(r) spender_name, danke für deine Spende, bla blah blah etc."

"Du bist soo beredt!" kommentierte Penny sarkastisch. Sie tippte weiter und ergänzte die folgenden Zeilen.

<pre lang="python">
   letter = "Liebe(r) " + spender_name + ", "
   letter += "danke für deine Spende von " + spender_betrag
   print letter
</pre>

"Wenn du die zwei Zeichenketten addierst," erklärte sie "hängt Python sie einfach aneinander - das nennt man Concatenation."

"Aber wozu sind diese plus-istgleich-Zeichen da?"

"Wenn du einer existierenden Variable etwas hinzufügen willst, könntest du sagen 'wasauchimmer = wasauchimmer + etwas' aber es geht viel schneller zu sagen 'wasauchimmer += etwas'"

"Oooooooh!" schnaufte Poppy - die sehr gut darin war, aus ihrer Sicht hilfreiche Kommentare einzuwerfen. "Schreib 'großzügige Spende'!"

"Aber manche Leute waren nicht besonders großzügig."

"Das lässt sich leicht lösen. Wir schreiben nur großzügig, wenn sie mehr als 20 Euro gespendet haben."

"Natürlich!" rief Penny. "Warum hab ich nicht daran gedacht?"

"Hey, deshalb sind wir so gute Freundinnen - ich bin das Hirn und du bist..." Poppy brach ab.

"die Tipse?" sagte Penny verächtlich, als sie wütend in die Tasten haute.

<pre lang="python">
   letter += "Danke für deine "
   if float(spender_betrag) > 10:
</pre>

"Was bedeutet 'float'?" fragte Poppy.

Penny drehte sich, so dass sie ihrer Freundin ins Gesicht schaute. "Ok, unser Python-code hat einen String Text aus der Datei gelesen, korrekt?"

"Yup."

"Also denkt es, dass '5' das Zeichen '5' ist und nicht die _Zahl_ '5'."

"Ah! Wenn du also '5'+'2' addierst, ergäbe das '52'."

"Bingo! Deshalb müssten wir das Zeichen in eine Zahl 'casten'. Stell dir das als Zauberspruch vor, mit dem du jemand in einen Frosch verwandelst."

Poppy ging ein Licht auf. "Kapiert! Wenn du also '`float(spender_betrag)`' schreibst, sagst du Python 'Stell dir das als Zahl vor'"

Penny nickte und tippte weiter.

<pre lang="python">
   letter += "Danke für deine "
   if float(spender_betrag) > 10:
      letter += "großzügige "
   letter += "Spende von " + spender_betrag
   print letter
</pre>

"Es ist ganz einfache Mathe. Du kannst > benützen wenn etwas größer als etwas anderes ist und < für weniger als."

Poppy lugte auf die Tastatur. Sie putzte ihre Brille und schaute nochmal. "Und wo ist das Größer-Gleich-Zeichen?"

"Das gibt es nicht. Du musst einfach `=` danach tippen, wie `>=` oder `<=`"

"Schick. Upps, keine Kritik, aber du hast das Euro-Zeichen nach dem Betrag vergessen."

Flink änderte Penny die Zeile zu:

<pre lang="python">
   letter += "Spende von " + spender_betrag + " €"
</pre>

Aber als sie diesmal das Programm starteten, passierte etwas unerwartetes.

#### Lass den Code auf deinem Computer laufen

<pre>SyntaxError: Non-ASCII character '\xc2' in file letter.py on line 9, but no encoding declared; see http://www.python.org/peps/pep-0263.html for details</pre>

Die Mädchen fluchten im Chor. Immmer kam ihnen so etwas dazwischen.

"Computer" meinte Penny, "sind manchmal richtig dämlich. Sie hassen es, wenn man komische Zeichen benutzt."

Poppy dachte darüber nach: "Dann müssen wir ihm also verraten, welche Zeichen wir benützen?"

"Sehr richtig. Wir brauchen genau eine Zeile am Anfang unseres Programms." Penny scrollte hoch und tippte die magische Formel.

<pre lang="python">
# This Python file uses the following encoding: utf-8
</pre>

"Das sollte es erschlagen."

"Also, wir haben den Namen, wieviel sie gespendet haben und eine Nachricht. Was brauchen wir noch?"

"Nichts!" sang Penny. "Schauen wir weiter fern."

"Wie wäre es," fuhr Poppy fort, ihre Freundin ignorierend, "wenn wir ihnen noch sagen, was mit ihrer Spende gekauft wurde?"

"Oder wir könnten weiter fernsehen!"

"Nein. Wenn schon, dann machen wir es richtig."

"Ookay!" schnupfte Penny. "Wieviel kostet eine Impfung?"

Poppy kramte auf dem Schreibtisch ihrer Mutter, alle juristischen Sachen dort gezielt ignorierend, bis sie das Blatt fand, nach dem sie gesucht hatte.

"1,34 Euro pro Impfung."

"Das ist einfach," sagte Penny. "Wir erzeugen eine Variabe für die Impfkosten und teilen den Spendenbetrag dadurch.

<pre lang="python">
impfung_kosten = 1.34
impfungen_gekauft = float(spender_betrag) / impfung_kosten
letter += ".  Damit konnten wir " + str(impfungen_gekauft) + " Impfungen bezahlen."
</pre>

"Jetzt müssen wir noch diese Zahl zurück in einen String casten, den wir dann in den Brief setzen." sagte Penny.

Poppy grinste süffisant. "Da wirst du ein Problem kriegen, Pen."

"Was zur Hölle meinst du damit?"

"Starte den Code und schau..."

#### Lass den Code auf deinem Computer laufen - was passiert?

Penny startete das Programm. Sie starrte auf die Ausgabe, rümpfte ihre Nase und rief "Scheibenkleister!"

"Das Problem ist," seufzte Poppy, "dass Computer _wirklich_ genau sind. Viel genauer als Menschen."

"Dumme Menschen," murmelte Penny.

"Also, können wir das nicht einfach abrunden mit der 'round()'-Funktion?" sagte Poppy, während sie die Sehnsucht ihrer Freundin, die Menschheit zu transzendieren und mit den Maschinen eins zu werden, demonstrativ ignorierte.

Penny tippte los.

<pre lang="python">
round( float(spender_betrag) / impfung_kosten )
</pre>

"Damit haben wir alles, oder?" fragte Penny traurig.

"Yup. Lass uns die Briefe ausdrucken und weiter fernsehen. Wenn wir Glück haben, haben wir nicht viel verpasst."

Ein Weilchen später kam Ada zur Tür herein, in sichtlich besserer Laune.

"Mädels, wo seid ihr?"

"Hier, Mama," rief Poppy.

"Was zum Teufel macht ihr vor dem Fernseher?" schimpfte Ada. "Ich dachte ich hätte euch gebeten..."

"Chill mal, Mama," unterbrach sie ihre Tochter. "Alles erledigt."

"Was?" rief Ada verblüfft. "Wie könnt ihr in dieser Zeit die ganzen Briefe geschafft haben? Das waren mindestens hundert."

"128." fiel Penny ein.

Sie überreichten der sprachlosen Ada einen Stapel Papier.

"Aber das ist fantastisch!" rief sie, "was für tolle Briefe - und wie schlau von euch, noch einzufügen, wieviele Impfstoffe es für die Spende gibt."

"Ach, nicht der Rede wert." sagte Poppy lässig. "Jetzt sind wir aber völlig k.o. von der ganzen Arbeit. Können wir ein Eis haben?"

Ada strahlte. "Nach dieser Aktion gibt es Rieseneisbecher für euch beide!"

"Mit Schokoladenstreuseln?"

"Übertreib mal nicht, junge Dame!" Und damit wirbelte sie in die Küche.
