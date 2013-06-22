# The Morse Code Mystery

## The Beachcombers

The waves crashed angrily on the beach, and the rain seemed to come in from all directions.  A sudden gust blew a thin drizzle straight down Poppy's collar.  
"This weather is _foul_," she spat.  
"Just five more minutes," yelled Penny.

Poppy collapsed herself until she was eye level with her friend Penny.  Even though Penny was the shorter of the two, she was hunched down on the beach anxiously glancing at the shoreline.

"Penny, what are we doing here? It's cold, wet, and most importantly," she paused for dramatic effect, "We're going to miss the Food Network's 'Marzipan Marathon'!"  
Her friend giggled - neither of them could stand those TV cookery channels - but they had agreed there was something oddly compelling about watching a man trying to eat his body weight in cake.  
"There!" Yelled Penny, pointing a little way down the shoreline. "I told you that interesting stuff gets washed up here when there's a storm. Grab it!"

Despite being the older of the two friends, Penny was always being treated like Poppy's younger sister - so she relished in the chance to bark orders at her friend for once.

Poppy scooped up the large square of blue canvas a spun around.  "Please can we go in now?" she whined, "It's cold and wet and..."

Before she could even finish her sentence, Penny exclaimed "Look! Look at the cloth!"

They both stared at the raggedy square of canvas.  It was peppered with strange white marks.

"Let's get home and work out what this is," said Poppy. With that, she started sprinting away toward her mum's home.

"That just what _I was about to say_!" yelled Penny, as she slowly trudged up the beach.

## Pi Power

"Will you be wanting some soup, girls?" asked Poppy's mum, Ada.  She had gotten used to both of them storming in and expecting to be fed.  
"No time Ada, thanks," said Penny breathlessly, "We've got to work out what this is."

"Hmmm, looks like old fashioned Morse Code to me," said Ada after a moment's cursory examination of the cloth.  "Where on Earth did you find..."

"Can we get some soup and croutons, and maybe some cheese. Do we have any crisps?" yelled Poppy as the girls bolted upstairs.

They flipped on the Raspberry Pi.  It had been a birthday present from Poppy's dad.  One of the few things she had left to remember him by.  Just as Linux was booting up, there was an enormous crack of thunder which shook the whole house. The lights flickered, then went off.

A second later they were back on, but there was a strange burning smell in the room.

"Oh no! Cried Penny, "The router!"

Where their Internet router had been was a smouldering lump of twisted plastic and metal.  
The girls flipped on the Pi.  
Poppy said a word which, if her mother had overheard her would have meant an instant reduction in pocket money.  "How will we find out what 'Morse Code' is if we can't get online?"

The girls sat, stunned.  No Internet.  No Facebook. More importantly, no Wikipedia!

They looked at their phones but, as always they didn't have any credit.

Poppy looked around the room forlornly.  The little study had been Poppy's dad's work area before he... Well. Just before.  She scanned the shelves looking for something which might help - even an old fashioned dial-up modem would do.

Penny suddenly chirruped, "Pops, what's the 'Encyclopaedia Britannica'?" Pointing to an imposing set of books on a shelf.
"No idea," sniffed Poppy despondently.  
"Only, and I know it was your dad's, but 'encyclopedia' sounds a bit like 'Wikipedia' and I wondered..."  
[![Ad Encyclopaedia-Britannica 05-1913](http://upload.wikimedia.org/wikipedia/commons/d/d8/Ad_Encyclopaedia-Britannica_05-1913.jpg)](http://commons.wikimedia.org/wiki/File%3AAd_Encyclopaedia-Britannica_05-1913.jpg "By Encyclopedia Britannica (scanned by Infrogmation, pulished on en WP) [Public domain], via Wikimedia Commons")

"Of course! Quick, which one of the books has 'M' printed on the side?" Poppy smiled. It was rare to see her smile these days, and Penny relished the chance to cheer up her friend.

They plucked the dusty volume from the shelf and opened it up more-or-less at random.  Its musty smell filled the room and they began flicking through the yellowing pages.  
"Where's the search function on this thing?" joked Penny.  
"Möbius, Moomins, Mormon, Morse!"

There, laid out in the pages of the encyclopaedia was a guide to Morse Code.

[![Intcode](http://upload.wikimedia.org/wikipedia/commons/e/e9/International_Morse_code.png)](http://commons.wikimedia.org/wiki/File%3AIntcode.png "By Rhey T. Snodgrass and Victor F. Camp [Public domain], via Wikimedia Commons")

The girls flipped on the Pi and waited for it to boot.

"The most important thing to consider when programming," said Poppy doing her very best imitation of Mr Cartwright their inexcusably dull IT teacher.  
"...is planning!" said Penny, finishing her friend's sentence.

"We want a program which will let us type in each letter of Morse Code and then show us the English translation."

Penny grabbed the keyboard. She knew that she would be doing most of the typing while Poppy did most of the pointing out of her mistakes.  Apparently, this was known as "pair programming" according to Mr Cartwright. She didn't think much of it.

"First," said Poppy, "Let's define a [dictionary](http://docs.python.org/2/tutorial/datastructures.html#dictionaries) of English and Morse Code."

Penny's hands darted across the keyboard as her friend read the dots and dashes from the book.

<pre lang="python">
morse = {  '.-'  :'A', '-...':'B', '-.-.':'C', '-..' :'D', '.'   :'E',
           '..-.':'F', '--.' :'G', '....':'H', '..'  :'I', '.---':'J'
        }
</pre>
#### Can you program the rest of the dictionary yourself?

Poppy sighed, "Why on Earth have you bothered to line up all the letters?"  
"It helps me think," said Penny defensively, "I like it neat. Besides, Python doesn't care how I space things like that."  
"Fine! Let's do a quick test to see if it works," said Poppy.  
"Right, I'll ask the user to type a single letter of Morse Code. Then it's really easy to look it up in the dictionary," said Penny.

<pre lang="python">
get_code = raw_input('Type a Morse Character ')
print morse[get_code]
</pre>

She ran the program.  As expected it asked her to type in a code.  She hit the sequence ".-" and hit enter.

She was rewarded with a glowing "A" on the screen.

#### Does your program does the same?

"Good start," said Poppy. "But it's going to be a pain to type in every Morse character, then hit enter, then try to string the letters together."

Penny thought for a moment. She knew she could come up with something clever.

"How about we read in the string we type in, then break it up based on where the spaces are?" She said tentatively.  
Poppy looked confused, "What do you mean, Pen?"

Penny ran Python directly so she could show what she was thinking
<pre>
Python 2.7.3 (default, Aug  1 2012, 05:14:39) 
[GCC 4.6.3] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> </pre>

At the prompt she typed
<pre lang="python">
>>> "This is a test".split()
</pre>

"If I'm right, the [.split()](http://docs.python.org/2/library/string.html#string.split) function will give us a list of all the word."

She gently thumbed the enter key.

<pre>['This', 'is', 'a', 'test']</pre>

"Yes!" Shouted both girls simultaneously.

"So now we will have each Morse Letter in a list, then we want to look it up in the dictionary."  
"That's right. Luckily it's super simple to do something on every item in a list - look,"

Penny typed directly into Python again.
<pre lang="python">
>>> list_of_words = "This is a test".split()
>>> for item in list_of_words:
... print item
</pre>
But this time, when she hit enter, an error message popped up!
<pre>
  File "&lt;stdin>", line 2
    print item
        ^
IndentationError: expected an indented block
&lt;/stdin>
</pre>

This time it was Penny's turn to swear.

#### Can you work out where Penny and Poppy have gone wrong?

"Wipe that grin off your face! Yes, [spacing and indentation are important in Python](http://www.secnetix.de/olli/Python/block_indentation.hawk). But generally it's fine if I line up my code just how I like it."

She tried again. This time hitting the spacebar as hard as she thought it could stand.

<pre lang="python">
>>> list_of_words = "This is a test".split()
>>> for item in list_of_words:
...    print item
</pre>

This time, the result was a lot more satisfactory.
<pre>
... 
This
is
a
test
>>> 
</pre>

"Getting there," muttered Poppy under her breath.  They swiftly changed the last few lines of their code to read:

<pre lang="python">
get_code = raw_input('Type in the Morse Code ')

code_list = get_code.split()

for item in code_list:
   print morse[item]
</pre>

"Ok," said Penny, "Let's see what this mysterious blue cloth says on it..."

<pre>...  ---  ...  -...  ---  .- -  ...  .-  -.  -.-  ---  -.  ..  ...  .-..  .-  -.  -..</pre>

They checked and double checked what they had typed in.

"Ready?" said Poppy.  
"Let's do it!" said Penny as she hit the enter key.

#### Can *you* solve the Morse Code Mystery?

## Saving The Day

"Well done you two," said the Mayor. "Without your help, that sailor would have been stuck for long time."

Penny and Poppy both grinned. It had all been such a rush, they'd gone from running their code, to screaming for Poppy's mum, to calling the coastguard, to seeing a shipwrecked sailor being rescued.  They had been interviewed for TV and the clip had _hundreds_ of YouTube likes.

There was even a Facebook page dedicated to thanking them!

The Mayor had decided that such fine upstanding citizens deserved a reward - and had invited them to a special event in the town hall.

"Who would have thought two girls would know Morse Code?" They Mayor said, "Did you learn that at school?"

Penny fixed him with a steely glare, "No. We taught ourselves."

The Mayor peered over his glasses, "But surely you had help from someone? An older brother perhaps?"

Poppy knew the look on Penny's face and answered before her friend lost her temper, "I think you'll find," she said sweetly, "that **women** don't need help from **boys**!"

Poppy felt Penny's hand slip in to hers. She started to chuckle as her hand was squeezed in firm but measured bursts.

<pre>-  ....  .-  -  ...  .--  ....  -.--  -.--  ---  ..-  .-  .-.  .  --  -.--  -...  .  ...  -  ..-.  .-.  ..  .  -.  -..</pre>

THE END
