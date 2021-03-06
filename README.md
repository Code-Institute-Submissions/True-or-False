
# True or False 

![Multi device Screenshot](https://github.com/AlexPullen91/True-or-False/blob/master/wireframes/true-or-false-mockup.jpg?raw=true)


True or False is a simple quiz app presenting the user with a question. Is it true or false?

---

# Contents
1. [UX / Project Goals](#ux)
2. [User Goals](#user-Goals)
3. [User Stories](#user-stories)
4. [Design Choices](#design-choices)
5. [Wireframes](#wireframes)
6. [Features & Potential Future features](#features)
7. [Technologies used](#languages)
8. [Testing](#testing)
9. [Issues and resolutions](#issues-and-resolutions)
10. [Deployment](#deployment)
11. [Credits](#credits)
---

## UX


### Project Goals

Provide a simple but engaging user experience for someone interested in playing a general knowledge trivia game.

#### User goals

* Something quick, simple and engaging.
* Easily navigated user interface.
* Fun and challenging.
* Interesting variety of questions.
* Ability to save and check high scores.

#### User stories

* *"As a trivia game fan I expect to be appropriately challenged by the questions"*
* *"As a user I expect to be able to navigate straight into a game from the landing page"*
* *"As a competitive player I expect to be able to log my scores and compare them with those of others"*
* *"As a user I expect real time feedback to my input when I interact with the site"*
* *"As a user I expect to be able to play multiple times with a refreshed set of questions each time"*
* *"As a user I expect to have the option to play again immediately when I finish"*

---

## Design Choices
* User interface situated centrally in the screen leaving lots of space outside of it to be used by background effect.
* [Particle](https://marcbruederlin.github.io/particles.js/) effect in the background to create interesting visual for the user reminiscent of DNA structures and sci-fi style interfaces.
* Less is more approach to avoid cluttering the UI with unnecessary features and icons.
* Indigo dye #1a4e6e and Honolulu blue #2c6e96 combine to make a [gradient background](https://cssgradient.io/)
* White #FFFFFF for the particle effect and font color.
* Green #00af14 and Red #e20000 for the right and wrong answer modal button.
* [Roboto Mono](https://fonts.google.com/specimen/Roboto+Mono?sort=popularity&preview.text=Question+number+1+2+3+4+5+6&preview.text_type=custom&sidebar.open&selection.family=Roboto+Mono:wght@300) for font family.

---

### Wireframes


I used [Balsamiq](https://balsamiq.com/) to create wireframes for **mobile, tablet and desktop.**

I opted to leave out social links from the final product in favour of a less cluttered UI.

You can find my wireframes [here](https://github.com/AlexPullen91/True-or-False/tree/master/wireframes).

---

### Features

* Main menu with play button and high scores button that navigates to their respective pages.
* Game section featuring [API generated questions](https://opentdb.com/) presenting user with clickable option between true or false.
* Modal pop ups also inform the user if they got it right or wrong which the user can dismiss by clicking next or just outside of the modal.
* Mousing over buttons gives hover effect signalling interactivity to users.
* Scores can be saved to local storage with their user name which then feature on seperate high scores page.

#### Potential Future features

* Particle effect *responds to user input* to increase feeling of interactivity.
* The effect briefly swells and speeds up when the correct answer is given. It slows down and disperses slightly when the wrong answer is given.
* Choice of specific topics.
* Countdown timer to give sense of urgency.
* Audio and audio feedback to user input.
* More permanent way to save and compare scores across devices and globally.

---
## Technologies Used

### Languages

* [HTML](https://en.wikipedia.org/wiki/HTML)
* [CSS](https://en.wikipedia.org/wiki/Cascading_Style_Sheets)
* [Javascript](https://www.javascript.com/) 

---

### Libraries

* [Google Fonts](https://fonts.google.com/)
* [sweetalert2](https://sweetalert2.github.io/)
* [Particles](https://marcbruederlin.github.io/particles.js/)

---

### Tools

* [Github](https://github.com/)
* [Gitpod](https://www.gitpod.io/)
* [Git](https://git-scm.com/)
* [Google Chrome developer tools](https://developers.google.com/web/tools/chrome-devtools)
* [Open Trivia Database API](https://opentdb.com/)
* [CSS Gradient](https://cssgradient.io/)
* [Balsamiq](https://balsamiq.com/)
* [Coolers](https://coolors.co/)

---

## Testing

Testing for responsiveness and bugs throughout development was carried out with google chrome developer tools and the device toolbar to ensure compatibility on all screen sizes.

* True or False has been tested on an iPhone X, Macbook Pro and Windows 10 iOTA and is working as intended on the following browsers:
    * Google Chrome
    * Microsoft edge
    * Safari
    * Mozilla Firefox

* All HTML ran through [W3C validator](https://validator.w3.org/) without any issues.
* CSS ran through [W3C validation service](https://jigsaw.w3.org/css-validator/validator.html.en) without any issues.

## Manual Testing

*Test case:* **Save button disabling**

This test determines whether or not the save button is disabled by default and with/without user interaction.

    1. Moused over save button to see cancel sign instead of pointer cursor or hover animation.
    2. Clicked save button multiple times and nothing happens.
    3. Moused over to input field, entered "Test".
    4. Moused back to save button and pointer has replaced cancel sign.
    5. Clicked save and text changed to "Saved!" and button can no longer be clicked.

    Verdict: Working as intended

*Test Case:* **Submitting a high score**

This test determines if the user can successfully submit and record a high score.

    1. Moused over username field to see cursor change and signal typing is available.
    2. Clicked input field and typed in "name".
    3. Moused over save button to see cursor has changed to pointer instead of cancel sign and then clicked, seeing text changed to "Saved!".
    4. Moused over to high scores button and clicked. Page changes to highscores.html and "name" is correctly displayed along with score.

    Verdict: Working as intended

*Test Case:* **High Scores sort and cap at 10 / statement loading and answer validation**

This test determines if the high scores sort and display a maximum of 10 scores highest to lowest and if statements load and are answered correctly.

    1. Played through the game 10 times logging with a unique name and different score each time.
    2. A variety of different statements (same ones sometimes repeated) load from the API and correct/wrong answers are accurately detected each time.
    3. On 11th playthrough I ensured score was high enough to place and submitted with unique name.
    4. Lowest score drops out in place of the latest addition and confirms functionality.

    Verdict: Working as intended


### Issues and Resolutions

* During development I had trouble assigning the value stored in ```incorrect_answers``` to my ```wrongAnswer``` variable.
    * By utilising ```debugger``` in chrome dev tools I could step through the code methodically and examine with greater clarity what exactly was happening.
    * It became apparent that ```incorrect_answers``` was storing the value within an array unlike ```correct_answer``` and therefore I was simply missing a zero index from my code ```[0]```.
    * It would seem that this is all because the API provides a multiple choice option for questions and there would normally be 2 other wrong answers stored in this array.

* During development I encountered a problem when writing the conditional statement to determine if the correct answer was being selected. 
    * I began investigating this issue with ```console.log(correctAnswer === true)``` which was reliabily returning false even when I knew the answer was true.
    * Upon closer inspection I realised I was actually comparing a string value ```"True"``` stored in ```correctAnswer``` rather than the boolean ```true``` 
    * Using the strict equality operator ```===``` against ```"True"``` solved this problem.

* During development I noticed some statements weren't loading in properly.
    * For example, ```"&quot;Windows NT&quot; is a monolithic kernel."```
    * [This](https://stackoverflow.com/questions/24602154/explain-what-quot-means) post I found explains that it's [unicode](http://www.fileformat.info/info/unicode/char/0022/index.htm) for quotation marks. I changed out ```innerText``` for ```innerHTML``` which solved the problem.

### Known Issues

* Some of the statements loaded in from the API feature extremely long words which disrupts the layout on smaller screens. I've attempted ```word-wrap: break-word``` to remedy this but have been unsuccessful so far. Needs further investigation.

* On mobile devices the particles effect can occasionally get squashed up to the top of the screen and won't fill the entire background. Needs further investigation. 

* The particle effect is very taxing on the site's performance and due to time constraints I've unfortunately had to scale back initial ambitions to enchance the interactivity based around this effect. See below an example of one of the triggered functions in the button event listeners that would swell and speed up the effect on correct answers. 

```
const particlesCorrect = () => {
  Particles.init({
    speed: 0.7,
    sizeVariations: 5,
    minDistance: 150,
  });
  setTimeout(() => {
    particlesReset();
  }, 3000);
};
```

a similar function ```particlesWrong()``` was used to slow down and disperse the particles on wrong answers and then ```particlesReset()``` returned the effect to it's default state. 

After only a couple questions performance tanked and particularly so for mobile devices therefore I opted to remove these functions and leave the particles running in the background. As I had planned to feature the particle effect more prominently this is something that I'd like to revisit in the future.


---

## Deployment

True or False was developed on GitPod, using git and GitHub to host the repository.

__When deploying True or False using GitHub Pages be sure to follow these steps:__

1. Navigate to **'/AlexPullen91/True-or-False'** or alternatively click [here](https://github.com/AlexPullen91/True-or-False).
2. In the top navigation click on 'settings'.
3. Scroll down to the GitHub Pages area.
4. Select 'Master Branch' from the 'Source' dropdown menu.
5. Click to confirm my selection.
6. True or False should now be live on GitHub Pages.

__In order to run True or False locally be sure to follow these steps whilst still on Github:__

1. Navigate to **'/AlexPullen91/True-or-False'** or alternatively click [here](https://github.com/AlexPullen91/True-or-False)..
2. Click the green 'Clone or Download' button.
3. Copy the url in the dropdown box.
4. Using your IDE of choice open up your preferred terminal.
5. Navigate to your desired file location.
6. Copy the following code and input it into your terminal to clone True or False.

```git clone https://github.com/AlexPullen91/True-or-False.git```

---

---

## Credits


### Content

* Questions retrieved from [Open Trivia Database API](https://opentdb.com/)

### Code

* [James Q Quick's brilliant youtube channel](https://www.youtube.com/channel/UC-T8W79DN6PBnzomelvqJYw) was instrumental in learning how to write the JavaScript for this site.
* [sweetalert2](https://sweetalert2.github.io/) for modals.

### Acknowledgements

* My mentor [Simen Daehlin](https://github.com/Eventyret), always very generous with his time, support and encouragement.

### Disclaimer

*This site is intended for educational purposes only.*

