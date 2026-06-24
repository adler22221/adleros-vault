---
created: 2023-05-31T02:49
author: human
---



My note: 

#excerpts
Author: Vedant Jumle
Source: 
https://stackoverflow.com/questions/67861641/why-is-pdf2image-giving-me-a-blank-image-file
Retrieved 

> I trying to perform OCR using Tesseract OCR on multiple big pdf files (~400-600 pages). I don't necessarily want to extract text from all pages, but I just want a few pages (page numbers are known)...

# Why is pdf2image giving me a blank image file?
**There is nothing wrong with the source OCR,** in fact it is better than most similar examples, true there is a glitch here and there but that's due to the source quality thus to be expected and I suspect a second pass would fare much worse.

Here is the source with OCR text highlighted [![enter image description here](https://i.stack.imgur.com/XBhPz.png)](https://i.stack.imgur.com/XBhPz.png)

Here is the OCR (which is readable as searchable text), represented as an image which you suggest you desire to run a second time but all you can do is get worse, never better unless you type any characters that are missing or malformed.

[![enter image description here](https://i.stack.imgur.com/2swYa.png)](https://i.stack.imgur.com/2swYa.png)

And here it is as TEXT exported to WordPad

```
First Edition, 5,000 Copies, November 1972 

© The Navajivan Trust, 1972 

Principal collaborators: 
Shankar Prasada, ics (retd.) 
Special Secretary, Kashmir Affairs (1958-65) 
Chief Commissioner of Delhi (1948-54) 

B. L. Sharma 
Former Principal Information Officer, Government of India, 
Former Special Officer on Kashmir Affairs in the External Affairs 
Ministry, New Delhi, and author 

Inder Jit 
Director-Editor, India News and Feature Alliance and 
Editor, The States, New Delhi 

Trevor Drieberg 
Political Commentator and Feature Writer 
Former News Editor, The Indian Express, New Delhi 

Uggar Sain 
Former News Editor and Assistant Editor, 
The Hindustan Times, New Delhi 

Printed and Published by Shantilal Harjivan Shah 
Navajivan Press, Ahmedabad-14 
```

[![enter image description here](https://i.stack.imgur.com/JvVy1.png)](https://i.stack.imgur.com/JvVy1.png)
