Download the latest version from [here](http://github.com/fagga/morningtea/raw/master/morningtea).

### What is it?

It's basically the same as the Firefox extension [Morning
Coffee](https://addons.mozilla.org/en-US/firefox/addon/2677) which opens
certain predefined URLs depending on the current weekday or something. I'm
using [Vimperator](http://www.vimperator.org/) and don't have a toolbar in
Firefox, so I can't use Morning Coffee. Additionally, morningtea should work
with any browser, not just Firefox.


### How does it work?

It's a very simple Perl script that reads ~/.morningtea (or any file you
specify as an argument) which contains the commands to call your browser and
pairs of URLs and some kind of date pattern that defines when to open them.  


### Browser commands

The first line in ~/.morningtea is called a single time when you start
morningtea, meant to start the browser if it is not running. I use iceweasel,
so mine looks like this:

`[ -h .mozilla/firefox/hite019y.default/lock ] || (iceweasel & sleep 10)`  
If lock file exists, browser is already running; else run iceweasel in
background, wait 10 seconds to give it time to come up, then return.

The second line is the command that opens each URL. Again, mine:  
`iceweasel -new-tab '%url'`  
Every occurence of "%url" is replaced with the actual URL that is to be
opened. Note that there is no escaping done for you; you have to do this in
the URL if necessary.  


### URLs and date patterns

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

