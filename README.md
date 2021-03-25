# Pre-work - *Memory Game*

**Memory Game** is a Light & Sound Memory game to apply for CodePath's SITE Program. 

Submitted by: **Dzvenyslava Koman**

Time spent: **5** hours spent in total

Link to project: (insert your link here, should start with https://slow-almondine-teeth.glitch.me/dontletyourdreamsbedreams)

## Required Functionality

The following **required** functionality is complete:

* [x] Game interface has a heading (h1 tag), a line of body text (p tag), and four buttons that match the demo app
* [x] "Start" button toggles between "Start" and "Stop" when clicked. 
* [x] Game buttons each light up and play a sound when clicked. 
* [x] Computer plays back sequence of clues including sound and visual cue for each button
* [x] Play progresses to the next turn (the user gets the next step in the pattern) after a correct guess. 
* [x] User wins the game after guessing a complete pattern
* [x] User loses the game after an incorrect guess

The following **optional** features are implemented:

* [x] Any HTML page elements (including game buttons) has been styled differently than in the tutorial
* [x] Buttons use a pitch (frequency) other than the ones in the tutorial
* [x] More than 4 functional game buttons
* [x] Playback speeds up on each turn
* [x] Computer picks a different pattern each time the game is played
* [x] Player only loses after 3 mistakes (instead of on the first mistake)
* [ ] Game button appearance change goes beyond color (e.g. add an image) -- attempted
* [ ] Game button sound is more complex than a single tone (e.g. an audio file, a chord, a sequence of multiple tones)
* [ ] User has a limited amount of time to enter their guess on each turn

The following **additional** features are implemented:

- [ ] List anything else that you can get done to improve the app!

## Video Walkthrough

Here's a walkthrough of implemented user stories:
<img src="http://g.recordit.co/vK7ZYbJpty.gif">


## Reflection Questions
1. If you used any outside resources to help complete your submission (websites, books, people, etc) list them here. 

[https://unsplash.com/t/textures-patterns](https://unsplash.com/t/textures-patterns) — I found pictures for the optional task here.

I also actively used websites such as W3School and GeekForGeeks; I primarily looked at rules connected to the syntax of JavaScript, CSS, and HTML since I was not familiar with it prior to this exercise.

I used stackoverflow to check whether anyone ever had similar problems to the ones that I had. I found it to be highly useful.

2. What was a challenge you encountered in creating this submission (be specific)? How did you overcome it? (recommended 200 - 400 words) 

I had some troubles with implementing a feature whereby playback decreases with each iteration. My initial mistake was that I changed the variable clueHoldTime inside the loop of the playClueSequence() function. This resulted in clueHoldTime decreasing with both each round of the game and each sound/press of the button that was made. Also, unless I reloaded the page, the decreased clueHoldTime did not go back to the initial value of 1000 and started decreasing from the number for length of sound that I finished last time.

I could not initially understand what was causing the problems. However, I used alert and consol.log to print out the value of the clueHoldTime variable each time the loop in playClueSequence() function is run. This made me identify what the problem was and how to solve it. To solve the problem, I placed the clueHoldTime outside of the loop in the playClueSequence() function. This way, each time the playClueSequence() function was called, clueHoldTime decreases by 50. Since the function is called each time the round begins, clueHoldTime decreases with each round.

Also, I initiated the variable clueHoldTime to 1000 in the start() function so that each time the game is restarted the value of clueHoldTime gets back to 1000.

After these changes, I thought I solved the problem. However, now after approximately 3 rounds the sounds started playing concurrently (figured out this using consol.log function). The problem was solved by setting the delay to a constant number.




3. What questions about web development do you have after completing your submission? (recommended 100 - 300 words) 

- I am now really interested in knowing how the process of designing the website works. More specifically, I am wondering how one decides how to best position and design all the different features of the website (buttons, menus, etc.) so that to serve the needs of the client as best as possible and achieve the goals of the website. I understand that lots of research should go into it, and these decisions should not be arbitrary. Also, a potential important step would be to ask users for feedback to revise the design of the website. Yet, I was wondering whether this is the job that the web developer does (or at least contributes to) or whether it falls more into the responsibilities of the project manager or the designers.
- I am wondering how bigger websites such as Facebook work with data, i.e., how they make their websites work efficiently given the huge amount of the data that these websites need to load every second. 
- Also, Glitch seems to simplify development of the websites by allowing one to use HTML, CSS, JavaScript all in one place. I was wondering how developers manage the process of development and maintenance of their larger and more complex websites (for social media companies, for example) as compared to the one I made for this task. I would guess they do not use Glitch, and, based on my research, the process for them is much more complex. 
- Additionally, I was thinking how one develops a progressive web application, i.e., an application that would open on any browser and any device (both computers and smartphones). I think there are some differences between different browsers and smartphone software, and it would be convenient to develop one application for all the browsers at the same time. 


4. If you had a few more hours to work on this project, what would you spend them doing (for example: refactoring certain functions, adding additional features, etc). Be specific. (recommended 100 - 300 words) 
There are several modifications that I would like to implement. Here is a to-do list of improvements (I am planning on working on it during my spring break):
- Make sure that the image does appear when a colored button is pressed. While I started implementing this feature, I did not manage to make it work. The images are in the .jpeg format so they should render without any problems. However, it is not the case; when the image is not hidden, I just see a placeholder for it. I researched the problem and tried several potential solutions but I still did not succeed. For example, I first assumed that the image is too large and thus tried setting the size of the image to a certain default. However, this did not work because the image is by default of the same size as a button.
- Add an option of pausing and then resuming the game. After the user presses "resume," the computer would be programmed to replay the last played sequence. This feature would be especially useful in cases where there is a limit on the time (as in the last optional task).
- I would add more documentation (comments and docstrings) in the code to explain how the game works so that anyone who has not seen the code before could quickly understand how it works and could contribute to making the game better.
- Give a user the option of choosing a melody that they would like to play. This would potentially involve giving a predetermined set of melodies for a user to choose from (a menu). The sound associated with each color would change with each round; this way, if a user is playing the same song several times, then the sequence changes. However, this might make the game much harder for a user because a given color would not be associated with a certain sound, i.e., there will not be a cognitive clue for a user to follow the melody. In some contexts (concentration and memory exercises), though, this feature might be useful.
- In CSS, the code that specifies the color for each button in both states (idle and pushed) seems to be repetitive. If possible, create a more general function that would take a button id as intake and then return color for each state.
- Create a settings menu that the user can hide if needed. This menu would allow the user to adjust the game to his/her needs. The menu would include the following:
- A choice of several color schemes. There would be a default color scheme; however, users would be able to choose one that fits their needs and/or desires. For example, some users might be sensitive to bright colors or be color blind.
- Volume adjustment button that would allow the user to adjust the volume regardless of the volume set on their local machine.
- Make sure that the game shows nicely on screens of different sizes and on different devices.




## License

    Copyright [Dzvenyslava Koman]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
\ ゜o゜)ノ
