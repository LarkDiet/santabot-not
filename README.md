# santabot-not
A near-faithful recreation of the classic 2004 holiday chatbot.
Rescripted using rivescript-js.

## What?
SantaBot was a browser-based chatbot where the user could "chat" with Santa through an HTML form input. Upon submission, the input would be sent to the server to be parsed by the bot logic, and the page would reload with the user's last input and Santa's reponse above the form field. The website hosting the chatbot has since gone defunct, much to the dismay of children everywhere (and my friend Quint). Snapshots of the front-facing portion of the site are available on the Wayback Machine, but they are non-functional without the server-side code.

## Why?
To help save Christmas, I decided to take matters into my own hands and revive SantaBot for one more season of joy. I felt it would also be a fun project for me to refresh my knowledge on HTML and Javascript. Fortunately, making the bot functional again was the easy part, largely thanks to the Rivescript library. This is still very much a work in progress while I continue cleaning up the code and expanding the bot's library of responses.

## How?
Before I could even get started in implementing scripts, there was a bit of cleanup on the HTML that had to be done — both for overhauling the previous implementation and just because it looked a little dated. According to the website, SantaBot premiered on the web in 2004 (though its earliest proper snapshot is from Christmas 2005), and the source code remained hardly unchanged through the years, except for the addition of the "History of Christmas" essay, links to witty jokes and quotes from Santa (whether these were actual responses the bot would return if you asked the associated questions is currrently unknown), and space for banner ads.

To improve the readibility of the code, I linked a new CSS document to replace several in-line style attributes in the HTML. I also assigned consicely-named id attributes to each component of the chatbox for use in the Javascript section. The entire body of the page is (annoyingly) structured with tables, which I hope to replace with a CSS-centric layout soon.

Originally, every time the user submitted a query, the entire page would have to reload to display the bot's response. By mid-2000's internet standards, this likely would have led to a lot of waiting time between bot responses, perhaps by design to imitate the pacing of a real messenger session. With the new Rivescript implementation, this would not be necessary. Rather than using the form POST method to send queries, the submit button instead calls a function that creates a "message" variable from the inputted value of the form field. The Rivescript reply() uses this variable to fetch an appropriate reply based on the .rive files in the brain. The messsage and reply variables are then written to the chatbox HTML.
