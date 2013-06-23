# Cook The Books

## Clearing Out

The mood in the school assembly was grim.  Mrs Hopper, the Head Teacher, had a face like stone.

"I'm sorry children," she said, "but we simply can't afford to keep the school library open any more."

Poppy's heart sank.  She'd spent so long in the school's library.  It was the perfect place to hang out after school, or during soggy lunchtimes, or just when she just needed a break from the world. Some of her best friends were characters from books...

Just then, she noticed Penny's hand spring up.  Penny was her _real_ best friend.  Always encouraging, not put off by the situation with Poppy's dad, and **always** ready to ask an awkward question.

Mrs Hopper couldn't ignore Penny's frantic hand waving, "Yes, Penny, you have a question?"

Penny gathered up her breath and let all of her frustration out in one long breath, "But all the kids use the library and there are really great books in there and it's just a STUPID idea!"

Penny went bright red as she realised what she had just said.

"Detention!" said Mrs Hopper, "And see me after assembly."

## Hopping Mad

Poppy loitered outside Mrs Hopper's office.  She casually leaned in towards the doorway and strained to hear what Mrs Hopper was saying to Penny.

"Penny, I simply will ***not*** be spoken to like that."  The Head Teacher sounded really angry, "I don't get to decide how much money to Government gives us.  I have to make the best use of the resources we have.  It was a choice between closing down the library or closing down the computer lab."

She paused.  The Head knew how much Penny loved computing lessons - how could she possibly choose between them? It was a real "Sophie's Choice".

"So," the Head continued, "We need to start selling off all the books in the library.  Hopefully we'll raise enough money to upgrade some of the computers.  For your detention, I want *you* to make a list of all the books we have so we can start to sell them."

Poppy scuttled away from the door as Penny came bustling out - her cheeks red with shame and her eyes brimming with tears.

"Oh Pen!"

"Well," sniffed Penny, "I guess we'd better get cracking."

"We?" said Poppy in mock horror.

"Oh, I'm sorry, don't you want to help your best friend try and save the library?"

Penny strode off down the corridor in the direction of the library, her shoes clacking on the cheap wooden flooring.  After a second's hesitation, Poppy ran after her.

## Library

The ancient library computer wheezed into life.  Covered in layers of book dust, old library cards, and what looked like some abandoned knitting - the computer was older than both Penny and Poppy put together.  It took so long to boot, it was no wonder that students rarely bothered to use it to check books in and out.

"Do you think we can get a list of all the books from here, Poppy?" said Penny suspiciously. "Only, that thing looks like it belongs in a museum."

With suspiciously poor timing, the hard drive in the machine made a prolonged and ugly crunching sound. The screen glowed with an ominous message: "File allocation table bad drive C."

Poppy glared at the monitor, the error message steadfastly refused to budge. "Right!" she proclaimed, "Time for Plan B."

She rummaged around in her school bag.  There, nestled under her pencil case and an old packet of crisps was her Raspberry Pi.

Penny scrabbled around the library and found a keyboard and helped her friend set it up.

"Python to the rescue?"

"Yes, and I think I know just how to do it. Are you happy to type?" Poppy asked.

"Sure."

"Ok, this is what we want to do..." Poppy paused while she gathered her thoughts, "Every book has a unique number printed on the back of it, right?"

"That's right," said Penny, "The ISBN.  It's a code which gets given to every book when it's published.  But it's just a number - it doesn't tell us anything about the book itself."

"I know, but we can look the ISBN up on the Internet and see what it tells us."

"You mean use Google?" Asked Penny.

"Well, sort of. If we typed the ISBN into a search engine, it would give us lots of information but it would be quite hard for the Raspberry Pi to understand.  Luckily, Google has a free JSON API."

"You're just making things up now," said Penny defensively.  "Who is Jason and what's his ape eye?"

Poppy stifled her giggles, "An API is an Application Programming Interface.  It's a way for computers to talk to each other.  One computer sends a specially formatted code to another computer, that second computer replies with another code the computer can read."

Penny's eyes lit up, "I see! So the code is simple enough for a computer to understand. But, wait, I still don't understand who Jason is...?"

A smile spread across Poppy's face. "Let me show you.  First, we have to tell Python that we want to work with URLs - web addresses."

<pre lang="python">
import urllib2
</pre>

"That just means we'll be using the URL Library version 2 to help us.  Now, we need to know how Google's books API works.  Some APIs are really complicated.  Luckily, this one is as easy as 3.14."

Poppy made sure the coast was clear and then plucked out her emergency phone.  Strictly speaking she wasn't meant to have it in school - but it was too cheap for anyone to bother stealing and was awfully handy when she needed to look something up.  She searched for information on Google's books API.

"Right, that looks pretty simple," she said, "Type this in, please."

<pre lang="python">
https://www.googleapis.com/books/v1/volumes?q=isbn:
</pre>

"Basically, you just add the ISBN after the colon and it should give you back all the data Google knows about a book.  Let's try it!"

At random, Poppy picked up a slim volume from the English section and carefully read out its ISBN "014018385X"

Penny's fingers deftly flew over the cheap beige keyboard. "Ok, so we want to ask Google for the information and then display it on screen."  

<pre lang="python">
import urllib2
print urllib2.urlopen('https://www.googleapis.com/books/v1/volumes?q=isbn:014018385X').read()
</pre>

#### What happens when you run the code?

"Whoa!" Exclaimed Penny, "*That's* JSON?"

"Pretty much," said Poppy after glancing at the text which had filled the screen. "Want me to decipher it for you?"

Penny nodded mutely; dumbfounded by the data her Pi had gobbled up from the Internet.

Poppy continued, "So JSON is just a way of structuring data so it's easy for computers to understand and *fairly* easy for humans to read.  It's just a way of describing a thing, or group of things.  Look, here's you represented in JSON..."

She shoved her friend to one side and typed away.  She wasn't a touch typist like Penny, so had to spend some time hunting for the "U" key which always seemed to vanish right when she needed it.

<pre lang="JSON">
{
	"Person": {
		"name": "Penny",
		"eyes": {
			"number": 2,
			"colour": "green"
		}
	}
}
</pre>

"There you go, do you see how it works?" Poppy asked.

Penny read carefully over the code. "I think so.  Every thing has a value.  So 'name' is equal to 'Penny'.  But, some values can hold lots of things.  So my 'eyes' have multiple properties.  Hmmm, let me see..."

This time it was Penny's turn to push her friend aside and type.

<pre lang="JSON">
{
	"Person": {
		"name": "Penny",
		"eyes": {
			"number": 2,
			"colour": "green"
		},
		"favourite_food": "Mango",
		"hair": {
			"length": "short",
			"colour": "red"
		}
	}
}
</pre>

"How's that?"

Poppy gave it a brief look and said "I think you've got it.  There only one other, teeny, tiny, minor complication."

Penny sighed dramatically.  There was always some spanner in the works.

Poppy took over typing duties again, "Right, let's say you have multiple people, here's how you'd represent it in JSON."

<pre lang="JSON">
{
	"People": [
		{
			"Person": {
				"name": "Penny",
				"eyes": {
					"number": 2,
					"colour": "green"
				}
			}
		},
		{
			"Person": {
				"name": "Poppy",
				"eyes": {
					"number": 2,
					"colour": "brown"
				}
			}
		}
	]
}
</pre>

After Poppy had finished scrabbling around on the keyboard, she said "Right. So. The square brackets `[` and `]` mean that there is a group of similar things between them.  In this case, there are going to be multiple people.  We could put millions of people in there. Or just one.  It depends on what we want to do."

Penny thought for a moment, "OK, that doesn't seem so bad. What's the catch?"

"Heh," Poppy laughed feebly. "Well, if you want to access the first item, you have to use the number '0'. If you want the second, it's the number '1' and so on."

Penny yawned and stretched her arms up the the ceiling. "Fine, whatever. Let's get on with this."

Poppy grinned her Cheshire Cat smile. "So, we have our JSON back from Google's API.  Now we just get the precise information we want out of it.  Let's start by telling Python that we want to use JSON."

<pre lang="python">
import urllib2
import json
</pre>

"Now we need to eat that JSON up and store it as a variable."

<pre lang="python">
book_data = json.load(urllib2.urlopen('https://www.googleapis.com/books/v1/volumes?q=isbn:014018385X'))
</pre>

"Nice," said Poppy, "Let's print `book_data` to the screen so we can make sure it's right."

#### Try to print book_data to the screen

Penny stared at the screen, rubbed her eyes, and stared again. "Well, it's something. But how do we get the title out of this mess."

"Oh, that's easy," said Poppy with a self-confident air. "Now we've got the JSON data we can pretty easily get anything we want out of it.  So, the JSON has a load of `items`, we want the first one, then we want the `volumeInfo` which contains the `title`."

"Clear as mud!"

"It's like this:"

<pre lang="python">
print book_data['items'][0]['volumeInfo']['title']
</pre>

And with that, the title of the book appeared on the screen.  The girls cheered and Poppy tickled the Raspberry Pi's ears and offered to give it a biscuit.

"Ok, one down," said Penny.  "Now we need to get the author and the thumbnail image of the front cover."

#### Can you get your program to display the Author's name and the URL for the image?

Penny's plan was simple.  They would get the ISBN of every book in the library, use the Python code they had written to find out the author, title, and image.  Then they would create a web page on their school's website to sell the books.

"This library is **ancient**," Penny explained, "There must be hundreds of old books in here that someone wants to buy."

#### Can you change the program so it asks you to input an ISBN, then prints the results?

It had been hours since they started.  They swapped between typing and fetching books from the shelves.  Some of the books just didn't appear to be in Google's mighty brain, so they put them to one side for now.  Poppy's back was beginning to ache, and Penny's fingers were suffering from typing for so long.

They weren't even halfway done.  Shelves and shelves of books seemed to extend into the far distance.

"One more, then let's call it quits for the evening." Yawned Poppy.

Penny picked up the next book.  She couldn't see an ISBN on the back, so she flipped it open.  There, in spidery ink above the ISBN was written "With best wishes" followed by a scrawled signature.

"Pops... I think I know how we're going to save the library!  Type this ISBN in, would you? 0747532699."

#### What's special about that book?
 
## Making The Papers

Being in the news was _fun_!  When word spread about their incredibly rare find, the media descended on the school like a plague of locusts.

The local MP had turned up to the school and was busy trying to charm the reporters.  "I'm so incredibly proud," he oozed, "of these two remarkable young ladies.  With the sale of this book, it looks like the school library will be well stocked with books for many years to come!"  His smile had far too many teeth for Poppy's liking.

A reporter shoved a microphone in Poppy's face. "How come," the reporter asked, "you found that book then?"

"Oh," said Poppy sweetly, "When we heard that the Government wanted to shut down our library, we just knew we had to do something to save such a precious resource."

A silence fell on the room.  A single flash from a camera illuminated the MP's face.  His grin had become rictus.

Penny span round and in her politest voice said, "Why *did* you want to close our library, sir?"

All of a sudden the assembled hordes of press began screaming "Minister! Minister! Do you have any comment..."

The MP briskly pushed his way through the reporters and out to the waiting car.

Mrs Hopper strode over to the girls.

"Uh oh," whispered Penny.

"Girls," she began, "If I *ever* catch you talking in that way to a member of the Government again..." She paused for dramatic effect, "I will be *very* proud of you."

And, with that she gave a curious little smile and wandered off into the bowels of the school.