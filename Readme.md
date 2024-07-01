# Hexacore Auto Click / Auto tapper / Bot(no)
All actions can be done in browser Developer tools (F12)
Nothing needed to download, no insecure/sensitive requests

## main channel https://t.me/silencekey

Via small reverse engineering i made a script for autotapping https://t.me/HexacoinBot
So, first thing, that you need is auth token, you can recieve it with one request, that you can make even from browser:

userId `112233` is your telegram id, you can get it from https://t.me/getmyid_bot
Username aka `nickname` is kinda useless, so just your @name from telegram without @;

```
fetch("https://ago-api.onrender.com/api/app-auth", {
  "headers": {
    "accept": "*/*",
    "cache-control": "no-cache",
    "content-type": "application/json",
    "pragma": "no-cache",
    "priority": "u=1, i",
    "sec-ch-ua": "\"Not/A)Brand\";v=\"8\", \"Chromium\";v=\"126\", \"Microsoft Edge\";v=\"126\", \"Microsoft Edge WebView2\";v=\"126\"",
    "sec-ch-ua-mobile": "?0",
    "sec-ch-ua-platform": "\"Windows\"",
    "sec-fetch-dest": "empty",
    "sec-fetch-mode": "cors",
    "sec-fetch-site": "cross-site",
    "Referer": "https://ago-wallet.hexacore.io/",
    "Referrer-Policy": "strict-origin-when-cross-origin"
  },
  "body": "{\"user_id\":112233,\"username\":\"nickname\"}",
  "method": "POST"
}).then(r=>r.json()).then(console.log)
```
After this request you will see your auth token, save it for use in next step

Replace value in " " with your token, adjust target amount and tap speed with values
of targetTaps and perTick;
You can just change 10000 to 1000, etc => total amount of taps that script need to imitate;

```
(async () => {
    const sleep = (ms) => {
        return new Promise((resolve) => setTimeout(resolve, ms));
    };
    const auth = "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2Vy....";
    const targetTaps = 10000;
    const perTick = 30;
    for (let i = 1; i * perTick < targetTaps; i++) {
        let res = await fetch("https://ago-api.onrender.com/api/mining-complete", {
            headers: {
                accept: "*/*",
                authorization: auth,
                "cache-control": "no-cache",
                "content-type": "application/json",
                pragma: "no-cache",
                priority: "u=1, i",
                "sec-ch-ua": '"Not/A)Brand";v="8", "Chromium";v="126", "Microsoft Edge";v="126", "Microsoft Edge WebView2";v="126"',
                "sec-ch-ua-mobile": "?0",
                "sec-ch-ua-platform": '"Windows"',
                "sec-fetch-dest": "empty",
                "sec-fetch-mode": "cors",
                "sec-fetch-site": "cross-site",
                Referer: "https://ago-wallet.hexacore.io/",
                "Referrer-Policy": "strict-origin-when-cross-origin",
            },
            body: `{"taps":${perTick}}`,
            method: "POST",
        });
        res = await res.json();
        if (!res.success) {
            console.log("Tapping error", res);
        }
        console.log(`Taps made: ${i * perTick}`);
        sleep(50);
    }
})();
```
voulia, just wait

Any questions? Feel free to comment in Telegram channel or open Issue, this repo just a `scratch pad`

just a bit seo tags?
Hexacore, https://t.me/HexacoinBot, Hexacore | UGC | AGO, Autoclicker, Bot, Autotapper,
Also a bit tags from scam repos, pls dont shame c:

hexacore auto bot free download / hexacore auto clicker Hi everyone today we present you our bot for crypto game hexacore with which you can automate the whole process in the game which is possible hexacore scripts / hexacore clicker / hexacore tool / hexacore toolkit
