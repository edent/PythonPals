# The Python Pals Write A Wrong

Poppy's mother, Ada, was **not** happy.

"I don't care about that," she shouted down the phone, "Why am I always the one who has to pick up the pieces?"

She carried on ranting.  Penny and Poppy were sat in the lounge. Even though the TV volume was quite high, they could still hear snatches of the conversation.

Suddenly, the door burst open and Ada stormed in, "What are you two doing right now?" she demanded.

"Just watching TV," said Poppy, "It's the episode where they..." but before she got a chance to finish, her mother interrupted.

"Nothing then. Good. You can make yourselves useful."

"But _mum_!"

"But nothing.  I need to go into town to deal with.... just into town. I'm not going to have a chance to type up all these thank you letters. So I need you to do it."

Penny smiled sweetly at her friend's mother, "Sure thing, Ada, we'd be happy to!"

"Good. It's settled. And please get them all done by the time I get back. I need to get them sent and I..." she looked close to tears.

"Don't worry, mum, we'll get them done. I promise!"

Ada gave a weak smile, kissed her daughter on the forehead, and left without saying a word.

Penny turned to her pal and said, "Let's get cracking!"

They ran into Ada's work room.  It was plainly furnished, although the desk was a mess of papers.  A vase sat in the corner, its flowers long since withered.

"What's all this about, Poppy?" asked Penny.

"There's loads of really yucky diseases out there and mum's been raising money to make sure that young women stay healthy. Now, where does my mum keep her pen and paper?"

Penny fixed Poppy with a steely glare - the one she usually reserved for people who asked if she wanted to take up cross-country running, or some other mad sport.

"What do you want to write them all by hand for?" She asked.  Out of her blue and white school rucksack she pulled her Raspberry Pi and set it up on the desk.

Poppy passed Penny a USB stick which had been nestling in a collection of newspaper clippings on her mother's desk, "All of the donors should be on there."

Penny plugged the stick into the Raspberry Pi.  She fiddled around until she could see its file system.

"Aha, there we go!" Penny said triumphantly "Let me just open it up."

A few clicks later and the text file displayed on the screen.  It showed the names of all the donors and how much they'd given.

<pre>Anna 2.50
Beth 5.93
Cath 23.50
Dom 15
Erik 3.14
...
</pre>
([You can download the file to your computer](https://github.com/edent/PythonPals/blob/master/donors.txt))

The file kept on scrolling and scrolling.

Poppy shrieked, "There's well over a hundred names here! We're never going to be able to finish all these letters by the time my mum comes back! Not even you are that fast a typist."

"Pops," said Penny, "I don't want to be mean - but you're being _incredibly_ thick. So utterly, mind bendingly dense that I'm not sure if we can be friends any more." Very loudly and slowly she said "We have a computer, you prat! We'll get the Pi to do the hard work for us!"

Poppy looked sheepish, "Oh... Yeah. Wait! I suppose we can use Python to get this done in a few minutes?"

Penny put on her cheesiest American accent and drawled, "Got it in one, partner."

When they had both regained their composure, Penny perched on a chair with both legs tucked underneath her. Poppy hopped up on the windowsill so she could see the screen and her friend at the same time.

Poppy started, "Well, let's break it down in to easy to manage chunks.  You've got a file with the names and amounts people have given, right?"

"Right."

"Ok, so we want to read in each line of the file, then create a letter based on the information."

"That should be pretty easy, Pops." Penny stretched out her fingers and started typing. She was most at home when her fingers were flying over the keyboard.  As she typed, she spoke.

"It just takes one line of code to open a file. You just tell Python where the file is, and if you want to read to the file or write to the file."
<pre lang="python">
textfile = open('donors.txt', 'r')
</pre>
"Our file is in the same directory as this Python program, and we only want to read it.  To see if we've got the right file, we can tell Python to display its contents."

<pre lang="python">
print textfile.readlines()
</pre>
She saved the program and ran it.  The file displayed itself in the console.

"Great," said Poppy, grinning, "One task down. Now every line just has the person's name and how much they donated, right?"

"Yup. So we can read the file a line at a time and do something with each line.  Watch."

She deleted her code and started again
<pre lang="python">
textfile = open('donors.txt', 'r')
lines = textfile.readlines()

for line in lines:
   chunks = line.split()
   donor_name = chunks[0]
   donor_amount = chunks[1]
   print donor_name
</pre>

"So," she said methodically, "We open the file. We get every line. We split every line based on spaces. Of those two chunks, we called the first the donor's name, and the second the donor amount. Then we print out the donor's name - just to be sure."

Her finger hovered over the keyboard. Just as she was about to run the program, Poppy interrupted.

"Hang on. Why is '`donor_name`' coming from chunk zero? Shouldn't it be from one - and the amount from chunk two?"

"Ah," said Penny, "In Python - and most other languages - lists always start from zero."

"That's dumb," said Poppy. 

"You get used to it." 

"But what's the point in that?"

"Well, think of the years. We're in the 2000s now.  The first year of the 2000 was - obviously - 2000. The second year was 2001, the third was 2002 and so on."

"Oh!" said Poppy, as things clicked into place, "That makes sense... kinda..."

"As I said, you get used to it. Now, where were we?"

"Right, we want to say something like 'Dear `donor_name`, Thanks for your donation, blah blah blah, etc'"

"You are _so eloquent_!" Penny's sarcasm flew out before she could stop herself.  She carried on typing, adding the following lines.

<pre lang="python">
   letter = "Dear " + donor_name + ", "
   letter += "Thank you for your donation of " + donor_amount
   print letter
</pre>

"When you add two strings of text together," she explained, "Python just sticks them next to each other - it's called concatenation."

"But what are those plus-equals symbols for?"

"If you want to add something on to an existing variable, you could say `whatever = whatever + something` but it's quicker to say `whatever += something`"

"Ooooh!" gasped Poppy - who was very good at interjecting with what she perceived as helpful comments, "Make it say 'Generous Donation'!"

"Yeah, but some of the people _weren't_ very generous."

"Well, that's easy enough to solve. Only say generous if they gave more than &pound;10."

"Of course!" Said Penny, "Why didn't I think of that?"

"Hey! That's why we're such good friends - I'm the brains and you're the...." Poppy trailed off.

"The typist?" Penny said scornfully as she, hammered the keys angrily.

<pre lang="python">
   letter += "Thank you for your "
   if float(donor_amount) > 10:
</pre>

"What does '`float`' mean?" asked Poppy.

Penny turned in her chair to face her friend, "Ok, our Python code has read a string of text from the file, right?"

"Yup"

"So it thinks that '5' is the character '5' not the _number_ '5'."

"Ah! So if you had '5'+'2' it would be '52'."

"Bazinga! So, we need to '[cast](http://www.cyberciti.biz/faq/python-convert-string-to-int-functions/)' the character into the number. Think of it like casting a spell on someone to look like a frog."

The light dawned on Poppy's face. "I see! So when you say '`float(donor_amount)`' you're saying to Python 'Imagine that this is a number'"

Penny nodded and carried on typing.

<pre lang="python">
   letter += "Thank you for your "
   if float(donor_amount) > 10:
      letter += "very generous "
   letter += "donation of " + donor_amount
   print letter
</pre>

"It's just simple maths. You can use `>` for seeing if something is greater than something else, or `<` for less than."

Poppy peered at the keyboard.  She cleaned her glasses and peered again. "So where's the greater-than-or-equal-to key?"

"There isn't one.  You just have to type the equals key afterwards like `>=` or `<=`"

"Nifty. Oh, and not to criticise, but you left off the &pound; symbol on the donor amount."

Penny deftly changed the line to read:
<pre lang="python">
   letter += "donation of £" + donor_amount
</pre>

But this time, when she ran the program, something unexpected happened.

#### Now run the code on your computer

<pre>SyntaxError: Non-ASCII character '\xc2' in file letter.py on line 9, but no encoding declared; see http://www.python.org/peps/pep-0263.html for details</pre>

Both girls swore in unison.  There always seemed to be something to trip them up.

"Computers," opined Penny, "Can be really dumb sometimes. They hate it when you use funny symbols."

Poppy considered this, "So we need to tell it what characters we'll be using?"

"Pretty much. We just need to pop this line at the top of our code." Penny scrolled to the top and tapped out the magic incantation.

<pre lang="python">
# This Python file uses the following encoding: utf-8
</pre>
"That ought to do it."

"So, we've got their name, a message, and how much they donated. What else is there?

"Nothing!" sang Penny, "Let's carry on watching TV."

"How about," continued Poppy, blithely ignoring her friend, "How about we told them what their donation has bought?"

"Or, we could _carry on watching TV_!"

"No, if a job's worth doing, it's worth doing properly."

"_Fine_!" Penny huffed, "How much did each vaccination cost?"

Poppy scrabbled around on her mother's desk, studiously ignoring all the legal papers on there, until she found the document she was looking for.

"&pound;1.34 per vaccine."

"That's pretty easy," said Penny, "We'll create a variable for the vaccine cost, then divide the amount donated by that. 
<pre lang="python">
vaccine_cost = 1.34
vaccines_bought = float(donor_amount) / vaccine_cost
letter += ".  That enabled us to buy " + str(vaccines_bought) + " vaccines."
</pre>
"Obviously, we'll have to cast the number back to a string so we can stick it in to the letter." said Penny.

Poppy got a smug grin on her face, "You're going to have a problem there, Pen."

"What on Earth are you talking about?"

"Run it and see..."

#### Run the code on your computer - what happens?

Penny ran the program. She stared at the output, twitched her nose and shouted "Rattlesnakes!"

"The problem," Poppy sighed, "is that computers are _really_ precise. Much more so than humans."

"Stupid humans," muttered Penny.

"So, can we just round things down using the 'round()' function?" said Poppy, conspicuously ignoring her friend's desire to transcend humanity and become one with the machines.

Penny typed away.

<pre lang="python">
round( float(donor_amount) / vaccine_cost )
</pre>

"That's pretty much it, isn't it?" asked Penny plaintively.

"Yup, let's run off these letters and get back to the TV. If we're lucky, we won't have missed too much."

A short while later, Ada swung into the house, her humour looking much improved.

"Girls? Where are you?"

"In here, mum," called Poppy.

"What on Earth are you doing in the TV room?" Said Ada, suddenly looking furious, "I thought I asked you to..."

"Chill, mum," her daughter interrupted. "It's all done."

"What?" Said Ada, clearly baffled, "How could you have done all of those letters? There were at least a hundred."

"One hundred and twenty-eight," chimed in Penny.

They handed over a sheaf of paper to a dumbstruck Ada.

"But this is marvellous!" she cried, "What wonderful letters - and how clever of you to add in the details about how many vaccines their donations were worth!"

"Oh, it was nothing," said Poppy airily. "Now," she continued, "We're quite exhausted after all our hard work. Perhaps you would be so kind as to bring us some ice cream?"

"After all this," beamed Ada, "Ice cream floats for the pair of you!"

"With chocolate sprinkles?"

"Don't push your luck, young lady!" And with that, she twirled off into the kitchen.
