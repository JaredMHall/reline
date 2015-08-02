# reline - formatting text line widths

## Introduction & User Guide

### Using a text file as input
Reline is a little command line tool with the specific job of reformatting text width.  

So let's say you have a textfile, let's called it **my_file.txt** and its line width is around 18 words per line.  
You could do something like this...  
`reline my_file.txt 8`  
which would in turn decrease the line width to a predictable 8 words per line.  
  
The same thing can be done with characters. Say that you wanted not more than 50 characters per line without splitting any words.  
`reline myfile.txt -c 50`  
I haven't perfected this yet so it's possible that this might exceed the line width that you specify.  
If you would like to make sure and see exactly how long each line is, that can be done like this:  
`reline myfile.txt -c -i 50`  
Adding the `-i` flag will include the character/word count of each line (depending on whether the `-c` flag has been passed) and also a total line count.  
  
Lastly the words can be split to maintain exact line lengths by adding the `-sw` flag rather than the `-c` flag.  
`reline myfile.txt -sw 30`  
This will split every line at exactly 30 characters, splitting any word on to the next line.  
  
### Using a pipe as input  
Same as the above except no text file is specified (I am yet to think of any good examples for this one).  
`<some program's> | reline 5`  

## Installation  
`cd /usr/local/bin`  
`ln -s <path_to_reline/reline>`  

## Testing
So far I've tested this on OSX mavericks and Linux Mint 17.2 'Rafaela'  
although it should fucntion on any *nix system that has python 2.7  
  
## Warning  
The current version separates words by spaces, which may lead to some unexpected results.  
Also, currently, it treats any punctuation or number that has spaces on either side as a word as well.  



