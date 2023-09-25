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

#### Usage
Be sure to open whitelist.json and add the names of the people you want ChatGPT to talk to
```json
[
  "Average Joe",
  "Joe Smith",
  "Friendly Joe",
  "REPLACE THESE NAMES :)"
]
```

Then, open snapchat in a new tab, and run the program! The bot will move your mouse around, opening chats and messaging people without you having to lift a finger!

![Demo](https://github.com/MattHandzel/MakeFriendGPT/assets/39449480/11a69196-d25f-4305-b688-cd89ee6891d2)

## How it works???
It might be surprising to believe that such a revolution in your social life can be done in a single python script, but it is!

#### The Magic
This script uses a ChatGPT wrapper to send prompts to ChatGPT and receive messages from it. Because you login using your openai account, you don't need to do anything with your API key, so this is very easy for people with no programming experience to use.

**How it works**
1. Scan for any new chats
2. If there is a new chat, check to see if the name of that person is in whitelist.json
3. If so, continue to step 4, else continue to step 1
4. Open the chat and copy what the user and the other person were saying into the clipboard, use pyperclip to send that data to ChatGPT
5. Send the conversation to ChatGPT, with the following prompt: 
```txt
"Your instruction is to continue what the character \"ME\" would say next in following conversation ME is trying to make friends with the other person. ME is very funny, a good listener, and talks casually. IMPORTANT: Only respond with what ME would say next\n The conversaion is delimited in triple backticks\n ```{conversation}```"   
```
Where *conversation* is the current conversation
6. When response is received, parse response
7. Send response to soon-to-be-friend
8. Close chat and wait again