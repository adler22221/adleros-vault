---
created: 2023-04-18T20:15
author: human
---



Created on: [[20230418]]
Who's involved: 
About what: 

My note: 

Author: 
Source: 
https://forums.zotero.org/discussion/99170/from-zotero-to-obsidian-a-tag-based-workflow-in-pictures
Retrieved 

> This post has been created in continuation of a couple of templates shared. See this thread for more context.

# From Zotero to Obsidian : a tag based workflow in pictures
This post has been created in continuation of a couple of templates shared. See [this thread](https://forums.zotero.org/discussion/97185/basic-template-for-tagged-highlights-when-creating-a-child-note-from-annotation#latest) for more context.

Workflow description:  
_1\. Use Zotero pdf reader to annotate your readings  
\- highlight, annotate  
\- tag your highlights, tag your post-it aka fleeting notes  
\- make comments  
2\. export to your obsidian vault  
3\. use obsidian as you much as you like to refine your knowledge system_

I used the following templates to do so.  
A. Template for tags and highlights in Zotero:  
edit the advanced preference _extensions.zotero.annotations.noteTemplates.highlight_ as followed:  
`{{if comment}}<p>{{comment}}{{endif}}<blockquote><i>{{highlight}}</i></blockquote>{{citation}}{{if tags}}<br/>#hgh/{{tags : tags join=' #hgh/'}}{{endif}}`  
\- see it at work [from Zotero 6.+ reader interface](https://drive.google.com/file/d/1-V4DvYrpXnCaCYH-UY-rTUGyTSUF4tLV/view?usp=sharing)  
\- see results after export [from Obsidian interface](https://drive.google.com/file/d/1jj2WYz-17_SGwVJp22q7OXZF5lg2cfre/view?usp=sharing)

B. Template for tags and post-it notes in Zotero:  
edit the advanced preference _extensions.zotero.annotations.noteTemplates.note_ as followed:  
`<p><i>Note:{{comment}}</i>{{if tags}}<br/>#note/{{tags : tags join=' #note/'}}{{endif}}<br/>{{citation}}</p>`  
\- at work [from Zotero](https://drive.google.com/file/d/1sL7DvSPEZ34fKI83MmATmRyeYFiS0gHV/view?usp=sharing)  
\- results [from Obsidian](https://drive.google.com/file/d/1G2PmjccLdeJDiTGrHgQMyLvqqTGhfnKx/view?usp=sharing)

Overall results:  
\- from [Zotero](https://drive.google.com/file/d/1xNQNz-XoSzWSRyMMUdQFXkQQ0CjzRTIN/view?usp=sharing)  
\- from Obsidian: [here](https://drive.google.com/file/d/1RZM5trUMTYdC70NVT5mMn9y3tTQv_BfT/view?usp=sharing) and [here too](https://drive.google.com/file/d/12x5CN5PTBD6uQPg6UcK11SJroGhuQlbn/view?usp=sharing)

Hope it works for you and that the links are correct, let me know if not.  
Any feedback is welcome.  
It remains more of sketch than a full usecase but I think it gives an idea of what one could do with the reader-anotater features from 6.0.  
Also, it emphasizes the nested tag feature on Obsidian side.
