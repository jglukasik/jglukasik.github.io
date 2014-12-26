--- 
title: On building a better remote 
date: 2014-08-07
---

When I went home for winter break, I got to play with my little brother's new
Xbox One. My favorite thing about the console was the new Kinect. The first
thing that caught my attention was the facial recognition login, but that was
short lived, as my brother needed to turn it off because it kept mistaking his
face for mine, and signing him in to my account. But what I really fell in love
with was the always-on voice control.

Always-on voice is a game changer. Speech recognition has always been a cool
feature, but I'd always seen it as a novelty. Why worry about carefully
enunciating my words, hoping the machine understands what I'm saying, confirm
that the software actually did what I wanted it to, and then possibly have to
start all over again? Instead, I would just type in my commands like I always
had, and never really gave voice recognition a chance. But this all changes when
you have something always listening. Before, I always had a computer at my
hands, I'd press a button, and it would start listening. If my hands are already
on the device, why not just keep them there for another few seconds and type in
my request? But with the Kinect, it was now completely hands free. And it was
more than that, it was remote. I could interact with the device from accross the
room. I would enter my basement, say "Xbox on," and before I sat down on the
chair the console, _and the tv_, would be on.  I felt like I was in the future.

It was that second part, the minor little addition, that really caught my
attention. It turned on the tv! That was a dumb screen, bought years ago, that
all of a sudden became _smart_, it listened to me! It reminded me a lot of the
Chromecast, in that it was a nice new piece of tech, that majorly increased the
functionality of an older device. Months passed, but ideas of voice control and
retrofitting old machines with new tech lingered in my mind.

Eventually I got a [Rasperry Pi](http://www.raspberrypi.org/), a really tiny,
really cheap, and really awesome computer.  I then saw a post on Hacker News for
[Jasper](http://jasperproject.github.io/), a project that adds voice control to
a Raspberry Pi. Here was my chance! Ideas flew into my head of my entire home
life, voice controlled, managed by my Raspberry Pi. I saw that article on a
Monday thick in the middle of a midterm crunch week, and I forced myself to wait
until that Friday to dive into it, knowing I would quickly lose myself in that
irresistable thrill of programming, the thrill of _building something new_.

It wasn't until Thursday that I realized that I needed to compile all the
software. The authors of Jasper made a nice fresh image preloaded with all the
necessary ingredients, but I already had some stuff running on my Pi that I
wanted to keep alongside this new project. I had heard this took a while, so I
made a nice little bash script to install and compile all the pieces. Monday
morning I ssh'd into the Pi from my phone in physics lecture and started the
process. After classes I went to work, and from there I entered my Pi again to
check on the progress of things. I soon realized that something messed up, and
barely any progress was made. Oh well, I thought,  as I logged in to my Pi from
my work machine to start the process again. 3 hours later, its still going. I
get home, its still going. I go for a run, its still going. I wait all. night.
long. Still going. And thats when I realized that there is a downside to having
a $35 computer. Compiling things takes fucking forever.

And just like that, I lost the spark. Now, I had to struggle to get the software
working, instead of making a cool future robot butler. In the following days I
managed to compile and install everything, but I was in a constant state of
ironing out some bug in the install process that made the final product useless,
and I quickly lost steam and didn't touch the project at all. 

A few weeks later, I tried again, this time with Steve Hickson's
[PiAUISuite](http://stevenhickson.blogspot.com/2013/06/installing-and-updating-piauisuite-and.html).
I bought a snazzy mic on amazon, installed his software, and everything seemed
to be going alright. But then I ran into audio problems, and the frustration set
in again. I resarched endlessly about audio input on Linux, tinkering with
settings here and there, reading blog posts and trying out their solutions (a
style one of my bosses would later explain to me as [cargo
culting](http://en.wikipedia.org/wiki/Cargo_cult_programming)), and emailing
back and forth a bit with Steve himself (that was another neat moment for me.
Holy shit! The people that make these things are actually _human beings_ that I
can talk to in real life!). Long story short, this second attempt at voice
didn't go much better.

But here I did something different. Instead of just frustratedly leaving this
project altogether, I pivoted and took a different approach. I simplified my
grand scheme of a general purpose, voice controlled, apartment robot to
something simpler. A tv remote. Because I hated having to always get up from the
couch and walk a few feet to the table to grab the one remote to our tv. Or have
to look for it in the couch, or in the kitchen, or wherever it happened to be
put down last. I'm really lazy and tv remotes suck, I can make something to make
this minor inconvenience more convenient.
