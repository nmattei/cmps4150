---
layout: page
title: Project 0
published: true
---

## Project 0: Getting Setup!

**Note: This project is to be completed on your own. Later projects will come with partners but this project is solo!**

As always, please follow the [Coding Guide](codingguide.md) when writing code for this course.

**Note:** There is an issue with the autograder and Python versions newer than 3.8! It's a small issue and in order to fix it you can either (1) downgrade your Python or (2) put the following two lines into the autograder file right under the end of the import block.
```Python
import cgi
import html
cgi.escape = html.escape
```

### Setting up the Environment.

Possibly the easiest way to get going with the code is to setup Anaconda on your system.  If you have trouble with this please use [Getting Started with Anaconda Guide](https://conda.io/projects/conda/en/latest/user-guide/getting-started.html).

If you need to install Linux and you have Windows 10 an easy way is to use the Linux Subsystem -- [use this guide.](https://www.dataquest.io/blog/tutorial-install-linux-on-windows-wsl/).  Note that this may have issues with the GUI but it should work.

If you were in the Data Science class last year and are comfortable with Docker you can download the standard Ubuntu image from [DockerHub (Link)](https://hub.docker.com/_/ubuntu) and follow the [same directions as for the data science class (replacing the image in the directions discussed)](https://github.com/TulaneIntroDataScience/fall2019/tree/master/project0).

Note that there seems to be some issues with TKinter and newer versions of Python (above 3.7) on the newest version of MacOS.  If your computer randomly logs you out when you try to run PacMan then [please try the tips here](https://www.python.org/download/mac/tcltk/#built-in-8-6-8), or simply downgrade Tkinter using the command: `conda install tk=8.6.7`


### The Assignment

Navigate over to the [Berkeley Site for the PacMan Projects](https://inst.eecs.berkeley.edu/~cs188/fa20/projects/).  **Note:** There are a number of versions of these projects.  Please make sure you are following the links from the course website!  You should be working on the Fall 2020 Versions!

We'll be doing the first project: [Intro to Python and Unix/Linux and Autograder](https://inst.eecs.berkeley.edu/~cs188/fa20/projects/).  Complete the three questions in the assignment and ensure that your solution passes the autograder.

This project is designed to test your Python3 knowledge and make sure you can run the autograder and submit your assignments.  As such, this is worth less points but is an important step in getting your computer ready to do the other projects in this course.

### What To Turn In!

Turn in through [Canvas](https://tulane.instructure.com/). You should submit a Zip file that contains all of the files for the project as well as a text file that captures the **entire output** of the autograder.  Name the output capture Lastname.Autograder.txt.

You should rename the folder (before zipping it) to `Lastname.Project0`.Please make sure to zip and submit **the entire directory**.  If you do not do this, we cannot run your code and you will lose points.

### Grading Rubric

Note that for all of these projects simply passing the autograder is not sufficient to ensure full credit.  We will include comments to why points were taken away -- if you are still confused Arie and Dr. Mattei are available to talk to you and provide explanations.  

We expect all code to be written in a professional manner. That means there are comments where there needs to be, that the code is written in a general way that is (reasonably) efficient, and that you use naming conventions that others can understand.  If we open your code and we can't understand it, you will lose points even if it works.

* (10 Points) *Professionalism*: You have written code that is interpretable -- it contains comments where needed to understand, variable names are reasonable, and code that is reasonable and efficient.  You have followed directions to turn in the file, clearly labeling everything. Please refer to the [Coding Guide](codingguide.md) for additional instructions.
* (10 Points) *Question 1:* You have written code for the addition function that is general and passes the required tests.
* (10 Points) *Question 2:* You have written code for the buy lots of fruit function that is efficient, general, and passes required tests.
* (10 Points) *Question 3:* You have written code for the shop smart function that is reasonable, general, and passes the required tests.
* (10 Points) *Office Hours:* You have visited one of the course TAs or Prof. Mattei in office hours and they have checked you off.

* Total Score: 50 Points

| Full    |    Good |  Okay |   Lacking   |   Poor  | No Marks |
| : ---- :| : ---- :| : ---- :| : ---- :| : ---- :| : ---- : |
| You completely and fully met the criteria described. | You have met most of the criteria but lack sufficient depth and/or missed one or more minor pieces. | You have missed components of the required criteria and/or they are incorrect / inappropriate or lack depth. | You have missed major components of the required criteria and/or may of them are incorrect. | Little to no evidence of work and major missing components. | Missing or completely inadequate. | 