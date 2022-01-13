# synth.wsbogs.com

Welcome to the readme of the formerly wsbogs synth, now \<name to be determined / multiverse> synth. 

## FAQ

---

- Q: What is this?
- A: This is a client-side TTS (Text to Speech) website that aggregates and displays in real time all comments on Reddit stock community daily threads. This originally started as a project for the wsbogs community after karma farmers, bots, and the easily manipulated overran the original /r/wallstreetbets subreddit.

---

- Q: Why did you make this?
- A: As someone who works but also trades, I like to keep tabs on what's going on in the market without refreshing reddit all day or having it up; but more importantly, I like laughing at the shitposting and comments that go on in a given day. Since i'm using it, I figured I'd host it and give others access to give back to the community for making me money. Also, a good portfolio piece.

---

- Q: How are you profiting off of this, are you front running all our trades?
- A: No, but if I was doing that I wouldn't go through all the effort of making this site and just make a bot like all the other sites have. I designed this from the bottom up to be as cost effective as possible.

---

- Q: What browsers does this support.
- A: This should work in chrome, FF, and Edge. This also works on chrome for android and should work for chrome on iOs. This does not work in IE11 or Safari because IE11 is for boomers and Safari actively made the decision to not support the W3C standards around TTS (so they could upsell you on some apple product or some dongle, probably). I listen on my Pixel 6 all the time and it sounds great. 

---

- Q: Hey this doesn't work on my machine.
- A: Swing by the [Issues](https://github.com/drbergeron/wsb_synth_pub/issues) in git hub and let me know what's going on. Because this is client side most times you're in control of your own destiny and certain setups can cause this to work or not work. I can investigate though.

---

&nbsp;

# What's New?
v1.2.1

- fixed mute bots not working
- fixed mute emoji spam not working
- added logic to handle some different emoiji spam types
- added version to site so changes are more obvious?
- changed some backend logic for identifying emoji spam differently; maybe better, but definately differently.

---

v1.2 - Jan '22

What happened to 1.1? I released it at some point and never udpated this document. What's new in 1.2?

- Added options for muting emoji spam, saying usernames, muting bots, and altering the number of posts that stay on the feed.
- Added 2 new communities - MaxJustRisk and SuperSecretYachtClub
- Created a better option saving experience using cookies

--- 

v1.0 - July '21

Glad you asked, here's just what i could think about while making this document that 2 people will probably end up reading:

- I threw out the old [Reddit.net](https://github.com/sirkris/Reddit.NET) backend library i was using and created my own custom built thread-safe wrapper to handle this workload around the reddit API (parsing comments from absolute goons). This is a huge change to the overall process but i think it's more stable and allows me to fetch updates almost real-time.

- Now instead of just the OGs subreddit, the synth backend ingests comments from stickied daily threads from several different communities and then passes them to all clients subbed to that community's feed.
    - Open the settings menu on the top, check the boxes of communities you want to subscribe to. I save this info to your browser however localstorage works in javascript. Is it cookies? is it webworkers? Magic? I dont care enough to find out but just know it works.

- New **Mute Mode** that will only display posts to the feed once every 1.5 seconds and not attempt to play them. Perfect if you're trying to concentrate or want to throw it on a second monitor while you work.

- Tons of code stuff:
    - Re-organized and re-vamped the front end code
    - Front end now uses async/await promises instead of polling and functional js programming which i decided is not the tool for this job.
    - Updated SignalR to the latest version which fixes chrome, firefox, and edges tab throttling so the synth can stay up in the background
        - I filed an enhancement in signalR for the new Grouped Tabs chrome feature as that isn't currently handled.
---

## Usage Guide
Here's a quick guide for how to use the site:
- Press Play to load your computer's synthesized voices and connect to the community hub
- Click on the settings bar to:
    - Select your preferred voice, it's pitch, rate, and volume
        - I'm a big fan of "Google UK English Male" on Chrome and "Microsoft Natasha Online (Natural) that comes with Edge"
        - Because these voices are all client side, any issues may be resolved by installing diferent or additional voices on your machine. 
    - Select which communities you're subbed to
- If a speech is long running or just complete garbage click the "skip" button to go to the next one.
- The "Trim Backlog" button displays a badge telling you how many comments are queued up on your computer that have yet to be played.
    - Clicking will trim to the latest 3 comments.
- Clicking the Mute button in the middle will disable speech and just push comments to the feed once every 1.5 seconds.
- Comments:
    - Display shows the 10 most recent comments
    - Click the user's name to open the permalink to that comment
    - If the synth detects any tickers in the comment it will display them as blue pills on the right of the comment.
        - clicking any of these pills will open the ticker in marketwatch
    - If the synth detects any links in the comment it will create a pop-out link icon on the _far right_ you can click on to launch that link in a child tab
- If there are any problems connecting or the server goes down a reload button will appear, you can click this to reload the page. Click play again to re-connect.
- Total Users listening along are displayed on the upper right.
- The Octocat button on the bottom takes you here. 
- Donate to people and make the world a better place.

---

### Known Issues:
- Edge breaks on certain emojis and will cut saying the comment short on that emoji
    - i reported this to microsoft
- When i push a new version of the front end you get a weird refresh, just press play again
- I haven't figured out a good way to handle people pasting ascii art yet (bunch of emoji's x100 is said)
- Mac is unable to determine what voices you have installed so it just shows you all of them. You'll need to be aware of what your system voice is and have it selected on either your iphone or android device.
- Don't put the synth site in a chrome grouped tab, or disable the tab freezing flag in chrome if you do. Chrome freezes js in these groups after a while and it will stop working in the background.

---

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
            - This should work similar to windows 
        - Linux: 
            - Need one of you Tux commandos to test this on Gnome or something
            - This might be interesting to check out: - [Link](https://github.com/mozilla/TTS/tree/dev#install-tts)


### Bugs

Found one? Open up an [issue](https://github.com/drbergeron/wsb_synth_pub/issues) and i'll check it out if I have the means to reproduce.

### Other Notes:
 - I haven't had any issues with adblockers, proxys, VPNS, etc causing any issues with this so you should be gucci if you use any of those ([like](https://pi-hole.net/) I [tend](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm?hl=en) to [use](https://www.privateinternetaccess.com/)).
 - It physically pains me to say this but microsoft edge has a really good selection of voices available that it comes shipped with, same instructions for adding voices apply above.
 - Firefox comes with only the operating system voices, that i'm aware of. Will update if I find a way to add more across all OS.


 Original Synth [Post](https://www.reddit.com/r/wallstreetbetsOGs/comments/lsqn4l/brrrrrrrr_wars_return_of_the_synth/)
 
