# Die frisierten Bücher

## Die Räumungsdrohung

Die Stimmung in der Schulversammlung war düster. Frau Hopper, die Direktorin machte ein steinernes Gesicht. 

"Es tut mir sehr leid, Kinder," sagte sie, "aber wir können es uns die Schulbibliothek nicht mehr leisten."

Poppy rutschte das Herz in die Hose. Sie hatte so viele Stunden in der Schulbibliothek verbracht. Es war der perfekte Ort, um nach der Schule rumzuhängen oder an regnerischen Mittagen oder auch einfach, wenn sie eine Pause von der Welt brauchte. Einige ihrer besten Freunde waren Charaktere aus Büchern...

Gerade da bemerkte sie, dass Penny die Hand hob. Penny war ihre echte beste Freundin. Immer Mut machend, nicht abgeschreckt von der Situation mit Poppys Vater und immer bereit, unbequeme Fragen zu stellen.

Frau Hopper konnte Pennys wildes Handwedeln nicht mehr ignorieren: "Ja, Penny, hast du eine Frage?"

Penny holte tief Luft und ließ dann ihrem Frust freien Lauf: "Aber alle Kinder benützen die Bücherei und es gibt großartige Bücher da drin und das ist eine völlig blödsinnige Idee!"

"Nachsitzen!" sagte Frau Hopper. "Du kommst nach der Versammlung zu mir."

## 

Poppy lungerte vor Frau  Hoppers Büro herum. Sie lehnte sich an den Türrahmen und strengte ihre Ohren an, um zu hören, was Frau Hopper zu Penny sagte.

"Penny, so redet man nicht mit mir." Die Direktorin klang richtig wütend. "Ich bin es nicht, die entscheidet, wieviel Geld uns die Regierung gibt. Ich muss das beste machen aus dem, was wir haben. Es war die Entscheidung zwischen Schließung der Bibliothek oder Auflösung des Computerraums.

Sie hielt inne. Die Direktorin wußte, wie sehr Penny die Computerstunden liebte - wie konnte sie zwischen den beiden wählen? Es war die Wahl zwischen Pest und Cholera.

"Und jetzt", fuhr die Direktorin fort, "müssen wir anfangen, die Bücher in der Bibliothek zu verkaufen. Hoffentlich verdienen wir damit genug, um einige der Computer aufzurüsten. Als Aufgabe für dein Nachsitzen wirst du eine Liste aller Bücher anfertigen, so dass wir anfangen können, sie zu verkaufen."

Poppy fuhr von den Tür zurück als Penny herausstürmte - ihre Wangen rot vor Scham und ihre Augen voll Tränen.

"Oh Pen!"

"Nun," schniefte Penny, "dann machen wir uns besser an die Arbeit."

"Wir?" fragte Poppy mit gespielter Entrüstung.

"Oh, Entschuldigung, ich dachte, du wolltest deiner besten Freundin helfen, die Bibliothek zu retten?"

Penny steuerte den Flur in Richtung Bibliothek entlang, ihre Schuhe klackerten auf dem billigen Holzfußboden. Poppy zögerte kurz und rannte ihr hinterher. 

## In der Bibliothek

Der archaische Bibliothekscomputer bootete pfeifend. Bedeckt von Staubschichten, alten Karteikarten und von etwas, das wie eine aufgegebene Strickarbeit aussah - der Computer war älter als Penny und Poppy zusammen. So lange brauchte er zum Booten, dass es kein Wunder war, dass kaum ein Schüler je darin Ausleihen vermerkte.

"Du meinst, wir kriegen damit eine Liste aller Bücher hier?" fragte Penny misstrauisch. "Dieses Ding sieht aus als gehörte es ins Museum."

Mit verdächtig akkuratem Timing erzeugte die Festplatte in der Maschine ein langes, kratzendes Geräusch. Auf dem Screen leuchtete die unheilvolle Botschaft: "File allocation table bad drive C."

Poppy starrte auf den Monitor, wo die Fehlermeldung sich standfest weigerte zu verschwinden. "Okay," verkündete sie."Zeit für Blan B."


Sie wühlte in ihrem Schulrucksack. Dort, zwischen ihrem Federmäppchen und einer alten Chipstüte eingezwängt, war ihr Raspberry Pi.

Penny suchte in der Bibliothek herum und fand eine Tastatur. Sie half ihrer Freundin beim Anschließen.

"Python, unser Helfer in der Not?"

"Ja, und ich habe schon einen Plan, wie wir es anstellen. Tippst du?" fragte Poppy.

"Gerne."

"Also, was wir machen wollen..." Poppy hielt inne, um ihre Gedanken zu sammeln. "Jedes Buch hat eine eindeutige Nummer auf dem Buchrücken, korrekt?"

"Genau," sagte Penny, "die ISBN. Jedes Buch bekommt eine, wenn es veröffentlicht wird. Aber das ist nur eine Nummer, das sagt uns nichts über das Buch selbst."

"Ich weiß, aber wir können die ISBN über Internet abrufen und schauen, was uns das verrät."

"Du meinst über Google?" fragte Penny.

"So ähnlich. Wenn wir die ISBN in eine Suchmaschine eingäben, bekämen wir eine Menge Informationen, aber die wären schlecht für den Raspberry Pi zu verstehen. Aber glücklicherweise hat Google eine freie JSON API."

"Jetzt denkst du dir Sachen aus," wehrte Penny ab. "Wer ist Jason und was soll ein API sein?"

Poppy verbiß sich das Lachen und erklärte: "API ist die Abkürzung für Application Programming Interface, zu deutsch eine Programmierschnittstelle. Es ist eine Möglichkeit von Computern, miteinander zu reden. Ein Computer schickt einen auf bestimmte Art formatierten Code zu einem anderen Computer und dieser zweite antwortet darauf mit einem Code, den der erste lesen kann."

Pennys Augen leuchteten auf. "Verstehe! Der Code ist also einfach genug für einen Computer zu kapieren. Aber ich begreife immer noch nicht, wer Jason ist...?"

Poppy lächelte. "Ich werd es dir zeigen. Als erstes müssen wir Python sagen, dass wir mit URLs - Internet-Adressen - arbeiten wollen."

<pre lang="python">
import urllib2
</pre>

"Das bedeutet einfach nur, dass wir die URL Library Version 2 verwenden. Jetzt müssen wir herausfinden, wie Googles Bücher-API funktioniert. Manche APIs sind ziemlich kompliziert. Aber diese ist glücklicherweise kinderleicht."

Poppy stellte sicher, dass sie allein waren, dann kramte sie ihr Notfalltelefon aus der Tasche. Streng genommen waren Telefone in der Schule nicht erlaubt - aber es war so billig, dass es niemand freiwillig stehlen würde und sehr praktisch, wenn sie etwas nachschlagen wollte. Sie suchte nach Infos zu Googles Bücher-API.

"Das sieht wirklich ziemlich einfach aus, "sagte sie. "Tipp mal ein, bitte."

<pre lang="python">
https://www.googleapis.com/books/v1/volumes?q=isbn:
</pre>

"Du musst nur die ISBN nach dem Doppelpunkt ergänzen und es sollte alles zurückgeben, was Google über ein Buch weiß. Probieren wir's aus!"

Aufs Geradewohl schnappte sich Poppy einen dünnen Band aus dem Englisch-Regal und las sorgfältig die ISBN vor: "014018385X"

Pennys Finger tanzten über die Tastatur. "Okay, wir wollen Google nach der Info fragen und sie dann auf dem Bildschirm anzeigen."

<pre lang="python">
import urllib2
print urllib2.urlopen('https://www.googleapis.com/books/v1/volumes?q=isbn:014018385X').read()
</pre>

#### Was passiert, wenn du den Code ausführst?

"Uiii!" rief Penny, "Das ist JSON?"

"Im Prinzip ja. " sagte Poppy nach einem Blick auf den Text, mit dem sich der Bildschirm gefüllt hatte. "Soll ich es für dich entziffern?"

Penny nickte stumm, total benommen von den Daten, die ihr Pi aus dem Internet gezogen hatte.

Poppy fuhr fort, "JSON ist eine Methode, Daten so zu strukturieren, dass sie für Computer einfach zu verstehen sind und für Menschen _einigermaßen_ einfach zu lesen. Ein Weg, um ein Ding, oder eine Gruppe von Dingen zu beschreiben. Schau, das bist du dargestellt in JSON..."

Sie schob ihre Freundin zur Seite und find an zu tippen. Sie konnte nicht blind tippen wie Penny und brauchte einige Zeit, um das "U" zu finden, das nie da lag, wo sie es gerade brauchte.

<pre lang="JSON">
{
	"Person": {
		"Name": "Penny",
		"Augen": {
			"Anzahl": 2,
			"Farbe": "gruen"
		}
	}
}
</pre>

"Bitte sehr, begreifst du, wie es geht?" fragte Poppy.

Penny las sorgfältig den Code. "Ich denke ja. Jedes Ding hat einen Wert. So 'Name' ist 'Penny'. Aber einige Werte können auch mehr Sachen enthalten. So haben meine 'Augen' gleich mehrere Eigenschaften. Lass mich mal..."

Jetzt war Penny an der Reihe, ihre Freundin zur Seite zu schieben und zu tippen.

<pre lang="JSON">
{
	"Person": {
		"Name": "Penny",
		"Augen": {
			"Anzahl": 2,
			"Farbe": "gruen"
		},
		"Lieblingsessen": "Mango",
		"Haare": {
			"Laenge": "kurz",
			"Farbe": "rot"
		}
	}
}
</pre>

"So ungefähr?"

Poppy schaute über den Code und sagte: "Ich denke du hast es kapiert. Es gibt nur noch eine winzig kleine Komplikation."

Penny seufzte. Irgendetwas machte ihnen immer einen Strich durch die Rechnung. 

Poppy übernahm wieder das Tippen. "Und so stellst du es in JSON dar, wenn du mehrere Leute hast."

<pre lang="JSON">
{
	"Leute": [
		{
			"Person": {
				"Name": "Penny",
				"Augen": {
					"Anzahl": 2,
					"Farbe": "gruen"
				}
			}
		},
		{
			"Person": {
				"Name": "Poppy",
				"Augen": {
					"Anzahl": 2,
					"Farbe": "braun"
				}
			}
		}
	]
}
</pre>

Als Poppy fertig war mit rumsuchen auf der Tastatur, sagte sie: "So. Richtig. Die eckigen Klammern '[' und ']' bedeuten, dass eine Gruppe ähnlicher Dinge dazwischen steckt. Wir könnten da Millionen Leute reinschreiben. Oder nur einen. Das hängt ganz davon ab, was wir tun wollen."

Penny dachte einen Augenblick nach. "Das klingt nicht so schlecht. Wo ist der Haken?"

"Heh", Poppy lachte leise. "Wenn wir den ersten Gegenstand aufrufen wollen, müssen wir die Nummer '0' verwenden. Beim zweiten ist es die '1' und so weiter."

Penny gähnte und reckte ihre Arme. "Egal. Machen wir weiter."

Poppy grinste ihr Chsehsire-Katzen-Grinsen. "Also, wir haben unser JSON zurück von der Google-API. Jetzt müssen wir nur noch genau die Informationen bekommen, die wir wollen. Fangen wir damit an, Python zu sagen, dass wir JSON verwenden wollen."

<pre lang="python">
import urllib2
import json
</pre>

"Jetzt schnappen wir uns diese JSON und speichern es in einer Variablen."

<pre lang="python">
book_data = json.load(urllib2.urlopen('https://www.googleapis.com/books/v1/volumes?q=isbn:014018385X'))
</pre>

"Schick," sagte Poppy. "Lassen wir uns 'book_data' mal am Bildschirm anzeigen, ob alles stimmt."

#### Versuche, book_data auf dem Bildschirm auszugeben

Penny starrte auf den Monitor, rieb sich die Augen und starrte wieder. "Schon mal etwas. Aber wie bekommen wir aus diesem Salat den Titel heraus?"

"Das ist einfach," sagte Poppy selbstbewußt. "Jetzt, wo wir die JSON-Daten haben, können wir davon leicht alles, was wir wollen, anzeigen. Dieses JSON hat einen Stapel 'items', wir wollen das erste und dann wollen wir 'volumeInfo', das enthält 'title'."

"Klar wie Kloßbrühe!"

"Das geht so:"

<pre lang="python">
print book_data['items'][0]['volumeInfo']['title']
</pre>

Und mit diesen Zeilen erschien der Titel des Buchs auf dem Bildschirm. Die Mädchen jubelten und Poppy kitzelte Raspberry Pis Ohren und bot ihm einen Keks an.

"Nummer Eins erledigt, "sagte Penny. "Jetzt brauchen wir den Autor und ein Thumbnail-Bild des Covers."

#### Kannst du dem Programm beibringen, den Autor und die URL für das Bild anzuzeigen?

Pennys Plan war einfach. Sie würden die ISBN von jedem Buch in der Bibliothek nehmen und mit dem Python-Programm, das sie geschrieben hatten, Autor, Titel und Bild heraussuchen. Dann würden sie eine Seite auf der Schul-Website anlegen, um die Bücher zu verkaufen.

"Diese Bibliothek ist uralt." erklärte Penny. "Es muss hier hunderte alter Bücher geben, die jemand kaufen will."

#### Kannst du das Programm so ändern, dass es nach einer ISBN fragt und das Ergebnis ausgibt?

Es war Stunden her, dass sie angefangen hatten. Sie wechselten sich ab mit Tippen und Büchern aus den Regalen holen. Einige der Bücher erschienen nicht in Googles mächtigem Gedächtnis, diese legten sie fürs erste zur Seite.

Poppys Rücken fing an zu schmerzen und Pennys Finger taten weh vom vielen Tippen.

Sie waren nicht einmal halbfertig. Regale hinter Regalen schienen sich bis in weite Ferne zu erstrecken.

"Ein letztes, dann machen wir Schluß für heute," gähnte Poppy.

Penny nahm das nächste Buch. Sie sah keine ISBN auf dem Buchrücken, deshalb schlug sie es auf. Dort stand in verblaßter Tinte über der ISBN "With best wishes", gefolgt von einer krakeligen Unterschrift.

"Pops... Ich glaube, ich weiß, wie wir die Bibliothek retten. Gib mal diese ISBN ein, bitte: 0747532699."

#### Was ist so besonders an diesem Buch?

## In der Zeitung

In den Nachrichten zu sein war lustig! Als sich ihr irrsinnig seltener Fund herumsprach, fielen die Medien über die Schule her wie eine Heuschreckenplage.

Der örtliche Parlamentsabgeordnete tauchte auf und versuchte, sich bei den Reporter einzuschleimen. "Ich bin so unfaßbar stolz," verkündete er salbungsvoll, "auf diese zwei bemerkenswerten jungen Damen. Mit dem Verkauf dieses Buches wird die Schulbibliothek für viele Jahre sehr gut ausgestattet sein" Sein Lächeln hatte zuviele Zähne für Poppys Geschmack. 

Ein Reporter hielt sein Mikrophon Poppy unter die Nase. "Wie kam es, dass ihr das Buch gefunden habt?" fragte er.

"Oh", sagte Poppy zuckersüß. "Als wir hörten, dass die Regierung unsre Schulbibliothek schließen will,  mussten wir einfach etwas machen, um sie zu retten."

Alles wurde still im Saal. Ein einziger Blitz aus einer Kamera erleuchtete das Gesicht des Abgeordneten. Sein Lächeln war erstarrt.

Penny drehte sich um und fragte in ihrem allerhöflichstem Ton: "Warum wollten sie unsere Bibliothek schließen?"

Plötzlich begann die versammelte Pressehorde zu schreien: "Minister, Minister, haben sie einen Antwort..."

Der Abgeordnete schaufelte sich seinen Weg zwischen den Reportern frei und hinaus zu seinem wartenden Auto.

Frau Hopper ging zu den Mädchen hinüber.

"Uh, oh" flüsterte Penny.

"Mädchen", begann sie. "Wenn ich euch nochmal erwische, wie ihr in diesem Ton mit einem Regierungsmitglied redet..." Sie machte eine kleine Pause, "werde sich sehr stolz auf euch sein."

Und damit, ein seltsames kleines Lächeln auf den Lippen, ging sie ins Innere der Schule zurück.
