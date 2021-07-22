# synth.wsbogs.com

Welcome to the readme of the formerly wsbogs synth, now \<name to be determined> synth. 

## FAQ

---

- Q: What is this?
- A: This is a client-side TTS (Text to Speech) website that aggregates and displays in real time all comments on Reddit stock community daily threads. This originally started as a project for the wsbogs community after karma farmers, bots, and the easily manipulated overran the original /r/wallstreetbets subreddit.

---

- Q: Why did you make this?
- A: As someone who works but also trades, I like to keep tabs on what's going on in the market; but more importantly, i like laughing at the shitposting and comments that go on in a given day without having to constantly refresh a reddit feed.

---

- Q: How are you profiting off of this, are you front running all our trades?
- A: No, but if I was doing that I wouldn't go through all the effort of making this site and just make a bot like all the other sites have. 

---

- Q: What browsers does this support.
- A: This should work in chrome, FF, and Edge. Does not work in IE11 or Safari because IE11 is for boomers and Safari actively made the decision to not support the W3C standards around TTS (so they could upsell you on some apple product or some dongle, probably).

---

- Q: Hey this doesn't work on my machine.
- A: Swing by the [Issues](https://github.com/drbergeron/wsb_synth_pub/issues) in git hub and let me know what's going on. Because this is client side most times you're in control of your own destiny and certain setups can cause this to work 

---

&nbsp;

# What's New?

Glad you asked, here's just what i could think about while making this document that 2 people will probably end up reading:

- I threw out the old [Reddit.net](https://github.com/sirkris/Reddit.NET) backend library i was using and created my own custom built thread-safe wrapper to handle this workload around the reddit API (parsing comments from absolute goons). This is a huge fucking change to the overall process but i think it's more stable and allows me to fetch updates almost real-time.

- Now instead of just the /r/wallstreetbetsogs subreddit, the synth backend ingests comments from stickied daily threads from several different communities and then passes them to all clients subbed to that communities feed.
    - Click the antenna symbol in the middle, check the boxes of communities you want to subscribe to. I save this info to your browser however localstorage works in javascript. Is it cookies? is it webworkers? I dont give a care enough to find out but just know it works.

- New **Mute Mode** that will only display posts to the feed once every 1.5 seconds and not attempt to play them. Perfect if you're trying to concentrate or want to throw it on a second monitor while you work.

- Pick a voice:
    - Click the microphone button to select from available voices on your computer, adjust the pitch, rate, and volume. 
    - Because these voices are client side, any issues could be resolved by installing voices on your machine. 

## Troubleshooting

- Something's being weird
    - Try refreshing the page and re-pressing play
- I wish there was more voices
    - So because this is client-side it runs off the voices on your computer, if you want more, you can probably just add them! how cool!
        - Windows: Bill Microsoft's directions are excessive for this process, so here's what you do:
            - Go to settings, 
            - search for "speech", click on speech settings, 
            - Go to the "Manage Voices" section, click Add. 
            - Pick one and re-start your browser and it should be there.
            - Here's official instructions if you want them - [Link](https://support.microsoft.com/en-us/topic/download-voices-for-immersive-reader-read-mode-and-read-aloud-4c83a8d8-7486-42f7-8e46-2b0fdf753130)
        - Mac toy computers: 
            - Coming soon
        - Linux: 
            - Need one of you Tux commandos to test this on Gnome or something
            - This might be interesting to check out: - [Link](https://github.com/mozilla/TTS/tree/dev#install-tts)


### Bugs

Found one? Open up an [issue](https://github.com/drbergeron/wsb_synth_pub/issues) and i'll check it out if I have the means to reproduce.

### Other Notes:
 - I haven't had any issues with adblockers, proxys, VPNS, etc causing any issues with this so you should be gucci if you use any of those ([like](https://pi-hole.net/) I [tend](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm?hl=en) to [use](https://www.privateinternetaccess.com/)).
 - It physically pains me to say this but microsoft edge has a really good selection of voices available that it comes shipped with, same instructions for adding voices apply above.