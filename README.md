# polyglot

After reading the polyglot section from POC|GTFO, 
you learn that certain file extensions has certain bytes 
that pertain to the header of that file. I.E a pdf will have these numbers (in Hex)
25 50 44 46 2d 31 2e 33 that represent %PDF-1.3. 
<br>

### So what is a polyglot file anyways? ###
If you look up on wikipedia, the definition says its text that represents multiple languages, 
such that a file will have C code, python, and php. In a sence, polyglot is ubiqutous, since multi lingual individuals are 
polyglot. But in our context, polyglot means multi file extensions. Different file extensions can be nested in one file, and this
is what we are doing here.
<br>
### How I made a polyglot ###
So I am using this [polyglot generator](https://github.com/perfaram/pdf-zip-nes-polyglot). It nests four files together. 
The original, the message file, an image, and a nes extension. This outputs a file which I called test_polyglot. Now if you look at the image, 
It is a large file, it is a bit more than the all the files combined. There is a couple things you can do since these files are 
nested. You can do a hexdump on the 
test_polyglot file and see the message being outputed. You can also unzip the test_polyglot and you will get the image from
the pdf. Like magic!
### What I learned ###

So from what I learned is, that you can combine files inside another file and it will be out of plain site. If you can hide
files, you can hide something malicious. For example, in the text file we added, we could add javascript script tags. And when
the browser renders the image, it will also render the script tag. Which can be sneakly dangerous. 
