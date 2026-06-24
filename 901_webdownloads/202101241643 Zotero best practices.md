#_GTD_0_inbox

My note: 

#excerpts
Author: 
Source: 
https://forum.obsidian.md/t/zotero-best-practices/164/57
Retrieved {January 24, 2021}

> I've posted the plugin I wrote before in Zotero integrations, but I thought I'd add here a few things that could help make the most of Zotero (and also of the mdnotes plugin itself).  How to Extract annotations and highlights Zotfile will extract annotations from your PDF and store them as notes in Zotero. The notes include links to the specific page in the PDF where the highlight was made:    You can configure how to format these HTML notes with Zotfile's hidden preferences, check the .pdfExtra...

# Zotero best practices
I've posted the plugin I wrote before in [Zotero integrations 160](https://forum.obsidian.md/t/zotero-integrations/91/30), but I thought I'd add here a few things that could help make the most of Zotero (and also of the mdnotes plugin itself).

## How to

### Extract annotations and highlights

Zotfile will [extract annotations 75](http://zotfile.com/#extract-pdf-annotations) from your PDF and store them as notes in Zotero. The notes include links to the specific page in the PDF where the highlight was made:

![[9e63c1605c82efe3fca3f4cee2269ed2520bcce3.png]]

You can configure how to format these HTML notes with Zotfile's hidden preferences, check the .pdfExtraction settings [here 87](http://zotfile.com/#hidden-options)

Keep in mind that if you annotate your PDFs, Zotfile is also able to extract “pop-up notes”, but not inline notes. These highlights:

[![[635d0abaf4719f056098117ea9284e40d7fac4e9_2_517x258.png]]

image870×436 57 KB

](https://forum.obsidian.md/uploads/default/original/2X/6/635d0abaf4719f056098117ea9284e40d7fac4e9.png "image")

End up in this note:  
![[7c1145f41f9040b4d9ace75ea23460b11f550860.png]]

#### Splitting annotations and Highlights into different notes

There are a few settings worth looking into, depending on your workflow:

-   By default, the `extensions.zotfile.pdfExtraction.colorNotes` setting is turned off, which means all the highlights and annotations will be extracted to a single note.
    -   You can change the format of the title with `extensions.zotfile.pdfExtraction.formatNoteTitle`
        
    -   Setting `extensions.zotfile.pdfExtraction.colorAnnotations` to true, will add the color as a background in the annotations, and you can use `%(color_category)` to add labels in `extensions.zotfile.pdfExtraction.formatAnnotationHighlight` according to the colors in `extensions.zotfile.pdfExtraction.colorCategories`
        
        [![[998b92e16544c96649f34ad8695d1356e49ea98c.png]]
        
        image328×535 29.4 KB
        
        ](https://forum.obsidian.md/uploads/default/original/2X/9/998b92e16544c96649f34ad8695d1356e49ea98c.png "image")
        
-   Splitting notes by color can be turned on by setting `extensions.zotfile.pdfExtraction.colorNotes` to true
    -   You can customize the title of the note in `extensions.zotfile.pdfExtraction.formatNoteTitleColor`

### Export notes to markdown

Now that you have notes attached to your Zotero reference, you can export the reference's metadata and your highlights and annotations to a markdown file.  
The menus in Zotero are unfortunately not context-aware, so to know what to select for each menu follow the [cheatsheet 55](https://github.com/argenos/zotero-mdnotes#features) at the top of the README of mdnotes. The plugin helps with the following:

-   [Exporting metadata of a reference 43](https://github.com/argenos/zotero-mdnotes#Export-items-metadata-to-a-markdown-file)
-   [Exporting Zotero notes 34](https://github.com/argenos/zotero-mdnotes#Export-Zotero-notes-to-markdown) (e.g. those extracted by Zotfile or literature notes written by you)
    -   The export format for markdown is a little hardcoded (right now), but you can experiment with changing Zotfile's notes formats and include markdown or wikilinks in your annotations:  
        
        [![[3afd46d68f01baac9b316c06d3a449ac438fa84d_2_517x116.png]]
        
        image694×156 33.9 KB
        
        ](https://forum.obsidian.md/uploads/default/original/2X/3/3afd46d68f01baac9b316c06d3a449ac438fa84d.png "image")
        
          
        
        [![[8e56a965f6db3801980bfbd7bd9ffda8064773dd_2_517x195.png]]
        
        image759×288 37.3 KB
        
        ](https://forum.obsidian.md/uploads/default/original/2X/8/8e56a965f6db3801980bfbd7bd9ffda8064773dd.png "image")
        
    -   If you want to structure your notes, you can use underline (instead of highlight) to create H4 headings. A PDF like this:  
        ![[5575b570f0ed3841149c5bd7d4267df0f5695788.png]]
    -   After being exported, results in a markdown note like this:  
        
        [![[51d8b072d3771df32835d40894938f225913c7a1_2_517x292.png]]
        
        image770×436 36.4 KB
        
        ](https://forum.obsidian.md/uploads/default/original/2X/5/51d8b072d3771df32835d40894938f225913c7a1.png "image")
        
-   [Creating a file for your notes 22](https://github.com/argenos/zotero-mdnotes#Create-a-file-for-your-own-notes). Since this file contains your notes, this is the only file that **won't be overwritten** during batch export. If you want to replace it, you can choose the `Create Notes file` menu.

The plugin also can add these files you created as links to Zotero so you can double click them and edit them.

The default settings export all the information of the references in multiple files. If that doesn't work for you, there some settings to play around with, depending on what you want:

-   If you don't want to “pollute” your graph, you can choose to export everything in a single file.
-   If you don't want to include highlights and annotations in your export (e.g. as literature notes), you can either disable them in the settings so they're not included in the export. If you export everything in a single file, you can have the metadata in the same file.
-   Instead of using batch export on every item, selectively choose what you send to your vault by using the individual menus.

### Get links to a Zotero item or PDF

You can use Zutilo to get a link to the Zotero item or a PDF. You want to enable `Copy select item links` in Zutilo's settings so that it shows up in the context menu or as a shortcut. That will give you a link with Zotero's URL e.g. zotero://select/library/items/FE7B33LA which you can format in markdown.

Update: @silent(/u/silent) developed a Zotero translator to easily copy markdown-formatted zotero links [here](https://forum.obsidian.md/t/zotero-best-practices/164/72).

### Web clipping

In order to successfully use Zotero to save articles, it should have a “translator” that can correctly get the data for the citation out of it. You can find a list of existing translators [here 56](https://www.zotero.org/support/translators)

## Plugins

-   [ZotFile - Advanced PDF management for Zotero 84](http://zotfile.com/)
-   [Better BibTeX for Zotero 41](https://retorque.re/zotero-better-bibtex/)
-   [Zutilo: Zotero plugin providing some additional editing features 90](https://github.com/willsALMANJ/Zutilo)
-   [Zotero mdnotes: A Zotero plugin to export item metadata and notes as markdown files 115](https://github.com/argenos/zotero-mdnotes)
