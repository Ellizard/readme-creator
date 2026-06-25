# Quiz CLI

An interactive command-line quiz game for learning JavaScript.

## Project Description

Quiz CLI is a Node.js ES module CLI application that loads quiz questions from JSON, lets you choose a category and question count, and runs a multiple-choice quiz in the terminal with scoring, progress tracking, and missed-question review.

## Setup Instructions

Install dependencies with:

```bash
npm install
```

## How to Run the Project

Start the quiz with:

```bash
npm start
```

Or run the entry point directly:

```bash
node index.js
```

## Key Features

- Category selection
  - JavaScript Basics
  - Node.js Fundamentals
  - General Programming
- Question count selection
- Randomized question order using Fisher-Yates shuffle
- Score tracking
- Progress display
- Explanation display after each question
- Review of missed questions with explanations
- Replay flow to start another round
- Terminal styling with ANSI color helpers

## Requirements

- Node.js 18 or newer
- A terminal that supports ANSI colors

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
- `explanation` — explanation shown after the quiz

## Scripts

From `package.json`:

- `npm start` — runs `node index.js`
- `npm test` — runs the Node.js test runner with `node --test`

## Contributing

Contributions are welcome. If you'd like to help improve the quiz, consider adding more questions, improving category coverage, refining the terminal experience, or extending tests.

Before opening a pull request, make sure the project still runs correctly and tests pass:

```bash
npm test
```

## License

MIT
