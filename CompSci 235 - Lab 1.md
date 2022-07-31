# Essential Skills for the Industry

#### Agenda

1. Software Versioning
2. IDE
3. Terminal
4. Virtual Environment
5. Markdown
6. Debugging
7. Git & GitHub
8. Hands-On



## 1. Software Versioning

Each of the **digits** found on software versions (e.g. Python **3.10.5**) represent different types of updates performed on the program.

- The **first digit** represents **major releases**/changes that make the program **incompatible with** files that run on the **previous versions**.
- The **second digit** are the different changes made for **minor releases that add additional features** to the program. These changes are still compatible with previous versions with the same major release digit.
- The **third digit** are **bug-fixes**; they will **never break backward compatibility**.



This is important because we want to **create an app that uses late but not latest versions** of the coding language we use/IDE we use. We wouldn’t want to deal with **bugs out of our control** that have not been patched by Python for example.



## 2. IDE

### Pycharm

**<u>Pros</u>**:

- Full-feature IDE for Python
- Familiar UI to Java/Android IDE’s
- Easier to manage Projects & VEnv’s

**<u>Cons</u>**:

- Many features behind a paywall
- Projects need to be made for everything - tedious to run for short-term bug-testing/coding



### VS Community

**<u>Pros</u>**:

- Text-editor that’s quick and easy
- Completely free
- Can edit almost anything

**<u>Cons</u>**:

- Edits ‘everything’; however this requires extensions to install for ‘everything’
- Frequently asks to pick a Python interpreter



## 3. Terminal

Most servers don’t have a **GUI**; meaning a lot of commands have to be run through the terminal (CMD).

![Terminal example photos from slide 12](C:\Users\GGPC\Pictures\My Domain\UoA\CompSci 235\Labs\Snippets\Terminal Examples.PNG)



## 4. Virtual Environment

- These virtual environments are **virtual isolations** of a Python version and its installed packages.
- Having **virtual environments dedicated to each project** is important: If we create an app that runs with **Numpy package 1.23.1**; in a few years we wouldn’t be able to access this project otherwise when **Numpy package 2.10.2** is released. We need a **virtual isolation of the packages we used** to be able to run the old versions of Python, Numpy, etc. that we used years ago.



### Pycharm & Conda

**PyCharm** automatically <u>creates a venv for every project</u>; sweet and simple.

**Conda** is a VEnv that can be both a **package manager and virtual environment** (Otherwise we have Pip as a package manager).



### Package Info

To save the packages we used for our project; we can use

```c
# Save all package dependencies into "requirements.txt"
pip freeze > requirements.txt

# Install from requirements.txt
pip install -r requirements.txt
```

It’s important to save this info for **other users** who want to open our project with the necessary requirements/packages.

**Note**: This does not save the Python version we are using.



## 5. Markdown

Easy-to-use **markup language** (similar to HTML). Used on **GitHub and Jupyter Notebook**; easy to document information and code inline when writing notes with Markdown.



## 6. Debugging

```python
def sum_two_numbers(a, b):
    print("I'm here: sum two method")
    return a+b
```

We can use a **breakpoint** to halt the execution, and then use **step into or step over** to traverse the code and **evaluate expressions**.



## 7. Git/GitHub

**Git** is a **version control system** for collaborative software development: it allows for contributions to be made by multiple people over an online resource on the WWW.

There are many providers that implement Git: **GitHub, BitBucket, and AWS CodeCommit**.

**GitHub** is the most widely used out of those three; using **cloud services to store and manage code**. This **helps keep track of changes** and contributions made on the code by the developer/suggestions from others.



## 8. Hands-On

| Virtual Environments                    | Debugging                            | GitHub                  |
| --------------------------------------- | ------------------------------------ | ----------------------- |
| - Create a HelloWorld project with venv | Download CS235 Lab1 GuessingGame.zip | Create a GitHub account |
| - Install a package                     | Open the project in PyCharm          | Repo for Lab Reports    |
| - Generate requirements.txt file        | Add breakpoints/debug code           |                         |



# Lab Report:

## Reflection

The lab was a nice and short lab; an introductory slideshow on the importance of proper version labels and virtual environments.

### Versioning

Versioning was something I vaguely understood before studying CS; I knew big patches meant non-compatibility with older versions and the other numbers just meant something else. Now that I know the proper meaning behind them: I can definitely manage applications with a better understanding now.

### IDE

I prefer PyCharm over VSCode, I have to learn VS for other classes too so eventually I will default to that. I used to always just use IDLE for developing my code; slowly switching over to PyCharm. PyCharm is slightly more familiar to me due to using IntelliJ, and sometimes my VSCode refuses to run on some other languages which is something I have to fix eventually.

### Conda

Conda is very handy for code maintainability and passing on your programs to someone else; maybe even to myself when I delete my source folder accidentally...

Great to know the utility of CMD otherwise.

### Venv

With package managing and venv, I realise how legacy code has been maintained for all these years. Passing on the code with virtual isolation is a great way to separate old legacy code with new code being written to form a compatible patch with updated packages/languages. (This is great)

### MD

Markdown has been very fun to use; I’ve been using it for a few years now and right now I mainly use Typora to edit and create new MD files on a whim. I frequently still use some references for special symbols I use during note-taking.

I mainly use this online pdf: https://www.caam.rice.edu/~heinken/latex/symbols.pdf

It helps me keep-track of which symbols I need to remember and might use on occasion when using LaTex.

### Debugging

It’ll always be tedious to keep using print and having to stop/run code over and over again just to check on specific errors. With the use of breakpoint, it’ll be easier to isolate blocks of code and check for bugs that way.

### GitHub

A great way to maintain and manage code as well; the collaborative nature of GitHub lets aspiring/studious coders to brush up on their code and find meaningful things to use their experience on. A lot of code to read-over and many techniques to learn from veteran coders over there too. (My Account: https://github.com/AGraidh)



## Hands-On

### Virtual Environments

- I simply ran PyCharm and let it automatically set-up the VEnv, then I chose my Python destination folder.

- Following the PyCharm guide, https://canvas.auckland.ac.nz/media_objects_iframe/m-4HzGAzDz1dgmKTRMiBqwgpJDsaRkwYug?type=video , I install the Numpy package using a Terminal window accessed within PyCharm.

  ```c
  # Installed numpy package
  >pip install numpy
  ```

- Otherwise, if I needed help with pip commands I can just type

  ```c
  # Lists out all the commands available for pip
  >pip help
  ```

- Using a breakpoint, I can easily see the values of the variables and other information I can use to fix any bugs within the demo code; seeing that 0 is within the command `np.arange(value)`, and the value given is not in range. The easy fix is giving two parameters instead of 1, `np.arange(1, value+1)` instead.

- I generated a ‘requirements.txt’ file using the `pip freeze > requirements.txt` command in the terminal section of PyCharm.



### Debugging

#### Main Objective:

1. What is the probability of winning a game?

   We have a $1 \over 100$ chance of winning the game; this 1% chance is seen with the code in hiddenFunctions:

   ```python
   import random
   
   def pickANumber():
       return random.randint(1, 100)
   ```

2. Using the debugging feature, WITHOUT changing any code, is it possible to win every game?

   What line did you insert the breakpoint at?

   Without changing/rigging the code to one answer only; we can actually guess the number in every game. 

   When inserting a breakpoint at line 50; we can see the value of **selected_number** from **computer_pick_number()** before the game ends, 

   this means we can already guess what number it will be using the debug feature.

3. Using the debugging feature only, is it possible the user can win every game by guessing “42”?

   As it’s not possible to change values of variables within the debug feature, we **can’t win every game** by guessing ‘42’. This is because we can only see the randomly selected_number; not change it to our guess: 42.



### GitHub

(My Account: https://github.com/AGraidh)