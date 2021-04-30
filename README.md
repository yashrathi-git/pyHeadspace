# pyHeadspace
Command line script to download headspace packs, singles or everyday headspace OR download all packs at once.
<p align="center">
<img src = "https://raw.githubusercontent.com/yashrathi-git/pyHeadspace/main/images/demo-f.gif" alt = "demo">
</p>


## Installation
```sh
pip install --upgrade pyheadspace
```


### This tool is only meant for personal use. Do not use this for piracy!
***
## Setup

Run and enter login credentials.
```sh
headspace login
```

 

## Usage

## Download all packs at once
```sh
# Download all packs with each session of duration 15 minutes
headspace pack --all --duration 15

# Download all packs with session duration of 10 & 20 minutes
headspace pack --all --duration "[10,20]"
```
**Exclude specific packs from downloading:**
<br />

To exclude specific packs from downloading use `--exclude` option.
<br />
It expects location of text file for links of packs to exclude downloading. Every link should be on separate line.<br><br>
**links.txt**:
```
https://my.headspace.com/packs/5
https://my.headspace.com/packs/6
```
**command**
```sh
headspace packs --all --exclude links.txt
```
This would download all packs except the ones in `links.txt` file

## Downloading specific Headspace pack
```sh
headspace pack <URL> [Options]
```
It expects URL in format `https://my.headspace.com/packs/<int>`

<br />

**BASIC USAGE**
```sh
# Download with all session of duration 15 minutes
headspace pack https://my.headspace.com/packs/33 --duration 15 

# Download sessions of multiple duration
headspace pack https://my.headspace.com/packs/33 --duration "[20, 15, 10]"    

```
**Options:**
```sh
--id INTEGER         ID of video.
-d, --duration TEXT  Duration or list of duration
--no_meditation      Only download meditation session without techniques
                    videos.
--no_techniques      Only download techniques and not meditation sessions.
--out TEXT           Download directory
--all                Downloads all headspace packs.
-e, --exclude TEXT   Use with `--all` flag. Location of text file with links
                    of packs to exclude downloading. Every link should be
                    on separate line.
--help               Show this message and exit.

```

## Download single session
```sh
headspace download <URL> [options]
```

It expects URL in format `https://my.headspace.com/play/<int>`

<br />

**BASIC USAGE**
```sh
headspace download https://my.headspace.com/play/520 --duration 15
# Download sessions of multiple durations
headspace download https://my.headspace.com/play/520 --duration "[15,20]"
```
**Options:**
```sh
--out TEXT           Download directory.
--id INTEGER         ID of the video. Not required if URL is provided.
-d, --duration       Duration or list of duration
--help               Show this message and exit.
```


## Download everyday meditations
```sh
headspace everyday [OPTIONS]
```
**How to get your user id?** <br>
1. Go to https://my.headspace.com/everyday-headspace/info
2. Open developer tools using `Ctrl + Shift + I` or `Command + Shift + C`
3. Go to network tab and reload the webpage
4. Find a GET request made to URL: https://api.prod.headspace.com/content/view-models/everyday-headspace-banner
5. You would find your userId as query parameter in the URL.
<br>

**BASIC USAGE**
```sh
# Downloads today's meditation
headspace everyday --userid <YOUR USER ID>

# Download everyday meditation of specific time period.
# DATE FORMAT: yyyy-mm-dd
headspace everyday --from 2021-03-01 --to 2021-03-20 --userid <YOUR USER ID>
```
**Options**
```
--userid TEXT
--from TEXT          Start download from specific date. DATE-FORMAT=>yyyy-
                    mm-dd
--to TEXT            Download till a specific date. DATE-FORMAT=>yyyy-mm-dd
-d, --duration TEXT  Duration or list of duration
--out TEXT           Download directory
--help               Show this message and exit.
```

**If you encounter any issue or bug, open a new issue on [github](https://github.com/yashrathi-git/pyHeadspace)**



