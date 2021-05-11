# IfI-mysteriet 🐧

A failed attempt at making a cicada 3301 style puzzle at my university. The planning and setup of this project started at the end of february 2021.
The ARG ran for around 3 weeks starting at february 25th.

This is my attempt at documenting the puzzles. Why? I like to archive stuff. The project was a total flop but I put some time into it and I don't want it to go to waste even though I in hindsight see how poorly executed it is. Also, I have a massive ego which leads me to thinking people actually care about this stuff when they don't.

## Planning

At the 15th of february 2021, a video popped up in my youtube recommended feed. It was a LEMMiNO video about the infamous cicada 3301 puzzle from a few years back. I had watched the video before but it caught my attention and I decided to watch it again. Just like first time I was amazed by how cool it was that somebody manage to make such an extensive puzzle. The script-kiddie inside of me was in awe and I wished I was there at the time of it happening. But just like all the other cool shit that goes down on the internet, I missed out on it.

This did however inspire me to do my own puzzle. I knew that I wasn't skilled enough to create anything amazing but I was confident I could pull something off. That night I couldn't sleep as thoughts and ideas were flooding my brain. In order to get some sleep I knew I had to write it down so I could stop thinking about it. I then went to sleep determined to make this happen.

The next day I sat down and started to organize my ideas and started putting down a somewhat cohesive plan. I got to work with coming up with riddles and doing the easy stuff, like converting some text to hex and so on. Over the course of the next week I got to work on creating what I needed and preparing stuff. I bought domains, set up webservers for each domain, hiding messages etc.

Tuesday the 23th of februrary I went to my university to put up posters and recorded a video that would be revealed later in the puzzle. I was now ready to make the puzzle public.

## Stage 1 - Website with hidden message in a photo

The best way to reach people at my university anonymously was through the app Jodel, and that's were it all started. I posted a link to my newly created website [ifimysteriet.com](ifimysteriet.com) which lead to a website containing a PGP key and an image. This had a text file embedded inside of it, hidden using openstego...

```txt
dccde3a5b7cp6gebdehjxeyj5e2n27delyvgy2ctxbsprvx7cxcvm6ad.løk
```

...which lead to a site on the Tor network. For context, `.løk` at the end of is meant to tell the user that this is a `.onion` domain. Yay for having to use one extra brain cell I guess.

I put up some other decoy solutions to the puzzle. I didn't think this would actually fool anyone since it seemed to obvious to me but somehow it did.

These decoys were:

- HTML comments
- Javascript console log of LinusTechTips
- CSS comments
- Image size (420x690px)

-----image-----

I didn't plan on saying anything but I felt like I was forced to due to people being confused.

## Stage 2 - Onion site with another hidden message in a photo

The onion site was basically a copy of the site from the first stage, however this time I had changed the way I hid the message within the photo. Very creative, I know 🙃. This stage was basically a rip off from a cicada 3301 puzzle where you could find a message by opening the image in a text editor and look for it.

```txt
I objektorienterernes hus
Finnes det en pingvin
som vil lede vei

Men hvor er den mon tro?
Det er opp til deg

Der maskinkode får litt syntaktisk sukker
vil du finne meg
```

Since there was radio silence and the puzzle game had effectively died of already at this point I decided to post the message on Jodel the week after starting the puzzle.

-----image-----

This time people actually got what I was trying to say. The riddle lead to a IRL poster that I had hung up at the wall right by the classroom named "Assembler"

## Stage 3 - The first poster

-----image-----

The poster had a QR code attached to it which contained a [pastebin link](https://pastebin.com/raw/mFThC3ft) containing the following text:

```txt
앨 첼레 딧 싴켌?

brukernavn: ifistudent
passord: gensermannen

2A 00 4D 15 63 7F 59 23 60 15 0D 75 3B 12 65 27 6B 1B 3F 45 76 28

45 6C 28 7F 0C 17 38 4D 04 74 65 19 5D 73 0B 57 0A 7C 5A 6B 1B 4D
```

The korean text is a norwegian sentences written with hangul characters to the best of my ability? Why korean you ask? Well, I have a weird obsession with learning to read different scripts. I was particularly fascinated with hangul at the time because of it supposed simplicity. I was in the process of learning to read it so that's what I ended up doing. The text is supposed to phonetically sound like the sentence "Er skjellet ditt sikkert?", alluding that you should use SSH. This is further hinted to as I'm giving out the username and password to login somewhere through SSH.

In order to decode the hex numbers you need to do a bitwise or operation on the two sets. This will output an url, `olejohandahlfanpage.me`. Creating this part of the puzzle was the most time consuming part of the puzzle since I did this all by hand. I knew which binary code I had to end up with, but had to create two random sets of numbers that would output correctly.

-----image-----

Yeah, 5 pages of this shit. Let's just say I was tired of looking at ones and zeroes at this point.

Even though people were able to solve my so-called riddle it did not lead to any attention and things went radio silent again. I had to once again post the solution as a last resort of saving this project.

-----image-----

## Stage 4 - The SSH-able machine

When SSHing into the machine you were prompted with a message telling you that there is a hidden video file on this machinge and that it should be easy to find if you know how to use your linux tools.

A lot of documentation is lost at this point because I decided to delete it from my machine but the video file was hidden deep inside the `apt` folder of the machine (this was an Ubuntu instance). The video ended in `.morn` but was actually a mp4 file. I did this to make it harder to find. At this point you can probably tell that I've ran out of ideas and resorted to doing dumb shit like this. Hide and seek.

Anyway, this video file has also been lost so I don't have the actual video on hand but it contained a slideshow of text talking about how it would be cool if people were to make similar types of ARGs in the future. While some [eerie muscic](https://youtu.be/YYb9kSCkjE8) was playing in the background the video then proceeded to show where you could find the next clue to solve the puzzle. This was another poster, but this time hanging in the basement of the my university's building. Since the building is really big it is not as easy to find as it sounds like.

Oh and I also put in a little rick roll at the end of the video because I *had* to 👀

## Stage 5 - The final stage

The poster's QR code lead to a vocaroo file containing an audio file. This audio file had two hidden messages embedded within it, hidden in two different ways.

The first message is found by slowing and pitching the audio down. Not that complicated. This resulted in a message telling you to send a set of numbers to an e-mail address. Which address? The way to find out was to pass the file through Coagula, a program that enables you to draw the waveforms yourself. By looking at these waveforms you could read the address, `anon@ifimystseriet.com`.

-----image-----

This isn't the original waveform but I was too lazy to look up the final waveform. This is just an early experimental version using another address.

## The shutdown

So what happened next? Did you give out any more clues? No, I didn't. I was fed up at this point. No one had taken interest and it didn't look like anything would happen. I kept the servers up for another week just in case someone was actually trying to solve it behind the scenes. I then shut it down and the rest is history. I was kinda dissapointed but not all that unexpected.

## Final thoughts

There are a number of reasons as to why it failed. As mentioned, the puzzles were too hard. People struggled getting past the 1st stage and it all went downhill from there. In addition to this we were living in COVID-times and attendance at school was low. This meant that the posters I put up didn't get noticed and were dismissed. The puzzles weren't very inticing nor original and thus didn't garner any interest.

I'm still hoping that someone will pick up where I left of and try to create some puzzles in the future. I find them fun and interesting, both making and doing them :)

I have probably missed a lot of stuff as I'm writing this whole wall of text in one go in the middle of the night. It probably contains a lot of grammar mistakes and shit but I don't care. Hopefully it was somewhat readable and interesting for you to read. That is, if someone ever reads this.

👋
