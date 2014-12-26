---
title: My raspberry pi
tags: blog
date: 2014-03-27
---
I got a Raspberry Pi a little while ago (I actually got it on Pi Day), and it's
pretty awesome.

When I was home for spring break, I messed around a little with it.  I attached
a usb mouse and keyboard, hooked it up to a tv with hdmi, and plugged it in with
a phone charger and it was good to go.  I explored a bit of the Raspbian OS.  It
has a nice, easy to use desktop environment ready to go for novice users. The
target demographic for this machine is mostly school-age kids, as it is
developed primarily with the goal of getting cheap computers into schools for
kids to become more technologically literate and learn to code on.  However,
this graphical interface is pretty taxing for the little pi, and plus the
command line is better anyway.

When I got back to Madison, the first thing to do was set up ssh and get the box
connected to the internet.  One of my coworkers at my student linux sysadmin job
walked me through the basics of making the pi publicly accessible over the
internet, and how to set up a domain name and other networking things.  With his
help I was able to get my pi into the public internet, and now I can remotely
access the machine from anywhere in the world.  I usually access it from my
laptop, but I also can tinker with from my machine at work, or even from my
phone over 4G with an ssh app (I use JuiceSSH).

After that, I attached a webcam to it.  I am using a Logitech usb webcam that I
used with my old laptop.  I wrote a script that takes takes a picture from the
webcam and keeps the pictures all neat and orderly in dated folders with
timestamps for each picture.  The core of the script is this line: `ffmpeg -f
video4linux2 -vframes 1 -i /dev/video0 $pic_name`, which uses ffmpeg to take a
picture from the webcam, using video4linux to take care of the drivers. I then
set cron to call the script every minute. After a full day passes, and I collect
1440 images, I use MEncoder to stitch them all together into a nice lossless
video: `mencoder ""mf://*.jpeg"" -mf fps=40 -o March25.avi -ovc lavc -lavcopts
vcodec=ffv1`  My favorite timelapse I've taken so far has been the one of March
25th, as it snowed the night before. You also see a bit of me in the beginning
when I took the camera down for a while.

<iframe width="640" height="480" src="//www.youtube.com/embed/TgC5ckcmZa0"
frameborder="0" allowfullscreen></iframe>

Next, I tried to get this Ghost blog running on the pi.  Another coworker helped
me set up an Nginx lightweight web server on the pi, and from that I would
control access to the blog.  After some initial quirks associated with trying to
get everything going on an ARM machine, I was able to get Ghost running.
However, I ran into some problems creating and signing into an account, which
may be due to the pi's lack of power.  I know other people have gotten Ghost to
work on a pi, so I could probably look deeper into it to get it running
smoothly, but I also don't want to put too heavy of a load on my pi all the
time.  Instead, I have a few simple, static html pages on the pi, with a link to
this blog where it is currently located (on an Amazon Web Services EC2 cloud).
<a href=""http://www.jglukasik.com/main.html"">Here is my pi-run website.</a>

I wanted to come up with a unique name for the machine instead of the default
raspberrypi, so I named it blueberrycake.  (Which, by the way, there is an
excellent recipe for in [the family cookbook](cookbook.html))  I am loving this
thing so far.  I have a lot of ideas for this little guy, I'll be sure to post
here my progress.  "
