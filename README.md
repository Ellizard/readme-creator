# Quiz CLI

## Project Overview

Quiz CLI is an interactive command-line quiz game built with Node.js. It lets users choose a category, answer multiple-choice questions, and review their results at the end of each run.

The project is designed as a lightweight educational tool for practicing JavaScript, Node.js fundamentals, and general programming concepts directly in the terminal.

## Features

- Interactive terminal-based quiz experience
- Multiple quiz categories:
  - JavaScript Basics
  - Node.js Fundamentals
  - General Programming
- Configurable question count per round
- Randomized question order
- Immediate feedback for correct and incorrect answers
- Progress indicator during the quiz
- Final score summary with performance message
- Review section for missed questions
- Colorized terminal output using ANSI escape codes

## Tech Stack

- **Language:** JavaScript (ES Modules)
- **Runtime:** Node.js 18+
- **Built-in modules used:**
  - `node:fs/promises`
  - `node:path`
  - `node:url`
  - `node:readline`
- **Package manager:** npm
- **No external dependencies**

## Installation / Setup

### Prerequisites

- Node.js **18.0.0 or newer**
- npm

### Steps

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd quiz-cli
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

   > The project does not currently rely on external packages, but running `npm install` will prepare the local environment and generate a lockfile if needed.

3. Start the quiz:
   ```bash
   npm start
   ```

## Configuration

The quiz data is stored in:

- `data/questions.json`

This file defines the quiz categories, questions, answer options, correct answer indexes, and explanations.

### Supported content structure

Each category contains:
- `name`: category display name
- `questions`: array of questions

Each question contains:
- `question`: the question text
- `options`: multiple-choice options
- `answer`: the zero-based index of the correct option
- `explanation`: optional explanation shown after answering

No environment variables are required.

## Usage Examples

### Start the application

```bash
npm start
```

### Run the quiz

1. Choose a category from the menu.
2. Choose how many questions to answer.
3. Enter the number of the answer choice for each question.
4. Review your final score and any incorrect answers.
5. Choose whether to play again.

### Run tests

```bash
npm test
```

> Note: the repository currently includes a `test` script (`node --test`), but no dedicated test files are present in the repository snapshot.

## File Structure

```text
.
├── data/
│   └── questions.json      # Quiz content and question bank
├── index.js                # Application entry point
├── package.json            # Project metadata and scripts
└── src/
    ├── colors.js           # ANSI color helpers for terminal output
    ├── input.js            # Readline-based user input helpers
    └── quiz.js             # Quiz game logic and scoring
```

## How It Works

- `index.js` loads the quiz data from `data/questions.json`
- `src/input.js` handles prompting and menu selection in the terminal
- `src/quiz.js` manages shuffling, scoring, progress tracking, and results output
- `src/colors.js` formats terminal output with ANSI colors

## Development Notes

- The application uses ES Modules (`"type": "module"` in `package.json`)
- The quiz questions are shuffled each time a round starts
- Answers are stored during the session so the final review can show missed answers
- The app exits with a non-zero status code if an error occurs during startup or gameplay

## Contributing

Contributions are welcome. Good starting points include:

- Adding new quiz categories
- Expanding the question bank
- Improving the UI/terminal layout
- Adding automated tests
- Enhancing score tracking or difficulty levels

If you contribute, please keep the data format in `data/questions.json` consistent with the existing schema.

## License

This project is licensed under the MIT License, as declared in `package.json`.
