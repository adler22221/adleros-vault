---
created: 2023-03-12T03:44
author: human
---

#_GTD_0_inbox

Created on: [[20230312]]
Who's involved: 
About what: 

My note: 

Author: 
Source: 
https://matbury.com/wordpress/index.php/2015/07/13/adding-bibliography-metadata-to-your-web-pages/
Retrieved 

> Open Access publishing is gaining popularity and, at the same time, increasing numbers of academics are uploading their papers on their personal websites, faculty pages, and blogs. This is great news for people who don’t have the luxury of an institution to pay for their access to the usually pay-walled research databases. Along with this positive development, I think providing bibliographical metadata in academic websites and blogs should become more of a priority. It is necessary for bibliography managers such as Mendeley and Zotero to quickly, easily, and accurately store, retrieve, and reference academic papers, which can save other academics, science writers, journalists, and students hours of work for each paper or article they write. If academic websites and blogs provide the metadata to support bibliography managers, it means that it’s that much easier for people to cite their research and provide links back to their websites, faculty pages, or blogs. However, unlike research databases, most websites, faculty pages, and blogs don’t usually provide this bibliographical metadata.

# Adding bibliography metadata to your web pages – Matt Bury
**[![320px-Books](https://matbury.com/wordpress/wp-content/uploads/2015/07/320px-Books.jpg)Open Access](https://en.wikipedia.org/wiki/Open_access)** **publishing is gaining popularity and, at the same time, increasing numbers of academics are uploading their papers on their personal websites, faculty pages, and blogs. This is great news for people who don’t have the luxury of an institution to pay for their access to the usually pay-walled research databases. Along with this positive development, I think providing bibliographical metadata in academic websites and blogs should become more of a priority. It is necessary for bibliography managers such as [Mendeley](https://www.mendeley.com/) and [Zotero](https://www.zotero.org/) to quickly, easily, and accurately store, retrieve, and reference academic papers, which can save other academics, science writers, journalists, and students hours of work for each paper or article they write. If academic websites and blogs provide the metadata to support bibliography managers, it means that it’s that much easier for people to cite their research and provide links back to their websites, faculty pages, or blogs. However, unlike research databases, most websites, faculty pages, and blogs don’t usually provide this bibliographical metadata.**

### What is bibliographic metadata?

Metadata is intended for machines, rather than people to read. Bibliographic metadata tells bibliography managers and search engines by whom, when, where, what, and how an article or paper was published and makes it easier for people to find through title, author, subject, and keyword searches.

### Can we embed it in a blog?

I use [WordPress](https://wordpress.org/) (this blog is built on my own customised version of WordPress) and it’s the most widely used and popular blogging software on the internet. While there’s a large and diverse range of plugins and extensions available, a search shows that while there are [several that provide metadata](https://wordpress.org/plugins/search.php?q=metadata) for [search engine optimisation](https://en.wikipedia.org/wiki/Search_engine_optimization) (SEO), few offer support for bibliography managers, and none of the ones I’ve found support the minimum required metadata for academic citations. In order to find out how difficult or easy embedding metadata is, I tried an experiment on this blog to automatically generate as much relevant metadata from standard WordPress format blog posts as possible.

### What does academic bibliography metadata look like?

Here’s an example metadata set for a published academic paper in an academic journal database (Applied Linguistics, Oxford Journals):

```
<!-- start of citation metadata -->
<meta content="/applij/4/1/23.atom" name="HW.identifier" />
<meta name="DC.Format" content="text/html" />
<meta name="DC.Language" content="en" />
<meta content="Analysis-by-Rhetoric: Reading the Text or the Reader's Own Projections? A Reply to Edelsky et al.1" name="DC.Title" />
<meta content="10.1093/applin/4.1.23" name="DC.Identifier" />
<meta content="1983-03-20" name="DC.Date" />
<meta content="Oxford University Press" name="DC.Publisher" />
<meta content="JIM CUMMINS" name="DC.Contributor" />
<meta content="MERRILL SWAIN" name="DC.Contributor" />
<meta content="Applied Linguistics" name="citation_journal_title" />
<meta content="Applied Linguistics" name="citation_journal_abbrev" />
<meta content="0142-6001" name="citation_issn" />
<meta content="1477-450X" name="citation_issn" />
<meta name="citation_author" content="JIM CUMMINS" />
<meta name="citation_author" content="MERRILL SWAIN" />
<meta content="Analysis-by-Rhetoric: Reading the Text or the Reader's Own Projections? A Reply to Edelsky et al.1" name="citation_title" />
<meta content="03/20/1983" name="citation_date" />
<meta content="4" name="citation_volume" />
<meta content="1" name="citation_issue" />
<meta content="23" name="citation_firstpage" />
<meta content="41" name="citation_lastpage" />
<meta content="4/1/23" name="citation_id" />
<meta content="4/1/23" name="citation_id_from_sass_path" />
<meta content="applij;4/1/23" name="citation_mjid" />
<meta content="10.1093/applin/4.1.23" name="citation_doi" />
<meta content="http://0-applij.oxfordjournals.org.aupac.lib.athabascau.ca/content/4/1/23.full.pdf" name="citation_pdf_url" />
<meta content="http://0-applij.oxfordjournals.org.aupac.lib.athabascau.ca/content/4/1/23" name="citation_public_url" />
<meta name="citation_section" content="Article" />
<!-- end of citation metadata -->
```

An APA Style (6th Edition) formatted citation from this metadata would look like this:

Cummins, J., & Swain, M. (1983). Analysis-by-Rhetoric: Reading the Text or the Reader’s Own Projections? A Reply to Edelsky et al.1. _Applied Linguistics_, _4_(1), 23–41. http://doi.org/10.1093/applin/4.1.23

### How can I add bibliographic metadata to my website or blog?

If you use WordPress, you’re in luck. I’ve made some modifications to my WordPress theme so that the appropriate bibliographic metadata is automatically added to the head section of each blog article.

#### Pre-requisites

-   A good FTP client. [Filezilla](https://filezilla-project.org/) is a good free and open source one.  [Netbeans](https://netbeans.org/) and [Dreamweaver](http://www.adobe.com/ca/products/dreamweaver.html) have FTP clients built in. If you’ve never used an FTP client before, look up some beginner tutorials to learn the basics of editing remote server files.
-   FTP access and login credentials to the web server where your blog is hosted.
-   A good text editor, e.g. [Notepad++](https://notepad-plus-plus.org/), [Notepadqq](http://notepadqq.altervista.org/wp/), [Gedit](https://wiki.gnome.org/Apps/Gedit), [GNU Emacs](http://www.gnu.org/software/emacs/), etc., or an HTML integrated development environment, e.g. [Netbeans](https://netbeans.org/), [Brackets](http://brackets.io/), or [Dreamweaver](http://www.adobe.com/ca/products/dreamweaver.html).

The metadata format for blogs is a little different from academic metadata, i.e. it uses the [Dublin Core](https://en.wikipedia.org/wiki/Dublin_Core) standard, but thee principles are similar. Here’s what I did:

-   I chose an existing WordPress core theme, _[twentytwelve](https://wordpress.org/themes/twentytwelve/)_, (but this should work with any theme) and created a child-theme: I created a new directory in _/wordpress/wp-content/themes/twentytwelve-child/_ WordPress automatically replaces files in themes with any files provided in child theme directories.
-   I made a copy of the _header.php_ file from /_twentytwelve/_ and pasted it at _/wordpress/wp-content/themes/twentytwelve-child/header.php_
-   In a text editor, I opened the new _header.php_ file and added the following lines of code between the PHP tags at the top of the page. This retrieves the metatdata from WordPress’ database:

```
// Set post author display name
$post_tmp = get_post($post_id);
$user_id = $post_tmp->post_author;
$first_name = get_the_author_meta('display_name',$user_id);
// Set more metadata values
$twentytwelve_data->blogname = get_bloginfo('name'); // The title of the blog
$twentytwelve_data->language = get_bloginfo('language'); // The language the blog is in
$twentytwelve_data->author = $first_name; //'Matt Bury'; // The article author's name
$twentytwelve_data->date = get_the_date(); // The article publish date
$twentytwelve_data->title = get_the_title(); // The title of the article
$twentytwelve_data->permalink = get_the_permalink(); // The permalink to the article
$twentytwelve_data->description = substr(strip_tags($post_tmp->post_content),0,1000) . '...'; // Take 1st 1000 characters of article as description
```

-   After that, in the same _header.php_ file, between the <head> </head> tags, I added the following lines of HTML and PHP code. This prints the metadata on the article page. Please note that metadata is not visible when you read the web page because it’s for machines, not people to read. You can view it in the page source code (_Ctrl + u_ in Firefox and Google Chrome):

```
<!-- start of citation metadata -->
<meta name="DC.Contributor" content="" />
<meta name="DC.Copyright" content="© <?php echo $twentytwelve_data->author; ?> <?php echo $twentytwelve_data->date; ?>" />
<meta name="DC.Coverage" content="World">
<meta name="DC.Creator" content="<?php echo $twentytwelve_data->author; ?>" />
<meta name="DC.Date" content="<?php echo $twentytwelve_data->date; ?>" />
<meta name="DC.Description" content="<?php echo $twentytwelve_data->description; ?>">
<meta name="DC.Format" content="text/html" />
<meta name="DC.Identifier" content="<?php echo $twentytwelve_data->title; ?>">
<meta name="DC.Language" content="<?php echo $twentytwelve_data->language; ?>" />
<meta name="DC.Publisher" content="<?php echo $twentytwelve_data->blogname; ?>" />
<meta name="DC.Rights" content="http://creativecommons.org/licenses/by-nc-sa/4.0/">
<meta name="DC.Source" content="<?php echo $twentytwelve_data->blogname; ?>">
<meta name="DC.Subject" content="<?php echo $twentytwelve_data->title; ?>">
<meta name="DC.Title" content="<?php echo $twentytwelve_data->title; ?>">
<meta name="DC.Type" content="Text">

<meta name="dcterms.contributor" content="" />
<meta name="dcterms.copyright" content="© <?php echo $twentytwelve_data->author; ?> <?php echo $twentytwelve_data->date; ?>" />
<meta name="dcterms.coverage" content="World" />
<meta name="dcterms.creator" content="<?php echo $twentytwelve_data->author; ?>" />
<meta name="dcterms.date" content="<?php echo $twentytwelve_data->date; ?>" />
<meta name="dcterms.description" content="<?php echo $twentytwelve_data->description; ?>">
<meta name="dcterms.format" content="text/html" />
<meta name="dcterms.identifier" content="<?php echo $twentytwelve_data->title; ?>">
<meta name="dcterms.language" content="<?php echo $twentytwelve_data->language; ?>" />
<meta name="dcterms.publisher" content="<?php echo $twentytwelve_data->blogname; ?>" />
<meta name="dcterms.rights" content="http://creativecommons.org/licenses/by-nc-sa/4.0/">
<meta name="dcterms.source" content="<?php echo $twentytwelve_data->permalink; ?>" />
<meta name="dcterms.subject" content="<?php echo $twentytwelve_data->title; ?>" />
<meta name="dcterms.title" content="<?php echo $twentytwelve_data->title; ?>" />
<meta name="dcterms.type" content="Text" />
<!-- end of citation metadata -->
```

Please note that I put the Dublin Core metadata twice in two slightly different formats for maximum compatibility with search engines and bibliography managers.

### What about comprehensive academic bibliography metadata?

You’ll probably have noticed that the metadata I’ve included in my article pages, while sufficient for web page citations, doesn’t contain the same degree of detail as academic bibliography data (see first metadata snippet above), e.g. journal titles, ISSN’s, ISBN’s, etc.. As far as I know, there isn’t yet a way of storing that data in standard WordPress and so it more than likely needs a specialist plugin so authors can explicitly enter it to be stored and printed on the corresponding article pages. Would anyone like to develop one?
