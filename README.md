# Slippi Cumulative Stats

A script using [slippi-js](https://github.com/project-slippi/slippi-js) to calculate your overall and head to head win rates and play times from replays. Results are shown per character, stage, and nickname as well. You can specify your character, your opponent, your opponent's character, and even opponents to skip.

## Instructions
1. Download the program from the [Releases](https://github.com/BrodyVoth/slippi-cumulative-stats/releases/latest) page.
2. Move the program (`slippi-cumulative-stats-win.exe`) into the folder containing your `.slp` replay files. By default, this is `Documents/Slippi`, but may differ based on your Dolphin/Slippi settings.
3. Run it and follow the prompts.

Note: On Windows, replays created before Jun 30, 2020 may be in your FM-Slippi folder. (These old replays only count toward total play time, anyway)

## Example

![Example results](https://i.imgur.com/NWD7WbK.png)

## Win conditions
* Your opponent lost more stocks than you **or**
* You finished with the same amount of stocks but a lower percent than your opponent

Otherwise, it's considered a loss. Matches are ignored if they are shorter than 30 seconds, contain no deaths, or are incomplete. For example, matches where players SD or quit immediately (LRA-Start) are excluded to avoid skewing stats.

Note: LRA-Start detection is currently disabled due to inaccurate data.

## Run from source
Requires Node.js.

1. Place slippi-stats.js and package.json in a folder with replays
2. Open a command line in the directory and run `npm install`
3. Run `node slippi-stats.js`

## Troubleshooting

**"User(s) missing. Ignoring..."**  
  This message appears when the replay is missing key player data. This can happen if the match is from before July 2020 or if the tool cannot detect a valid connect code. These replays are skipped to preserve data accuracy.

**Nothing is showing up in results**  
  Make sure the tool is in the same folder as your `.slp` files and that those replays are from games with at least one completed stock exchange.

