# The Python Pals Divine A Date

Penny was in a right grouch.  Her voice wobbled as she unloaded her woes on to her best friend, Poppy.

"It's all so _unfair_!" She started to sob.

"Oh sweetie," said Poppy, "I hate to say this, but you're sounding like a right stereotypical teenager!"

Penny cracked half a smile and blew her nose.  "I know," she said "But it's true. Why _can't_ I date him?"

Poppy sighed.  Penny's mum Ada had banned her from seeing this boy - and it was causing no end of bother.

"Well, she explained, "they think he's too old for you. He is a *bit* grown-up."

Penny let out a little growl of rage "But I'm more mature than most grown-ups; half of them can't even _switch on_ a computer - let alone program it as well as I can!"

This was true.  What Penny lacked in years, she more than made up for in talent.  No one at her school could even come close to her when it came to Python.  Even the teachers turned to her for help when they were stuck.

"You don't really want to go out with him, do you?" asked Poppy, "I mean, he's got all those zits."

It was Penny's turn to sigh, "No. No not really. And he does have a really annoying laugh. But I want the _right_ to go out with him. That's what's unfair."

"Hang on..." Poppy was thinking.  What she lacked in coding skills, she made up for in tenacity and lateral thinking. "That **may** be unfair..."

Penny looked up from her disintegrating tissue. "I _know_," she pleaded.

"No, I mean literally unfair," Poppy paused, knowing she was getting in to dangerous territory, "What's the exact age difference between your parents?"

Penny's eyes began to twinkle - not with tears, but the hint of a mischievous idea...  "There's one way to find out," she grinned, "Let's get the Raspberry Pi!"

## The Difference Engine

"Ok," said Penny, wiping her nose on her sleeve, "What comes first?"

They always worked best like this - Penny sat cross-legged in front of the computer plugging away on the code, while Poppy strode around the room pontificating on the problems.

"First," said Poppy "Does Python have a way to handle dates and times?"

"Oh yes," and Penny began typing.

<pre lang="python">
from datetime import date
</pre>

"Basically, all you need to do is tell Python right at the start what special functions you want to be able to use. In this case, there are some built-in functions called 'datetime' and we just want those ones which deal with dates."

"Can we test it?" said Poppy cautiously. She always wanted to make sure that everything worked every step of the way.

"Sure!"

<pre lang="python">
print date.today()
</pre>

"That should show us today's date," Penny ran the program and was rewarded with

<pre>2014-03-24</pre>

"Well," said Poppy "Why is it written in such a funny order?"

Penny loved explaining to her friend, she relished the look on her face when she finally understood something.

"So, the Americans write the date with the month first - like 12/11 means December the Twelfth. But to Europeans, it means Twelfth of November.  In order not to confuse anyone, most computers represent the data as 'YEAR-MONTH-DAY'."

"Oh, that makes a funny kind of sense.  So, that's today's date - how do we create a specific date?"

"It's pretty easy," Penny's hands danced over the keyboard, creating a pleasant clattering sound.

<pre lang="python">
my_birthday = date(2000, 02, 29)
</pre>

"We create a variable and assign a date object to it. That's all."

"Alright, so what's zit-boy's birthday."

"As if I know!" said Penny in a scandalised tone of voice.

Poppy fixed her with her steely eyes and internally counted to ten.  

Penny cracked by the time Poppy got to 7 and, in a small voice said "January 15th, 1998."

"Eugh! He was born _last century_!"

"Shut up."  She added the variable.

<pre lang="python">
his_birthday = 
</pre>

#### Add in the boy's birthday.

"So, your birthday, his birthday. How do we tell how much older he is?"

Penny thought for a second.

"Python is usually really good at doing maths on things.  What happens if we..." She trailed off, lost in code.


#### How do you think you would get the difference between two dates?

The keyboard clattered away under Penny's relentless hammering.

<pre lang="python">
difference = my_birthday - his_birthday
print "The difference is " + str(difference.days)
</pre>

"The difference will be a date object - so we can ask it how many days it has. We also need to tell Python to cast it into a string, so that it will print out properly."

She ran the program.

#### What happens when you run the code on your computer?

Poppy shrieked "He's **ancient**!"

It was Penny's turn to glare, "It just looks bad because it's written in days. Not in years and months."

Poppy leant back, and twiddled her hair between her thumbs.  "Right, so there are 365 days in a year..."

"Don't forget leap years," said Penny, who was touchy about the subject.

"Ok, 365 and a quarter."

"Well, that's easy enough to calculate. I'll take the number of days and divide it by 365.25."

<pre lang="python">
print difference.days / 365.25
</pre>

Penny had to admit, that didn't make much of a difference. It _still_ looked bad.

Poppy grinned, "Ok, so let's see what it says about your parents."

Penny rummaged around in her brain for a bit, "My mum was born on October 17th, 1975 - and dad was born December 24th 1972."

With a quick whisk round the keyboard she entered in the dates.

Penny gasped, "My parents are _such_ hypocrites!" Both girls giggled.

Penny gave the Raspberry Pi a little pat on where she thought its head would be, "That's why we use computers - to make tricky things easy!"

She turned to her friend, "Let's do your parents next!"

The atmosphere in the room suddenly changed dramatically.  Poppy's memories of her father were still raw and painful.

"Pops," said Penny gently.

"No, it's ok," said her friend, with tears in her eyes. "But I think that's enough coding for today."

## A Midnight Nightmare

It was close to midnight when Poppy snuck out of bed.  Quickly she flipped her phone on to quiet mode.  She strained her ears to see if her mother had heard the alarm.  Nothing.

Poppy silently slid out of bed. She slowly tip-toed over to her Raspberry Pi and switched it on.

She just _couldn't_ let her mother hear her up at this hour!

Gently, she tapped her keyboard and subtly altered the Python code that Penny had written earlier.  She checked and double-checked her code.  There was **no way** she could afford to get this wrong.

Glancing around furtively, she inputted the today's date - 24th of March, 2014.

She shut her eyes tight, took a deep breath, and pushed down on the enter key.

For a full minute, she didn't dare open her eyes. She wanted to _so_ badly, but knew that opening them would unleash more emotions than she knew how to deal with.

She screwed her courage to the sticking-place, and her eyes flicked open.  There, glowing gently on the screen were the words which made everything real - and made her die a little inside.

<pre>Your father has been missing for: 101 days.</pre>

#### Can **you** work out when Poppy's father disappeared?
