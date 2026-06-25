# Quiz CLI

Quiz CLI is an interactive Node.js terminal quiz for learning JavaScript, Node.js, and general programming concepts.

## Project Description

The app loads multiple-choice questions from `data/questions.json`, lets you choose a category and question count, and guides you through a short quiz with scoring, progress tracking, explanations, and answer review.

It is built with ES modules, uses no external dependencies, and targets Node.js 18+.

## Features

- Category selection
- Question count selection
- Multiple-choice questions
- Randomized question order
- Score and progress tracking
- Explanations after each question
- Review of incorrect answers
- Replay support
- Terminal color helpers for clearer output

## Prerequisites

- Node.js 18 or newer
- A terminal that supports interactive input

## Installation

Clone the repository and install dependencies:

```bash
npm install
```

## Usage

Start the quiz with:

```bash
npm start
```

You can also run the entry point directly:

```bash
node index.js
```

The `npm test` script is available as well:

```bash
npm test
```

## Interactive Flow

A typical session looks like this:

```text
$ npm start

📚 QUIZ CLI
Test your programming knowledge!

Choose a category:
> JavaScript Basics
> Node.js Fundamentals
> General Programming

How many questions?
> All questions
> 3 questions
> 5 questions

Starting quiz...
Select your answer by entering the number.

Question 1 of 3
> 1) ...
> 2) ...
> 3) ...

✓ Correct!
💡 Explanation text...

📊 QUIZ RESULTS
Score: 2/3
Would you like to play again? (y/n)
```

## How to Add or Edit Quiz Questions

Quiz content lives in `data/questions.json`.

### Categories

Questions are grouped under a top-level `categories` object. Each category has a key, a display name, and a `questions` array.

Supported category keys in the current data set:

- `javascript`
- `nodejs`
- `general`

### Question format

Each question entry should include:

- `question` — the question text
- `options` — an array of answer choices
- `answer` — the index of the correct option
- `explanation` — a short explanation shown after the answer and in the review section

### Example structure

```json
{
  "categories": {
    "example": {
      "name": "Example Category",
      "questions": [
        {
          "question": "Your question here?",
          "options": ["A", "B", "C", "D"],
          "answer": 1,
          "explanation": "Why B is correct."
        }
      ]
    }
  }
}
```

## Project Structure

```text
.
├── index.js
├── package.json
├── data/
│   └── questions.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### File Overview

- `index.js` — application entry point and main quiz loop
- `src/quiz.js` — quiz logic, scoring, shuffling, progress bar, and results review
- `src/input.js` — `readline` helpers for terminal input
- `src/colors.js` — terminal color helpers
- `data/questions.json` — quiz questions and categories

## Scripts

From `package.json`:

- `npm start` — runs the quiz application
- `npm test` — runs the Node.js test runner

## Testing

`npm test` runs `node --test`. If no test files are present, the command may be minimal or act as a placeholder.

## Troubleshooting

- **Node version errors**: Make sure Node.js 18+ is installed.
- **Terminal input issues**: Run the app in an interactive terminal, not a non-interactive shell or redirected session.
- **Color display problems**: If your terminal does not support ANSI colors, the quiz may still run but formatting can appear differently.

## Contributing

Contributions are welcome. Useful improvements include adding questions, refining quiz flow, improving terminal UX, and expanding tests.

Before submitting changes, run:

```bash
npm test
```

## License

MIT
