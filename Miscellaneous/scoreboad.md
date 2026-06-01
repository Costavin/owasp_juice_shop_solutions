# Score Board   -   &#9733;

It can be checked if in the html there is some sign of the score board. From the command line, it can be check the output of the following command.

`$ curl -s http://localhost:3000/ | grep score --color`

Since it is empty, there is no reference to the word "score". However, if we remove the grep, we can notice at the end of the page, that there are linked a series of javascript sources. We can search there. In main.js we ntoice there is a match.

`$ curl -s http://localhost:3000/main.js | grep -E "score|board" --color`

We can search through the terminal, or look through the source tab of the DevTools interface.Finally, we can fin the path `/score-board`, which can be accessed on the browser:

`$ http://localhost:3000/#/score-board`
