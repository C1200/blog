---
layout: post
categories: How

title: How? Internet Radio Station
author: C1200
tags: broadcasting
date: 2023-02-25 10:26:00 +0000

comments: true
---

## The backend

The backend is just a basic [Express](https://expressjs.com) server running with
[Socket.io](https://socket.io).

When the server receives an audio chunk from the broadcaster client it gets written straight to
[FFmpeg](https://ffmpeg.org) running as a child process of the server. FFmpeg then outputs a m3u8
playlist and a set of segment files into the public directory.

I also made an API to query for live and on demand streams.

## The frontend (broadcaster)

The frontend uses modern Web APIs such as the Web Audio API. I used this API to merge microphone
audio with the audio coming from the `<audio>` element (the one that plays the music). I then use
a `MediaRecorder` to record the merged audio. When each chunk of data is ready, it is sent off to
the server over Socket.io.

[Watch the demo](https://youtu.be/eYd5d7rvAZ4)