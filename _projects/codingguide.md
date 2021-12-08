---
layout: page
title: Arie's Coding Guide
published: true
---

# Arie's Coding Manifesto (aka Coding Best Practices)

Hi! I'm Arie, one of your TAs for CMPS-3140 Introduction to Artificial Intelligence.  I'm a second year PhD student and have also been a professional software engineer for the past 5 years.  This course is heavily project based - you're going to read and write a lot of code.  For many of you, the projects will involve working in the largest codebase you've seen.  It may also be the first time you've implemented non-trivial algorithms with interactive components.

If you're unfamiliar, the guidelines below will help you work more effectively both individually and in teams.  They'll make it easier for Dr. Mattei and the TAs to offer help.  And they'll result in higher grades from professionalism scores and making life easier for your graders ;-).

For those of you interested in a career in software engineering, while not exhaustive by any means, the skills/habits/concepts listed below are absolutely critical for success.  For those of you interested in getting a good grade in this course, you will gain/lose points for how well you are able to apply them.  For those of you interested in neither, maybe they will help you think about the question "What is the person I'm submitting my work to going to do with it?", which is important to think about in many areas of life.

Beyond helping with homeworks and projects I'm always happy to nerd out on coding best practices, python, and software engineering so feel free (and encouraged!) to schedule time with me to talk.

--Arie

## Interactive Development Environment (IDE)

If you've never used an [IDE](https://en.wikipedia.org/wiki/Integrated_development_environment) before, now is the time to start.  An IDE will make you faster and more efficient at writing code, simplify debugging, and help keep you organized.  There are tons of IDEs out there and which to use often comes down to personal preference.  If you don't have a preference, you would like help from the TA, and/or you're interested in trying out a new IDE you should use [VS Code](https://code.visualstudio.com/) for this course with the [Python extension](https://github.com/Microsoft/vscode-python).

## Separation of Concerns

Understanding and **using** the concept of [Separation of Concerns](https://en.wikipedia.org/wiki/Separation_of_concerns) when writing code is critical when working with others, debugging, and writing extensible code.  There are tons of competing opinions and arguments about nuances for those interested to check out on Google.  But at it's heart:

> "The overall goal of separation of concerns is to establish a well-organized system where each part fulfills a meaningful and intuitive role while maximizing its ability to adapt to change ([source](https://www.castsoftware.com/blog/how-to-implement-design-pattern-separation-of-concerns))."

Do This:
```Python
def get_data():
  ...
def process_data(data):
  ...
data = get_data()
result = process_data(data)
```
Not This:
```Python
def get_result():
  ... work to get data
  ... work to process data
result = get_result()
```

## Rule of Three

The [Rule of Three](https://en.wikipedia.org/wiki/Rule_of_three_(computer_programming)) is a more practical take on the ["Don't Repeat Yourself" (DRY)](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) principle.  Trying to rigorously adhere to the DRY paradigm leads to over-engineering and inefficient use of time when you try to write code for a pattern that isn't totally clear to you yet.  On the other hand, the rule of three allows you to see different manifestations of a given pattern and hopefully leads to a better generic method if/when refactoring is needed.

* Do This:
```Python
numbers_list = [ value for value in range(4) ]
```
* Not This:
```Python
numbers_list = []
numbers_list.append(0)
numbers_list.append(1)
numbers_list.append(2)
numbers_list.append(3)
```

## Readable Code

When you submit code for consumption by another person you should think of your submission just as you would a paper for an English class or a professional email - it should be edited, organized, and coherent.  You wouldn't submit standard English writing with cross outs, text from brainstorming, or paragraphs out of order.  Don't do that with your code either.

This is the easiest area for novice coders to improve.  It's also the area that is the source of the most frustration as a grader (in this course) or a collaborator (in the real world).  These items don't involve understanding or thinking about difficult concepts.  Rather, the hurdle is simply awareness.  Now that you see them here, failure to incorporate these practices in your code can only be due to laziness and professionalism points will be docked heavily.

### Variable Names

Variable names should be human readable, sensible, and full words (within reason).  We have IDEs now (right?) that all come with IntelliSense to autocomplete words.  Given that, you don't save time typing by calling a variable ```val``` vs. ```value``` or  ```amvn``` vs. ```a_meaningful_variable_name```.  Further, I've found when people name variables without meaningful names it often signals a lack of understanding of what your code is doing and what the object actually is.  Thinking about a proper name can be a great first step if you're stuck or confused.

### Unused/Commented Code 

If you have code that has no function **delete it**.  Don't comment it out and don't just leave it there.  Take it out.  It can be very frustrating if you've spent hours writing some code to then find out you were going down the wrong path and that code you spent so much time on is useless.  That's the name of the game, it's going to happen, and it's OK.  

You may think in the back of your mind "I should keep it just in case I need it later" or "I'm just going to leave this here because I know my answer is wrong and I want the grader to see I put in effort to maybe get more points".  In the first case, if you want to save some unused code that is totally fine.  But still, delete it from your final submission and save it in another file!  In the second case, the opposite is true.  If you want me to see that you put in effort come to office hours.  Or write an email explaining what you did and why it didn't work.  Don't leave junk in the code.

**NOTE**: Adding ```print``` statements or other debugging code is a great way to tackle programming problems.  If you are not doing that you're either a genius and should work at NASA or you're doing it wrong.  BUT, once you've figured everything out, delete them! 

Do This:
```Python
def get_answer():
  return 42
meaning_of_life = get_answer()
print(meaning_of_life)
```
Not This:
```Python
def wrong_answer():
  print("I'm in the 'wrong_answer' function")
  return 41

# def get_answer():
  # return 41

def get_answer():
  # return 41
  return 42

meaning_of_life = wrong_answer()
meaning_of_life = get_answer()
print(meaning_of_life)
```

## Things to Generally Avoid
This section presents some code examples that make me say "yuck" when I see them.  They're either inefficient, inelegant, difficult to debug, or all three.  Of course there are always exceptions, but you should be able to get through most of your life without ever doing any of the below.

1. Looping through an entire list by index

  * Do This:
  ```Python
    for value in list_of_values:
      do_something(value)
  ```
  * Not This:
  ```Python
    for i in range(len(list_of_values)):
      value = list_of_values[i]
      do_something(value)
  ```

2. While Loops
* Do This:
```Python
  for value in list_of_values:
    do_something(value)
```
* Not This:
```Python
    i = 0
    while i < len(list_of_values):
      do_something(list_of_values[i])
      i += 1
```
3. Nesting/Too Many Loops
* Do This:
```Python
for value in list_of_values:
  intermediate_value = get_intermediate_value(value)
  result = do_something(intermediate_value)
```
* Not This:
```Python
intermediate_values = []
for value in list_of_values:
  intermediate_values.append(get_intermediate_value(value)
for intermediate_value in intermediate_values:
  result = do_something(intermediate_value)
```
4. Mutating Objects
* Do This:
```Python
for value in list_of_values:
  intermediate_value = get_intermediate_value(value)
  result = do_something(intermediate_value)
```
* Not This:
```Python
for value in list_of_values:
  value = get_intermediate_value(value)
  value = do_something(value)
```
