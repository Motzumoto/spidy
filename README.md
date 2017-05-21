# spidy
Spidy (spˈɪdi) is a simple to use command line web crawler.
Given a list of web links, spidy uses the Python lxml and requests libraries to query the websites. Spidy then extracts all links from the DOM of the page and adds them to its list.

# startup
User friendly log messages are printed in the console letting you know what proccess is going an if it is taking a long time and you don't know why. 
![Start example](/start.png?raw=true "Start pic")
In the .bat file that runs the web-crawler.py you can specify arguments to control the behavior of the crawler the first argument after specifying the python script is todo file where you can specify a separate file if you want to save multiple to do lists or already have a preset one default is crawler_todo.txt. Second argument is done file where same as to do you can specify a specific file where you want to load a done list from or save to default is crawler_done.txt. Third argument is log file where you can specify a file where you want so write all error messages etc to default is crawler_log.txt. Fourth argument is after how many queried webpages will the crawler autosave todo and done lists(default is 1000 iterations.
![options example](/bat.png?raw=true "options pic")
# how it works
This web crawler is very simple in that the main functionality is it's ability to parse the html for all links and then adds all of those links that are valid into a list called todo. As you would expect the crawler then goes on to do this same process for all links in todo. After every 100 links queried (by default) the crawler will autosave the done file and will prune the links for any invalid ones.
![Run example](/run.png?raw=true "run pic")

# error handling and management
While testing we have come across many common errors that aren't easily avoided such as http timeout, unicode encode errors, exceeding maximum redirects, http connection, and document empty(going to picture etc.) For all of these errors we have separate error handling that prints a relevant sttatement to the console since most of these errors are impossible to avoid we just continue past them. For unknown errors we have a cap which will cause the program to stop if we exceed that set amount.
