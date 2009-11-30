### What is it?

It's basically the same as the Firefox extension [Morning
Coffee](https://addons.mozilla.org/en-US/firefox/addon/2677) which opens
certain predefined URLs depending on the current weekday or something. I'm
using [Vimperator](http://www.vimperator.org/) and don't have a toolbar in
Firefox, so I can't use Morning Coffee.  


### How does it work?

It's a very simple Perl script that reads ~/.morningtea which contains pairs
of URLs and some kind of date pattern that defines when to open them. Then it
calls Firefox like this:  
`firefox -new-tab 'URL1' -new-tab 'URL2' -new-tab 'URL3' ...`  


### Examples for ~/.morningtea

`1-5/w: http://www.example.org/news`  
Open link on days 1 to 5 of each week, i.e. Mondays to Fridays.  
NOTE: Weekday numbers start with 1 (Monday) and end with 7 (Sunday).  

`1,10,20/m: http://www.example.org/lazy-news`  
Open link on the 1st, 10th and 20th of each month.  

Open link every 10 days.  
`10/y: http://www.example.org/stuff`  

That's pretty much it. Syntax is quite forgiving; you can put
newlines/tabs/spaces wherever you want, except inside the URL and in the date
pattern. Spaces in URLs can be replaced by + or %20. Everything that doesn't
fit into this pattern is ignored.  


### Bugs and Features

Please drop me a message if you encounter bugs or if you would like to have
another way to define when to open URLs. You can find my email address
[here](http://github.com/fagga).

