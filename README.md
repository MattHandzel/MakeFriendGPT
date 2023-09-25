# MakeFriendGPT
Making friends is hard, and time consuming! Wouldn't it be a lot easier if you could do that *automatically*? Introducting my submission for the AI@UIUC Fall 2023 technical assessment. This project allows ChatGPT to talk to your friends when you are doing other things, personally, I like to go to bed early, but my friends do not, this is my solution! It also lets you automate the **boring** stages of making friends, particularily the getting to know you part.

## Installation and Usage
This project allows ChatGPT to send messages as if it was you through Snapchat, it does this by controlling your mouse and keyboard to send messages, so it looks more natural.
#### Packages Used
``` py
import json # data managment
import time # time management
import pynput # control keyboard and mouse
import numpy as np # used for controlling the bot
import pyscreenshot as ImageGrab # only necessary when collecting data if a conversation is very long
import pyperclip # allows access to keyboard
from emoji import is_emoji # figure out if emojis are in a persons name and stuff so we can remove those emojis
from chatgpt import ChatGPT # This is a chatgpt wrapper I found, install using pip install chatgpt
```
#### Installation
Excited to save hours of your life?

Install the github repository and required packages with the following commands:

``` bash
git clone git@github.com:MattHandzel/MakeFriendGPT.git
cd ./MakeFriendGPT/
pip install -r ./requirements.txt
```

After installing chatgpt with pip install chatgpt, run the following command and follow the prompts to login
``` bash
chatgpt install
```

Now you are set to run the program!
#### Usage

Open snapchat in a new tab, and then run the program! The following video has VSCode on the right side for debugging, but it works in fullscreen too!
![Demo](https://github.com/MattHandzel/MakeFriendGPT/assets/39449480/11a69196-d25f-4305-b688-cd89ee6891d2)

## How it works???
It might be surprising to believe that such a revolution in your social life can be done in a single python script, but it is!


