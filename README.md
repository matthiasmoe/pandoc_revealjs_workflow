# Pandoc to reveal.js Workflow

The whole purpose of this project is to provide the setup for workflow to make scientific slides. Slides are completely written in [pandoc Markdown](https://pandoc.org/MANUAL.html) and coverted into [reveal.s](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&ved=2ahUKEwiFgPLY26yEAxXyX_EDHQhCBtYQFnoECA8QAQ&url=https%3A%2F%2Frevealjs.com%2F&usg=AOvVaw3ny9QaZS2NlTzl2uoGQM1i&opi=89978449).

I will provide:

- some basic setup instructions
- a reveal.js template `./templates/revealjs.pandoc`
- a configuration file that works for me `./config/presentation_default.yaml`
- some more insights into the different features that are provided in pandoc `./wiki`
- an own simplistic theme that works for the pandoc version established in this version
- some additional tips and hints that can contribute to get the best

This project is nothing huge but shall provide easy access to the functionalities of pandoc limited to revealjs. Let's face it, pandoc has such many amazing features that one can invest much time to just extract the needed ones for revealjs.

I would also appreciate the contribution of others by containing the wiki or adding new themes.


## Setup

### reveal.js

reveal.js is already added as a submodule in this project. It can be initialized by using the command

```bash
git submodule init --recursive
```

Next one has to set revealjs up. Therefore, one should know that it is a [Node.js](https://nodejs.org/en) project (javascript). Those projects use a package manager called `npm`. The package manager is installed along `Node.Js`. Installation recommendation can be found [here](https://nodejs.org/en/learn/getting-started/how-to-install-nodejs).

When npm is installed, a user has to install the node modules. This can be achieved - as typical for Node.Js project - through following commands:

```bash
cd ./reveal.js
npm install .
```

**Additional Recommendation**

I invite people to keep their presentation files separated from the `./reveal.js` folder. A folder can be initialized and linked into reveal.js. Those commands could be helpful

```bash
mkdir external
ln -s ./external ./reveal.js/external
```

Keeping reveal.js and the presentations separated can contribute to an easier update of reveal.js. Of course, this also allows having own presentations in an own git.

### Installation of Pandoc

Pandoc can be installed by using a package manager. However, in my personal experience, it is very important to have the most-recent version (many features are added on a constant bases). Many package managers often use older versions. My personal recommendation is to manually install the newest version. It can be found [here](https://pandoc.org/installing.html).


## The General Workflow

### reveal.js

A user has to start the reveal.js server. Therefore, following command can be used

```
cd ./reveal.js
npm start
```

The terminal will display the startup information and provide an insight of how to access reveal.js. Usually, reveal.js can be accessed by typing `http://localhost:8000` in a webbrowser. This leads to the demo of reveal.js. If you want to access another file, you use `http://localhost:8000/somefilename.html`.

**Tip:** If you followed my recommendation of making an external folder, this can help to navigate through your project. Let's assume, you have the folder `external`. By using `http://localhost:8000/somefilename.html/external` you receive navigation window in your browser that allows you to navigate freely around.

### Pandoc
