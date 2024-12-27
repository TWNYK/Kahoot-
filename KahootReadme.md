To match the README.md file with the provided code, we need to create a clear and structured description of the script, explaining its functionality, usage, and features. Below is the README.md content aligned with the given code:

```markdown
# KaHack!

KaHack! is a userscript for enhancing Kahoot quiz experiences by automating answers and customizing interface elements. This script is designed for users who want to have more control over their quiz participation by automatically answering questions or viewing correct answers in real-time.

## Features

- **Auto Answer**: Automatically answers questions based on the points per question you set.
- **Show Answers**: Highlights correct and incorrect answers during the quiz.
- **Customizable Points Per Question**: Adjust the points for each question with a slider.
- **Floating UI Panel**: A user-friendly UI with draggable elements to control the script's features.
- **Input Lag Adjustment**: Adjust the input lag to ensure optimal timing for auto-answering.

## Version

- **Version**: 1.0.25

## Installation

### Requirements

- A browser with support for [Userscripts](https://www.tampermonkey.net/) (e.g., Chrome, Firefox, etc.)
- Tampermonkey or Greasemonkey extension installed.

### Steps

1. **Install Tampermonkey/Greasemonkey**:
   - [Tampermonkey for Chrome](https://tampermonkey.net/)
   - [Greasemonkey for Firefox](https://www.greasespot.net/)

2. **Add the Script**:
   - Open your browser and click on the Tampermonkey or Greasemonkey extension icon.
   - Click "Create a new script" and paste the code provided below.
   - Save and refresh your Kahoot page to see the script in action.

3. **Usage**:
   - Once the script is installed, visit a Kahoot quiz page.
   - A floating panel will appear where you can:
     - **Enter Quiz ID**: Input a valid Kahoot quiz ID to load the questions.
     - **Adjust Points per Question**: Use the slider to set points per question.
     - **Enable Auto Answer**: Toggle auto-answer functionality to automatically answer questions.
     - **Show Answers**: Toggle whether to highlight correct and incorrect answers during the quiz.
     - **Adjust Input Lag**: Fine-tune input lag for accurate auto-answer timing.

### Code

Paste the following code into your console or use a userscript manager like Tampermonkey:

```javascript
// ==UserScript==
// @name         KaHack!
// @version      1.0.25
// @namespace    https://github.com/TWNYK
// ==/UserScript==
var Version = '1.0.25'

var questions = [];
var info = {
    numQuestions: 0,
    questionNum: -1,
    lastAnsweredQuestion: -1,
    defaultIL:true,
    ILSetQuestion:-1,
};
var PPT = 950;
var Answered_PPT = 950;
var autoAnswer = false;
var showAnswers = false;
var inputLag = 100;

function FindByAttributeValue(attribute, value, element_type) {
  element_type = element_type || "*";
  var All = document.getElementsByTagName(element_type);
  for (var i = 0; i < All.length; i++) {
    if (All[i].getAttribute(attribute) == value) { return All[i]; }
  }
}

const uiElement = document.createElement('div');
// UI setup and event listeners omitted for brevity...

// Main logic for answering questions, highlighting answers, and handling input lag...
```

## How It Works

1. **Loading Quiz Data**: The script fetches quiz data using the provided quiz ID. If the quiz is valid, it loads the questions and stores them.
2. **Auto Answer Functionality**: When enabled, the script will automatically answer questions based on the points per question.
3. **Answer Highlighting**: The script can highlight correct and incorrect answers during the quiz.
4. **UI Customization**: The floating UI allows you to adjust the settings like points per question, enable/disable auto-answer, and view answers.

## Customization

- **Points per Question**: You can set the points per question between 500 and 1000 using a slider.
- **Auto Answer**: Toggle auto-answering for each question. The script calculates the time delay based on the points you set.
- **Input Lag**: Adjust input lag to fine-tune the script's accuracy.
  
## Troubleshooting

- **Quiz not loading**: Make sure you entered a valid quiz ID. If the input box background turns red, the quiz ID is invalid.
- **Script not working**: Ensure that you have Tampermonkey or Greasemonkey installed and the script is properly saved.

## Credits

- **Made by**: [TWNYk](https://github.com/TWNYK)
- **Contributors**:
  - [jokeri2222](https://github.com/jokeri2222)
  - [Epic0001](https://github.com/Epic0001)

## License

This script is for educational purposes. Please do not use it in a manner that violates the terms of service of Kahoot or any other platform. Use at your own risk.
```

### Key Points in the README:

- **Script Name and Version**: Clearly specified at the top.
- **Features**: List of core functionalities provided by the script, like auto-answer, show answers, and input lag adjustment.
- **Installation Instructions**: Step-by-step guide on how to set up the script using Tampermonkey or Greasemonkey.
- **Code Block**: Instructions to paste the code into the browser console or save it as a userscript.
- **How It Works**: A brief explanation of the main script functionalities and how they interact with the Kahoot interface.
- **Customization**: Details about adjustable features like points per question and input lag.
- **Credits**: Acknowledgment of the creators and contributors.
