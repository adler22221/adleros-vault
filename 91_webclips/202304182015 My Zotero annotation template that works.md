---
created: 2023-04-18T20:15
author: human
---

#_GTD_0_inbox

Created on: [[20230418]]
Who's involved: 
About what: 

My note: 

Author: 
Source: 
https://forum.obsidian.md/t/my-zotero-annotation-template-that-works/51662/9
Retrieved 

> Hi  As I’ve been struggling for few days to make it right, I’d like to share my implementation of Zotero annotations template that I built and I believe looks very nice.  Features:   Simple layout Focuses on the content Large headers based on annotation color (Default is red annotation = h5) Includes highlights, boxes, comments  Requirements:   Obsidian (obviously) Zotero with Better Bibtex installed “Zotero Integration” plugin for Obsidian  Steps:   Copy my template into a new document of yours ...

# My Zotero annotation template that works
Hi

As I’ve been struggling for few days to make it right, I’d like to share my implementation of Zotero annotations template that I built and I believe looks very nice.

Features:

-   Simple layout
-   Focuses on the content
-   Large headers based on annotation color (Default is red annotation = h5)
-   Includes highlights, boxes, comments

Requirements:

-   Obsidian (obviously)
-   Zotero with Better Bibtex installed
-   “Zotero Integration” plugin for Obsidian

Steps:

-   Copy my template into a new document of yours
-   Direct the integration plugin into that template
-   Activate the CSS snippet that I’m attaching
-   Pull the annotation from Zotero using the integration plugin

Template:

```
---
year: {{date | format ("YYYY")}}
tags: research
authors: {{authors}}

Abstract:  {{abstractNote}}
---

### {{title}}
{{pdfZoteroLink}}

### Notes
{% for annotation in annotations -%}{%- if annotation.annotatedText -%}{% if 'Red' in annotation.colorCategory %} 
##### {{annotation.annotatedText | escape }}{% else %}
<mark class="customZot-{% if annotation.color %}{{annotation.colorCategory}} {% endif %}">{{annotation.annotatedText | escape }}</mark> ([{{annotation.page}}](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.page}}&annotation={{annotation.id}}))

{% endif %}{%- endif %} {% if annotation.imageRelativePath %} ![[{{annotation.imageRelativePath}}]]{% endif %}{% if annotation.comment %} 
>{{annotation.comment}}
{% endif %}{% endfor -%}
```

CSS Snippet (ZoteroHighlights.css)

```
.customZot-Yellow {
    background-color: rgba(255, 204, 0, 0.212) !important;
}

.customZot-Green {
    background-color: rgba(0, 255, 47, 0.215) !important;
}

.customZot-Blue {
    background-color: rgba(0, 0, 255, 0.187) !important;
}

.customZot-Purple {
    background-color: purple !important;
}
```

Below are some screenshots (I’m using “Things” theme)

[![Screenshot 2023-01-07 024034](https://forum.obsidian.md/uploads/default/optimized/3X/9/a/9a0fd84036743d60bd09d6acb1bb280a70bc4eee_2_522x500.png)](https://forum.obsidian.md/uploads/default/original/3X/9/a/9a0fd84036743d60bd09d6acb1bb280a70bc4eee.png "Screenshot 2023-01-07 024034")

[![Screenshot 2023-01-07 024329](https://forum.obsidian.md/uploads/default/optimized/3X/6/0/60b18ec56f165de4b805c41cd022bbe56a5689f2_2_522x500.png)](https://forum.obsidian.md/uploads/default/original/3X/6/0/60b18ec56f165de4b805c41cd022bbe56a5689f2.png "Screenshot 2023-01-07 024329")

[![Screenshot 2023-01-07 024416](https://forum.obsidian.md/uploads/default/optimized/3X/f/7/f72ad296c09c528a03ebcaa64a91661b0cc9c475_2_522x500.png)](https://forum.obsidian.md/uploads/default/original/3X/f/7/f72ad296c09c528a03ebcaa64a91661b0cc9c475.png "Screenshot 2023-01-07 024416")

-   #### created
    
    Jan 7
    
-   [
    
    #### last reply
    
    ](https://forum.obsidian.md/t/my-zotero-annotation-template-that-works/51662/14)
    
    [](https://forum.obsidian.md/t/my-zotero-annotation-template-that-works/51662/14)3d
    
-   2.3k
    
    #### views
    
-   7
    
    #### users
    
-   19
    
    #### likes
    
-   4
    
    #### links
    
-   [![](https://forum.obsidian.md/letter_avatar_proxy/v4/letter/r/f14d63/64.png "Ben")](https://forum.obsidian.md/u/readherring "readherring")
    

Just wanted to say thank you so much for posting this. I have finally been able to get my Zotero notes imported into Obsidian after spending hours fiddling around with it.

This is such a big help!

Thanks so much for this template - took some time for me to find my way through it but I did it ![:slight_smile:](https://forum.obsidian.md/images/emoji/apple/slight_smile.png?v=12 ":slight_smile:")

here’s my rendition - with the help of you and others ([Source1 52](https://publish.obsidian.md/history-notes/01+Notetaking+for+Historians)), used with BibTex and Zotero integration. I’m not the best with this templating stuff, so many apologies if its messy!

```
---
status:
year: {{date | format ("YYYY")}}
authors: {{authors}}
type: {{itemType}}
last-reviewed:
---
## {{title}} 
> [!info] 
> - **Abstract:** {{abstractNote}} 
> - **Sources**: [online]({{uri}}) [local]({{desktopURI}}) {%- for attachment in attachments | filterby("path", "endswith",".pdf") %} [pdf](file:///{{attachment.path | replace(" ","%20")}}) {% if loop.last %}{% endif %}{%- endfor %}
> - **Bibliography**: {{bibliography}}
> - **Cite Key:** [[@{{citekey}}]] 
 {%- if hashTags %}
> - **Tags:** {{hashTags}} 
{%- endif %}

>[!Personal Summary] 

## Annotations 
{% for annotation in annotations -%}{%- if annotation.annotatedText -%}{% if 'Purple' in annotation.colorCategory %} 
##### {{annotation.annotatedText | escape }}{% else %} 
<mark class="customZot-{% if annotation.color %}{{annotation.colorCategory}} {% endif %}">{{annotation.annotatedText | escape }}</mark> ([{{annotation.page}}](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.page}}&annotation={{annotation.id}}))
{% endif %}{%- endif %} {% if annotation.imageRelativePath %} ![[{{annotation.imageRelativePath}}]] {% endif %}{% if annotation.comment %}
>*{{annotation.comment}}* 
{% endif %}{% endfor -%}

```

That’s very good to hear! Happy that I was able to help ![:slight_smile:](https://forum.obsidian.md/images/emoji/apple/slight_smile.png?v=12 ":slight_smile:")

… and expanded:  

[![grafik](https://forum.obsidian.md/uploads/default/optimized/3X/3/a/3a757b9b610020862c619f78ed79db41716b44f9_2_277x500.png)](https://forum.obsidian.md/uploads/default/original/3X/3/a/3a757b9b610020862c619f78ed79db41716b44f9.png "grafik")

Hi nocona!

First, very nice template! I have a question tho…  
I’m fiddling a little with your callout headers. I’d like them to have the same name on each calloutHeader as the header they sort under. Now they are hard coded into:

{%- set calloutHeaders = {  
“highlight”: “Relevant / Important”,  
“strike”: “Disagree”,  
“underline”: “Todo / Read later”,  
“image”: "Image  
}  
\-%}

I’ve tried _a lot_ but my nunjuck-fu is too poor. Could you please help me to point out where to edit? In the setting above or in the object call further down?

This is the best thing I have found for my Obsidian and finally got my Zotero workflow working. However, could you possibly help me change a few things in it? I have no understanding of coding.

Hi ize, I just saw your post. I am not sure I understand your request. Could you please elaborate a little more what you would like to achieve?  
Thanks

Hi everyone !

Thanks to this thread and to [elena razlogova’s notetaking process 6](https://publish.obsidian.md/history-notes/01+Notetaking+for+Historians) I’ve writed my own script for when I read research article and to import my annotations into Obsidian. I also wanted to make it look good.

It put each highlights/notes/image into a callout of its own which color correspond to the annotation’s color in Zotero with underneath your comment if there is one. Then you can link it to your main writing notes.

Hope that it can help someone !

**Template :**

```
---
{% if title %}Title: "{{title}}"{% endif %}
Authors: {{authors}}{{directors}}
{% if publicationTitle %}Publication: "{{publicationTitle}}"{% endif %}
{% if date %}Date: {{date | format("YYYY-MM-DD")}}{% endif %}
citekey: {{citekey}}
tags: {{hashTags}}
---
## {{title}}
**Bibliographie :** {{bibliography}}

**Lien de la publication :** {{url}}

**Lien Zotero :** {{pdfZoteroLink}}

**Tags :** {{hashTags}} 

>[!abstract]+
>*« {{abstractNote}} »*

{% for annotation in annotations -%}
>[!Annotation|{{annotation.color}}]+ 
>{%- if annotation.annotatedText -%}*« {{annotation.annotatedText}} »*([{{annotation.page}}](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.page}}&annotation={{annotation.id}})){% endif %}{% if annotation.imageRelativePath %}![[{{annotation.imageRelativePath}}]]{% endif %}{% if annotation.comment %} 
>
>{{annotation.comment}}{%- endif %}

{% endfor %}
```

**CSS snippet :**

```
/* Red */
.callout[data-callout-metadata="#ff6666"] {
    --callout-color: 205, 52, 92;
}

/* Green */
.callout[data-callout-metadata="#5fb236"] {
    --callout-color: 114, 162, 100;
}

/* Blue */
.callout[data-callout-metadata="#2ea8e5"] {
    --callout-color: 52, 82, 255;
}

/* Purple */
.callout[data-callout-metadata="#a28ae5"] {
    --callout-color: 157, 131, 242;
}

/* Orange */
.callout[data-callout-metadata="#f19837"] {
    --callout-color: 244, 164, 96;
}

/* Yellow */
.callout[data-callout-metadata="#ffd400"] {
    --callout-color: 255, 236, 0;
}

/* Magenta */
.callout[data-callout-metadata="#e56eee"] {
    --callout-color: 255, 33, 255;
}

/* Gray */
.callout[data-callout-metadata="#aaaaaa"] {
    --callout-color: 152, 152, 152;
}

.callout-icon {
    display: none;
}
```

**Example of how it looks :**  

[![image](https://forum.obsidian.md/uploads/default/optimized/3X/d/2/d27db5a7f7507dca17d3761c7dd6d29e5789dd8c_2_393x500.png)](https://forum.obsidian.md/uploads/default/original/3X/d/2/d27db5a7f7507dca17d3761c7dd6d29e5789dd8c.png "image")
