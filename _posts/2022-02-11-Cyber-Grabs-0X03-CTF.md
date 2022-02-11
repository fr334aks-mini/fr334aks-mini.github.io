---
layout: post
title: "Cyber Grabs 0X03 Junior CTF"
date: 2022-01-22
image: ../../assets/img/Posts/cybergrabs.png
categories: [CTF-TIME]
tags: [wireshark, osint, rev, steg, crypto]
---

Hey and welcome to our new blog. Last week the team participated in the Cyber Grabs 0X03 Junior CTF which was a 12 Hours Jeopardy style team CTF

| CTF            | Cyber Grabs 0X03 Junior CTF                            |
| -------------- | ------------------------------------------------------ |
| CTF Start Time | Sun, 06 Feb. 2022, 07:30 EAT                           |
| CTF End Time   | Sun, 06 Feb. 2022, 19:30 EAT                           |
| CTF Time Event | [link](https://ctftime.org/event/1556)                 |
| Team           | [Fr334aks-Mini](https://ctftime.org/team/175491)       |
| Players        | 05t3, Winter, ★sW33t_1mPur1t13s, \_k0imet, n3rd, Parsz |

We managed to solve 21/29 challenges where we emerged 44/285 teams with 2750 points. In general, the challenges were fun despite a few challenges with the Infra.

![image](https://user-images.githubusercontent.com/58165365/153565716-a74139db-c830-4054-acb9-ce8fc2e49335.png)

# OSINT

# Misc

# Reverse

# Forensic

## Mr Robot

> Mr. Robot most famous TV show but least people know about it.

> _Solved by 05t3_

We are presented with a `.wav` file and the first thing that comes to my mind is using [Audacity](https://www.audacityteam.org/download/) & [Sonic Visualizer](https://www.sonicvisualiser.org/download.html) to check if the flag is visible on the spectogram. Turns out that was a dead end. After sometime of research, i came across a tool on github that could get the flag, `stegolsb`. To install it, simply run:

```
git clone https://github.com/ragibson/Steganography
cd Steganography
python3 setup.py install
```

`stegolsb wavsteg -r -i sound_steg.wav -o output.txt -n 1 -b 1000`

Breaking down the command above:

- WavSteg uses least significant bit steganography to hide a file in the samples of a .wav file.
- `-r` - is for recovering data from a sound file.
- `-i` - Path to a .wav file.
- `-o` - Path to an output file.
- `-n` - lsb-count (How many LSBs to use [default: 2])
- `-b` - How many bytes to recover from the sound file

For more information on stego-lsb, check out the official [project description.](https://pypi.org/project/stego-lsb/)

![image](https://user-images.githubusercontent.com/58165365/153573071-7d8d8a70-decc-4439-a2fb-551acb2af3cb.png)

FLAG: `CYBERGRABS{3VERY_8YTE_4RE_REAL_VALUE}`

# Web

# Crypto
