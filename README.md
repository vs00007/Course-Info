# $\color{Cerulean}{\text{EE1101: Course Wiki}}$
Hi there! 
Welcome to IITH. This course marks the beginning of a unique experience at IITH. For better or for worse, this course is the only one of this kind. 




> [!CAUTION]
>This course will be very intensive. (Contrary to other courses) If you want a good grade, you must put in much more time and effort.
>Be inquisitive. Ask questions. Doesn't matter if they are bad. Also, answer in class. Doesn't matter if the answer is terribly wrong. You'll understand the reason later.

## $\color{Cerulean}{\text{Course Content}}$
Honestly? We don't know what sir plans on covering in the course. To be even more honest, sir barely knows what he'll cover during the course. Here's a general idea of what you can expec to do throughout the semester:
* Basic Circuital understanding
* KCL and KVL
* 2 Port Network Analysis
* Operational Amplifiers
* RLC Circuits (Sinusoidal Steady State analysis)
  * Laplace Transform 
  * Fourier Transform

Besides the actual contents of the course, you will also learn 
* Python as a tool for visualisation (making "cool" graphs and stuff)
* C 
* $\LaTeX{}$ :Forget messy handwriting,
this is how real engineers write their reports (and it looks fancy too).

## $\color{Cerulean}{\text{Classes}}$

Your first class will be at the institute assigned time, and venue will be shared by sir before the class. The rest of the classes will be on a weekday (Wednesday mostly) from 5:30 PM to 8:30 PM. 

The classes will consist of "quizzes" which are essentially sir giving you question on the board, and you having to solve them using whatever online tools, and discussion with others. Everyday, sir will give a question, you have to answer it in a given time (5-15 min) and submit, at which point, sir will ask for volunteers to solve the question on the board. If no one volunteers, he will choose. (Even if you don't know the answer, dw).

You also might have code assignments in the class. Sir will ask you to do something related to a previous question, and you need to write code (or prompt an AI to write code). The submissions will be handled by the discord channel send-codes 
You also might have code assignments in the class. Sir will ask you to do something related to a previous question, and you will need to write code (or prompt an AI to write code). The submissions will be handled by the discord channels `#send-codes` or `#send-output`, and the TAs will evaluate the submissions until the time limit.


## $\color{Cerulean}{\text{Course Work}}$
The work you are expected to do will mainly consist of the following
* "Online Assignments" : These are the questions given to you in the `#question-assign` channel of Discord. Further instructions [here](#colorceruleantextworking-on-online-assignments)
* "Hardware Assignments" : These are circuits that you are supposed to build in the lab. More information [here](#colorceruleantextworking-on-hardware-assignments)



## $\color{Cerulean}{\text{Working on Online Assignments}}$

### $\color{cyan}{\text{Getting the Question}}$
Send the message `/getquestion` in the channel `#question-assign`. The Course Bot will get back to you in approximately 30 seconds. If it is your first time messaging the bot, the response should be something like this 

![getquestion For New Users](Figures/Working%20getquestion.png)
Your DMs should now contain the details of the question you have been assigned.

> Note
> * When you call the command, you have 1 assigned question.
> * You can only have one active question at a time. Unless sir specifies the question is on hold, or until the solution is accepted, you cannot request another question. 

You can request a question any number of times, assuming completion before each request.

### $\color{cyan}{\text{Decrypting the question }}$
The question you are assigned will be of the form

 `(Source) - (year/chapter_number/question_number)`

For example, `NCERT - 11/5/26` indicates question 26, from the 5th chapter in the year 11 from NCERT Physics Textbook.
Another format may be 

`(EXAM NAME / YEAR / SHIFT / QNO)` for GATE / JEE questions

### $\color{cyan}{\text{Solving the question}}$
It took us a while to understand the guidelines for writing the solution to the first question (Almost a month). To make it slightly easier for you, we have created a few awesome guides (Took us a long time 🙂) for some things you may struggle with in the beginning. Here is the *[Latex Guide]()* *. And here is the *[Python Guide]()*.  

Your approach to the question determines how things will go. Try to apply any and all concepts you have discovered in class, to the question. If you do not get an approach, do ask sir. You will have to redo the assignments multiple times, with small changes each time, until sir is satisfied with your pdf. 

Students during GVV sir's course be like
![You can expect to be like this during the course](Figures/revise-meme.png)

*<sub> These guides will be removed after a month-and-a-half. </sub>

### $\color{cyan}{\text{Storing solutions on GitHub }}$

If you don't know what 'git' is, here is a brief description. 

'GIT' - Global Information Tracker is a "version control system."
Git is like having a magic notebook for your code. This notebook keeps track of every edit you make, allowing you to rewind if needed and see how your code transformed. It also lets you work with others on the same code without conflicts, so it's like having a tool that keeps your code safe and organized!

GitHub is like a cloud version of GIT, and allows you to store and share your code with others on it.

How is it useful to us? 

Well, you see, Sir keeps track of the questions that the students solve, by creating a book containing all the accepted solutions. It is easier with GitHub

If you completed course setup, you already have a GitHub account, and a Repository for this course. Since your questions will be of multiple types, it will benefit you if you create a folder for each type.
* NCERT
* GATE
* ~~JEE~~ 

You can then label your assignments in whatsoever way you wish. 
Your assignment folder must contain the following 
* A Folder named 'tables' to store the table you have in your document
* A Folder named 'figs' if you have any figures in your document
* A Folder named 'codes' to store C / Python codes.

Ideally, here's how your repo should look.
![Repo_ss](Figures/Repo%20ss.png)

Other than the Folders, The only file you are responsible for maintaining is main.tex  (A_1.tex in this case). The rest are a by product of compiling the TeX file.

### $\color{cyan}{\text{Submitting the solutions}}$
When you are done with your work, you need to send the link of your repo ('Copy Permalink' in the 3 dots) or (Ctrl/Cmd + Shift + ,) to sir in the channel labelled `your_name - your_roll_number`. Sir will have one of 2 responses
* Make some change and revise
* Commit to repo

The first response is be self explanatory. The second one invokes the following procedure.

### $\color{cyan}{\text{Commiting your solution to repo}}$
When sir tells you to commit a solution to repo, you need to 
1. Fork the repository for the submission
2. Ensure the following lines in your code.
  ```latex
    \iffalse
    . %Preamble here
    .
    .
    \fi
    \author{ "Roll number / Name"} 
    \chapter{"Name of chapter"}
    \question %Before the beginning of the question
    \solution %Before the solution after the question
  ```

3. Make sure you have at least a figure and a table in your solution.
4. To autogenerate the necessary files, run 
  ```bash
    python3 latexgen.py
  ```
5. Then run 
  ```bash
    pdflatex main.tex 
    pdflatex main.tex
  ```
6. This will generate the pdf of the book. 
7. Open a pull request for sir's repo, with the commit message
    > "Q.no in Book - Q.no wrt source, Name, Roll number"

$$\color{yellow}{\text{This is the process for completing online assignments.}}$$


## $\color{Cerulean}{\text{Working on Hardware Assignments}}$
* The components and the circuit schematic will be provided (mostly). There is a chance that sir may ask you to design your own circuit. 
* There will be a viva-voce after the circuit building is done.
* You must maintain a handwritten Lab Report.

You will be evaluated on the demo of the circuit, the understanding you show during the viva, and your lab report.

> The lab work may be in pairs or in groups of 3 / 4. The lab reports must be written individually, the students will be questioned individually.
 
> [!TIP] 
> Experiment a lot with the circuit given. Try to improve it. Try to make changes and see what happens. Measure every possible voltage or current you can. Document the process.
