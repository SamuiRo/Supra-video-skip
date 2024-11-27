# Supra-video-skip
How to scip supra video before claim tokens


SUPRA

HOW to skip this SHIT Video before claim? 

1. Open browser console (f12)
2. Paste this and change video duration:
```javascript
const script = document.createElement('script');
script.src = "https://player.vimeo.com/api/player.js";
document.body.appendChild(script);

script.onload = () => {
    const iframe = document.querySelector('iframe[src*="vimeo.com"]');
    if (iframe) {
        const player = new Vimeo.Player(iframe);

        // scip to end
        player.setCurrentTime(256); // HERE you should change video duration 256 — video duration in seconds
    }
};
```

And press Enter

3. How to get video duration?

Send this:
```javascript
const script = document.createElement('script');
script.src = "https://player.vimeo.com/api/player.js";
document.body.appendChild(script);

script.onload = () => {
    const iframe = document.querySelector('iframe[src*="vimeo.com"]');
    if (iframe) {
        const player = new Vimeo.Player(iframe);

        // scip to end
        player.setCurrentTime(1); 
    }
};
```
You will see something like this: 
```javascript
VM4569 player.js:2 
 Uncaught (in promise) RangeError: Seconds must be a positive number less than the duration of the video (1113.233).
    at VM4569 player.js:2:17300
    at Array.forEach (<anonymous>)
    at z (VM4569 player.js:2:17274)
    at c._onMessage (VM4569 player.js:2:26369)
```

You can find video duration in (), in my case it is 1113.223


