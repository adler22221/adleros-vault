#_GTD_0_inbox

Created on: [[20230409]]
Who's involved: 
About what: 

My note: 

Author: Stephen Millard
Source: 
https://www.thoughtasylum.com/2023/01/29/obsidian-daily-task-list/
Retrieved 

> My use of Obsidian as a personal knowledge management (PKM) tool sees me making extensive use of daily notes. Each day I work, I create a new note and use it to keep an activity journal of all the key things I have done, link out to notes for meetings I have attended, things I have learned, etc. I also display my key tasks (for today and a soon as possible) and record any of the key tasks I have completed that day. I have always taken to cutting and pasting to transfer incomplete tasks to transfer them forward to the next daily note. But after having tried out Roam Research a few years ago and working with their task management approach, I have always felt that my method was inefficient; but as with many things Obsidian, I found a better way utilising a third-party plugin.

# An Obsidian Daily Task List
29 Jan 2023

My use of [Obsidian](https://obsidian.md/) as a personal knowledge management (PKM) tool sees me making extensive use of daily notes. Each day I work, I create a new note and use it to keep an activity journal of all the key things I have done, link out to notes for meetings I have attended, things I have learned, etc. I also display my key tasks (for today and a soon as possible) and record any of the key tasks I have completed that day.

I have always taken to cutting and pasting to transfer incomplete tasks to transfer them forward to the next daily note. But after having tried out [Roam Research](https://roamresearch.com/) a few years ago and working with their task management approach, I have always felt that my method was inefficient; but as with many things Obsidian, I found a better way utilising a third-party plugin.

## Aspiration

What I had always wanted was to be able to embed a daily task list into my daily note and keep my tasks centrally. That is easy enough using the [standard Obsidian embed functionality](https://help.obsidian.md/Linking+notes+and+files/Embedding+files), but then to edit them I would need to open the central task note, and if I wanted to mark off a task and keep it in that day’s daily note, I would end up copying around different panes or windows in Obsidian.

Now this is certainly possible, but it had a feel of friction to it, and I often have multiple notes open, and being in effect forced to open an additional note to edit information that was already on screen, well, that just niggled at me enough to make me not want to use it. Instead I just dealt with the friction once on a daily basis and with a quick cut and paste moved the incomplete tasks across from the previous to the current daily note.

## Enabling Editable Embeds

The plugin that has improved my position is the [make.md plugin for Obsidian](https://www.make.md/). This plugin provides a set of functionality intended to “enhance your Obsidian experience”. I intentionally do not use all of the features, for example, I find the _Maker Mode_ just gets in my way as I am quite comfortable with working in Markdown - but the plugin aims to provide features for novice Obsidian users through to those they term an “Obsidian Magician”. It also allows you to disable features you do not want to use - a big thank you to the considerate developers of this plugin on that one.

The functionality that helps with this particular use case is one they called _Flow_, which is based on the [Hover Editor plugin](https://github.com/nothingislost/obsidian-hover-editor). Whereas Hover Editor provides a fantastically flexible pop-up editor for an embedded note, _Flow_ allows you to edit the embedded note in situ. This fits much more with my mental model and I find to be a cleaner interface reminiscent of the Roam Research way of dealing with updating embeds. Of course the name of the feature gives it away as it is intended to keep you in the flow of the work in your current note, which is exactly my preference.

## A Closer Look

While the Make.md plugin has some great features, its documentation is currently lacking detail, so I am going to try and highlight the details of the _Flow_ feature to make this work.

In the settings for the Make.md plugin, there is a section _Flow Editor_. The default settings should be those shown below, and these settings are exactly how I have left it. While you can change the Flow Editor Style, the “Seamless” integration is exactly what I was looking for.

![](https://www.thoughtasylum.com/assets/images/2023/2023-01-29-settings.png)

With the settings in place, I can place of my tasks are placed in a single ‘Daily Tasks’ note with the intent of embedding this in an editable way into my daily notes.

![](https://www.thoughtasylum.com/assets/images/2023/2023-01-29-daily-tasks.png)

The tasks note can the be embedded into my daily note using `![[Daily Tasks]]` (and this is built into my daily notes template). In the screenshot below, you can see this, and beneath it the embedded content, but you may also note that on the right of the embed are a couple of additional icons. An infinity symbol and a link symbol. The infinity symbol is for locally toggling the flow feature on and off. The link symbol is for opening the original note in the current Obsidian panel (just like it does when you usually click on a link).

![](https://www.thoughtasylum.com/assets/images/2023/2023-01-29-today-noflow.png)

In the screenshot above, flow is disabled, and the text in the embedded note is displayed read only.

In the screenshot below, you can see the flow icon is a different colour. It is enabled, and the text is editable, with any changes being automatically reflected in the original Daily Tasks note. If you place the cursor on the embed line shown previously, you’ll also note that the embed code is not displayed. You need to switch out of Flow to see it in the editor (but it is still there in the note, it is just hidden from view).

![](https://www.thoughtasylum.com/assets/images/2023/2023-01-29-today-flow.png)

When I tick things off on the list, I just cut and paste them a few lines above. It would be amazing to be able to use the “move line up” command in Obsidian, but this actually works in the current note. You may notice that when editing the embedded note, there is a cursor in both the embedded note (e.g. Daily Tasks) and the note it is embedded in (e.g. daily note). While typing affects the embedded note, Obsidian commands will affect the other note.

All things considered, this is a minor inconvenience, and one I am perfectly willing to live with.

## Don’t Forget Your Canvas

In addition to the daily note, I also embed my daily tasks list into a canvas I use as a dashboard. I don’t need the Make.md plugin to do this, but the Make.md plugin allows me to have my daily task list in a centralised note, and this in turn allows me to bring it into the canvas.

![](https://www.thoughtasylum.com/assets/images/2023/2023-01-29-canvas.png)

You can also embed your daily note (both are shown here), but there’s a trick I’ve used to do that and I’ll cover that in a separate post; and you may notice that the embed does not get pulled in automatically. But for a dashboard like this, again it is something I can accept as generally I’m using this as a reference space rather than a space where I am going to be working on my notes directly.

## Summary

This embedding of a centralised list of daily tasks into my daily notes is a pretty straight forward set up and this is something I was craving for quite some time. It is only with the release of the Make.md plugin that this became possible to accomplish in a way that, for want of a better term, ‘flowed’ for me. One of the embed features that had spoiled me in my early experimentation in Roam Research is now accessible in Obsidian which is a big plus for me in my daily workflow of capturing information.

While the screenshots here are an example from my Obsidian demo vault, my real world usage is exactly the same. Just using different tasks and a slightly more involved daily notes and dashboards. But, hopefully this gives you a good flavour for a use case for the _Flow_ feature in Make.md.
