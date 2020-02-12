# Contributing
Contributions to the yuzu Games Wiki are welcomed, as keeping all of the data up to date and accurate is a community effort.

**Table of Contents**:
- [Info About This Wiki](#info-about-this-wiki)
  - [Angle Brackets](#angle-brackets)
  - [yuzu Version](#yuzu-version)
  - [Dates](#dates)
  - [GitHub Issues](#github-issues)
  - [Screenshots](#screenshots)
  - [Title IDs](#title-ids)
  - [TOML](#toml)
- [Code](#code)
  - [Icon](#icon)
  - [Game Screenshots](#game-screenshots)
  - [Savefiles](#savefiles)
    - [Save Metadata](#save-metadata)
    - [Save Data](#save-data)
- [Wiki](#wiki)

## Info About This Wiki

### Angle Brackets
Throughout this guide, code blocks like `<Value>` are used. This means that "Value" should be replaced by something, and the "<>" should be deleted.

### yuzu Version
All data must be collected from the latest official yuzu releases, downloaded from [here](https://yuzu-emu.org/downloads/).

### Dates
All dates follow the format `<4-Digit Year>-<2-Digit Month>-<2-Digit Day>`. For example, June 3rd 2017 would be "2017-06-03".

### Screenshots
The recommended application for capturing the icon is [ShareX](https://github.com/ShareX/ShareX) while we recommend using the `Capture Screenshot` feature within yuzu itself for game screenshots. Screenshots can not be compressed, and must be in the PNG format.

## Code
The code consists of the actual files in the Github repisitory. To modify them, you have to fork this repo, make your changes, and send a pull request.

At the root, there's a folder for each game. The names of these folders should follow these specifications:
- Only use letters, numbers, and hyphens (No spaces!), because they will be linked to on the site.
- Names should be lowercase to ensure consistency.
- Have a wiki page with the same name.

### Icon
The icon for a game is located at `/<Game Name>/icon.png` (See: [Screenshots](#screenshots). The suggested process for getting one is:
- Make sure the game is in your yuzu game directory.
- Set the icon size to `Full Size (256x256)` in the yuzu Configuration.
- Take a screenshot of yuzu's library listing (See: [yuzu Version](#yuzu-version)).
- Crop out the game icon.
- The icon should be `256x256`.

### Game Screenshots
The screenshots for the game are located in `/<Game Name>/screenshots/` (See: [Screenshots](#screenshots)). Screenshots **must** have a resolution of `1280x720`.

Additionally, if a game has a rating of 3 or higher, **you must include at least 3 screenshots**, otherwise 1 screenshot is acceptable. The names of the screenshots don't matter.

### Savefiles
#### Save Metadata
The metadata for a save is located at `/<Game Name>/savefiles/<Save Name>.dat`. This is info about the save. The DAT values (See: [TOML](#toml)) are:
- `title` (String): The location of the save ingame.
- `description` (String): A brief explanation about the save.
- `author` (String): Your forum account name, if you have one. If you don't, don't include this line.
- `title_id` (String): Title ID of the game.

#### Save Data
The save data is located at `/<Game Name>/savefiles/<Save Name>.zip` (See: [yuzu Version](#yuzu-version)). To make a ZIP file, the process is:
- Make sure the game is in your yuzu game directory.
- Right click on the game and click `Open Save Data Location`. This should open a window prompting you to select the user.
- After selecting the user, you will be taken to the folder in which the save data is stored.
- Compress the files within the folder into a ZIP.

## Wiki
The wiki contains info about specific game problems, and can be modified by anyone. They use [Markdown](https://guides.github.com/features/mastering-markdown/) formatting.

Each page's title should match the game's respective folder in the code section, except with hyphens in the code changed to spaces on the wiki. **Don't use the following characters in your wiki page's titles: \ / : * ? " < > |.**

The format of each page is as follows:
- H2 header with text saying `Summary`.
- Brief summary of how the game performs: graphically, auditorily, and frame rate (with general hardware comparison - see MK7 example). See: [yuzu Version](#yuzu-version).

An example of a game wiki page is the one for [Pokemon: Let's Go](https://github.com/yuzu-emu/yuzu-games-wiki/wiki/pokemon-lets-go):
```markdown
Pokemon: Let's Go series currently experiences freezes called softlocks in yuzu.
This currently makes the game unplayable, but does not have major issues aside from the softlocks.

Pokemon: Let's Go goes ingame if you follow the instructions below:

* Dump a save. You can also use ones from the `Savefiles` section.
* Dump and use your NAND and keys from your console following our [quickstart guide](https://yuzu-emu.org/help/quickstart/).
* Choose the "Single Player - Handheld - Undocked" in `Emulation > Configure... > Input`

#### How to get past the controller selection screen
* In the Input Configuration tab, and choose the "Single Player - Handheld - Undocked" profile.
```
