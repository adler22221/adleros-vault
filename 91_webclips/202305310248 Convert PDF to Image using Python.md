---
created: 2023-05-31T02:48
author: human
---



My note: 

#excerpts
Author: RokiDGuptaRokiDGupta
        
            37122 gold badges77 silver badges1414 bronze badges
Source: 
https://stackoverflow.com/questions/60701262/convert-pdf-to-image-using-python
Retrieved 

> I am trying to convert a pdf file to image file for this in my ubuntu server i have installed:
python2.7
poppler-utils
pdf2image==1.12.1
My code:

from pdf2image import convert_from_path,

# Convert PDF to Image using Python
I am trying to convert a pdf file to image file for this in my ubuntu server i have installed:

1.  python2.7
2.  poppler-utils
3.  pdf2image==1.12.1

**My code:**

```
from pdf2image import convert_from_path, convert_from_bytes

images = convert_from_path("/home/user/pdf_file.pdf")

# OR

with open("/home/user/pdf_file.pdf") as pdf:
    images = convert_from_bytes(pdf.read())
```

**OUTPUT**

**When I am using the function "convert\_from\_path"**

```
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/usr/local/lib/python2.7/dist-packages/pdf2image/pdf2image.py", line 143, in convert_from_path
    thread_output_file = next(output_file)
TypeError: ThreadSafeGenerator object is not an iterator
```

**When I am using the function "convert\_from\_bytes"**

```
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
  File "/usr/local/lib/python2.7/dist-packages/pdf2image/pdf2image.py", line 268, in convert_from_bytes
    paths_only=paths_only,
  File "/usr/local/lib/python2.7/dist-packages/pdf2image/pdf2image.py", line 143, in convert_from_path
    thread_output_file = next(output_file)
TypeError: ThreadSafeGenerator object is not an iterator
```

I have reinstalled all my utilities then i am facing these problems.
