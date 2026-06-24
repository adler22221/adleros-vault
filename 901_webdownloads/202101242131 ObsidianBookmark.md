#_GTD_0_inbox

My note: 

#excerpts
Author: Liamballin
Source: 
https://github.com/Liamballin/ObsidianBookmark
Retrieved {January 24, 2021}

> Chrome extension and nodejs server to allow web clipping to Obsidian. - Liamballin/ObsidianBookmark

# Liamballin/ObsidianBookmark
[![Screencap](https://github.com/Liamballin/ObsidianBookmark/raw/master/docs/sceencap1.gif)](https://github.com/Liamballin/ObsidianBookmark/blob/master/docs/sceencap1.gif)

The extension copies highlight areas of a web page to markdown, and sends it to a local node server. This then saves it as a markdown file in a folder, like an Obsidian vault, the user has chosen.

Until Obsidian supports adding new notes through their custom `Obsidian://` URL protocol, this might be the best way.

Inspired by jplattel's [Obsidian clipper](https://github.com/jplattel/obsidian-clipper) - a much less janky solution.

## Features

-   Automatically create a markdown note from a webpage.
-   Notes use a Zettelkasten identifier prefix, and the title of the webpage.
-   Downloads highlighted images to a custom attatchement folder, and updates links in the note.

## Roadmap

-   Allow adding tags in browser to recently saved note
-   Add config page to extension to set port and clip template
-   Download and link images asynchronously
-   Intergrate server into Obsidian plugin (?)

## Installation:

***

**For Mac or Linux, clone this repo and, in the server folder, run `npm install .` then `electron-packager .`. This will automatically crete a binary for your platform and architechture**

Download both .rar archives from [Releases](https://github.com/Liamballin/ObsidianBookmark/releases) page.

Extract files

#### Chrome extension:

Open chrome://extensions and turn on Developer mode in the top right. Select load unpacked and choose the extension folder.

#### Server:

Once the folder is extracted from the archive, running obsidian-bookmark.exe will launch the server. Choose a location for the vault root file and save location if different (Specific folder for web bookmarks)

## Usage

***

With the node server running, clicking the extension icon will save the current page as a markdown bookmark.

Any selected text or images will be included in the note.
