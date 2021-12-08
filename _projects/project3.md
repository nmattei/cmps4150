---
layout: page
title: Project 3: Multi-Agent Search
published: true
---

## Project 3: Multi-Agent Search

Note that there seems to be some issues with TKinter and newer versions of Python (above 3.7) on the newest version of MacOS.  If your computer randomly logs you out when you try to run PacMan then [please try the tips here](https://www.python.org/download/mac/tcltk/#built-in-8-6-8), or simply downgrade Tkinter using the command: `conda install tk=8.6.7`

**Note:** There is an issue with the autograder and Python versions newer than 3.8! It's a small issue and in order to fix it you can either (1) downgrade your Python or (2) put the following two lines into the autograder file right under the end of the import block.
```Python
import cgi
import html
cgi.escape = html.escape
```

### Working in Groups

For this project you are allowed to work in teams of size 2.  If you complete the project in a team both members must turn in exactly the same assignment through Canvas.  In your writeup you must clearly label whom you worked with and **how you worked together**.  Examples include: we setup a private Github repo to coordinate code and we met on Zoom X times.... or even we used [LiveShare for VS Code](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare) or [Teletype for Atom](https://teletype.atom.io/) or [RemoteCollab for Sublime](https://packagecontrol.io/packages/RemoteCollab).  Failure to turn in a collaboration plan that shows you coordinated will be a loss of professionalism points.  The turned in result will need to reflect the understanding of both students as we are still going to ask questions about this Project on the final and you both must be able to answer questions during code review.

**Project partners should turn in exactly the same files in Canvas.**

### The Assignment

Navigate over to the Berkeley Site for the PacMan Projects in the quick links below.  **Note:** There are a number of versions of these projects.  Please make sure you are following the links from the course website!

We'll be doing the third project: **Multi-Agent Search**.  Complete the five questions in the assignment and ensure that your solution passes the autograder.

This project is designed to test both your Python3 knowledge, you ability to work with code written by others, and most importantly, your understanding of search in multiagent environments!

When writing your code you should make use of the `util.py` when making data structures.  In general it is good to look at the files `pacman.py`, `game.py`, and `util.py` to make sure you have an understanding of the way the game is represented.

| File | What to Look For |
|:-------:|--------|
| `ghostAgents.py` | Agents to control ghosts. |
| `pacman.py` | The main file that runs Pacman games. This file describes a Pacman GameState type, which you use in this project. |
| `game.py` | The logic behind how the Pacman world works. This file describes several supporting types like AgentState, Agent, Direction, and Grid. |
| `util.py` | Useful data structures for implementing search algorithms. You don't need to use these for this project, but may find other functions defined here to be useful.

In addition to these files you are going to be modifying the following files.

| File | What to Look For |
|:-------:|:--------:|
| `multiAgents.py` | Where all of your multi-agent search agents will reside.|

I really cannot stress the following enough...

#### Note: Read the directions closely on the Berkeley page... there are lots of hints.

### Quick Links

| Resource | Link |
|:-------:|:--------:|
| Project 3: Files | [Link Here](https://inst.eecs.berkeley.edu/~cs188/fa20/assets/files/multiagent.zip) |
| Project 3: Multi-Agent Search | [Link Here](https://inst.eecs.berkeley.edu/~cs188/fa20/project2/) |
| 2020 Berkeley Pacman Projects | [Link Here](https://inst.eecs.berkeley.edu/~cs188/fa20/projects/) |

### What To Turn In!

Turn in through [Canvas](https://tulane.instructure.com/). You should submit a Zip file that contains a sub-folder with **all of the files from the project Multiagent**! At the top level you should also include a a text file that captures the **entire output** of the autograder.  Name the output capture `Lastname.Autograder.txt`. You should also include answers to the *written portion* questions below in your zip file.  This should be named `Lastname.WrittenAnswers.pdf`.

Example Folder Structure for Prof. Mattei:
```
- Mattei.Project3
|- Mattei.WrittenAnswers.pdf
|- Mattei.Autograder.txt
|- Multiagent
   |- pacman.py
   |- search.py
   |- multiAgents.py
   |- ...
------
```

You should rename the top level folder (before zipping it) to `Lastname.Project3` so that it is `LastName.Project3.zip`. You are not to modify any other files than the ones listed here, if you do we will not be able to run your code and you will lose points.

### Grading Rubric

Note that for all of these projects simply passing the autograder is not sufficient to ensure full credit.  We will include comments to why points were taken away -- if you are still confused Arie and Dr. Mattei are available to talk to you and provide explanations.  

We expect all code to be written in a professional manner. That means there are comments where there needs to be, that the code is written in a general way that is (reasonably) efficient, and that you use naming conventions that others can understand.  If we open your code and we can't understand it, you will lose points even if it works.

**Reminder:** Please list any and all sources you use to complete this program, failure to do this is technically plagiarism and will be treated as such. You do not need to list the book or any references directly from the course page.  Remember that it is very easy to Google for these answers and it is against your academic code of conduct to do so. We will be doing code review, asking questions on the test to make sure you understand your work, and checking your code against other students and our database of code from the internet.  Please refer to the [Syllabus](syllabus) for more details.

* (10 Points) *Professionalism*: You have written code that is interpretable -- it contains comments where needed to understand, variable names are reasonable, and code that is reasonable and efficient.  You have followed directions to turn in the file, clearly labeling everything.  You have cited all sources and how you used them in the written portion of your answers.
* (10 Points) *Question 1: Reflex Agent.* You have written code for a reflex agent that is general and passes the required tests.  Note that we will run your agent on the `openClassic` layout some number of times.  If your agent times out or never wins, you will get 0 points.  If your agent wins all the games, your score will be better.
* (10 Points) *Question 2: Minimax.* You have written code for a minimax agent that is general and passes the required tests.
* (15 Points) *Question 3: Alpha-Beta Pruning.* You have written code for an agent that uses Alpha-Beta pruning that is general and passes the required tests.  Note that your agent will still lose sometimes here.
* (15 Points) *Question 4: Expectimax.* You have written code for a minimax that is general and passes the required tests.
* (20 Points) *Question 5: Evaluation Function.* You have written code for an evaluation function agent that is general and passes the required tests.  This function will be scored based on its quality and speed.
* (20 Points) *Written Portion.* Several of the questions ask you to investigate the behavior of the algorithms in various settings.  Include a file with **~1 paragraph** answers to the following questions. Even if you are not able to complete the code, you may be able to discuss some of these questions and the response you should expect.
	* Question 1: Give the intuition behind your reflex agent.  Why did it work?  What did you try that didn't work?
	* Question 2: What happens as you increase the search depth for your minimax agent?  Why do you think this is?
	* Question 3: Compare the stright minimax agent to an Alpha-Beta pruning agent.  How much better or worse is it?  Why?
	* Question 4: Give some intuition as to why (or why not) your expectimax agent is working better than the other agents.
	* Question 5: Give the intuition behind your evaluation function.  Why did it work?  What did you try that did not work?

* Total Score: 100

### Code Review

After the project is turned in, Prof. Mattei will randomly select and reach out to 3 groups. You are expected to come to office hours with either Prof. Mattei or a TA and Prof. Mattei.  During this meeting we will be opening your code and you will answer several questions related to how you implemented your solution, why you made the decisions you made, and what various parts of the code are doing.