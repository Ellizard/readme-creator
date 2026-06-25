# Quiz CLI

An interactive command-line quiz game for learning JavaScript.

## Project Description

Quiz CLI is a Node.js ES module application that loads multiple-choice questions from `data/questions.json`, prompts the user to choose a category and question count, and runs a terminal-based quiz with scoring, progress display, result review, and replay support.

The application is organized into small modules for:

- terminal color helpers
- reusable input handling
- quiz state and scoring logic
- the main CLI flow

## Setup Instructions

Install dependencies with:

```bash
npm install
```

The project requires Node.js `>=18.0.0`.

## How to Run the Project

Start the quiz with:

```bash
npm start
```

Or run the entry point directly:

```bash
node index.js
```

To run the test script:

```bash
npm test
```

## Key Features

- Category selection
  - JavaScript Basics
  - Node.js Fundamentals
  - General Programming
- Question count selection
- Randomized question order using the Fisher-Yates algorithm
- Score tracking
- Progress display with a visual progress bar
- Per-question correctness feedback
- Explanation display after each question
- End-of-quiz summary with performance message
- Review of incorrect answers
- Replay flow to start another round
- ANSI-based terminal color styling

## Project Structure

```text
.
├── README.md
├── package.json
├── index.js
├── data/
│   └── questions.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

## Quiz Data Format

Quiz content is stored in `data/questions.json` under a top-level `categories` object.

Available categories:

- `javascript` → JavaScript Basics
- `nodejs` → Node.js Fundamentals
- `general` → General Programming

Each question includes:

- `question` — the question text
- `options` — an array of possible answers
- `answer` — the index of the correct option
- `explanation` — the explanation shown after answering and in the review summary

## Scripts

From `package.json`:

- `npm start` — runs `node index.js`
- `npm test` — runs the Node.js test runner with `node --test`

## Architecture Overview

- `index.js` loads the quiz data, shows the banner, coordinates category and question-count selection, runs the quiz loop, and handles errors and cleanup.
- `src/input.js` wraps Node.js `readline` with reusable prompt, selection, confirmation, and pause helpers.
- `src/quiz.js` contains the `Quiz` class, shuffling logic, question rendering, scoring, progress tracking, and results output.
- `src/colors.js` provides ANSI color helpers used throughout the CLI.

## Contributing

Contributions are welcome. If you'd like to improve the quiz, you can add more questions, expand category coverage, refine the terminal experience, or extend the test suite.

Before opening a pull request, run the test script:

```bash
npm test
```

## License

MIT
