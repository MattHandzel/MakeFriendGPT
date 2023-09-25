# MakeFriendGPT
Making friends is hard, and time consuming! Wouldn't it be a lot easier if you could do that *automatically*? Introducting my submission for the AI@UIUC Fall 2023 technical assessment. This project allows ChatGPT to talk to your friends when you are doing other things, personally, I like to go to bed early, but my friends do not, this is my solution! It also lets you automate the **boring** stages of making friends, particularily the getting to know you part.

## Installation and Usage
#### Packages installed
```
import json # data managment
import time # time management
import pynput # control keyboard and mouse
import numpy as np # used for controlling the bot
import pyscreenshot as ImageGrab # only necessary when collecting data if a conversation is very long
import pyperclip # allows access to keyboard
from emoji import is_emoji # figure out if emojis are in a persons name and stuff so we can remove those emojis
from chatgpt import ChatGPT # This is a chatgpt wrapper I found, install using pip install chatgpt
```

After installing chatgpt with pip install chatgpt, run the following command and follow the prompts to login
```
$ chatgpt install
```

