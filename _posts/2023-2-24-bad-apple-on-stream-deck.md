---
layout: post
categories: How

title: How? Bad Apple on Stream Deck
author: C1200
tags: bad-apple
date: 2023-02-24 11:46:00 +0000

comments: true
---

I started off making the Stream Deck plugin by using ffmpeg to get the frames of Bad Apple as
individual image files and loading them on to the Stream Deck key by using the setImage function.

This, however, did not work. Therefore, I tried making it play videos using a HTML `<video>` tag,
drawing the video to a HTML `<canvas>` and using the Stream Deck setImage function. This did work.
After that I made it work with YouTube and Spotify using their embeds. Finally, I added progress
bars by using `CanvasRenderingContext2D.fillRect`.

[Watch the video](https://youtu.be/W1XYDhrImqI)
