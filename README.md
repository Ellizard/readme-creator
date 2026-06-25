# Quiz CLI

An interactive command-line quiz game for learning JavaScript.

## Features

- Interactive terminal-based quiz experience
- Category selection from:
  - JavaScript Basics
  - Node.js Fundamentals
  - General Programming
- Option to choose how many questions to answer
- Randomized question order using Fisher-Yates shuffle
- Score tracking and progress display
- End-of-quiz result summary
- Review of missed questions with explanations
- Replay flow to start another round

## Prerequisites

- **Node.js 18 or newer**
- A terminal that supports ANSI colors

## Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/Ellizard/readme-creator.git
cd readme-creator
npm install
```

## Usage

Start the quiz with:

```bash
npm start
```

Or run the entry point directly:

```bash
node index.js
```

### Example flow

1. Launch the app
2. Choose a quiz category
3. Select the number of questions
4. Answer each question in the terminal
5. Review your score and missed questions
6. Choose whether to play again

## Project Structure

```text
.
├── index.js              # CLI entry point
├── package.json          # Project metadata and scripts
├── data/
│   └── questions.json    # Quiz content and categories
└── src/
    ├── colors.js         # ANSI color utilities
    ├── input.js          # readline prompt/select/confirm helpers
    └── quiz.js           # Quiz logic, scoring, progress, review
```

## Data Format / Quiz Content Structure

Quiz content is stored in `data/questions.json` and organized by category.

Each question includes:

- `question` — the question text
- `options` — an array of possible answers
- `answer` — the index of the correct option
- `explanation` — explanation shown after the quiz

### Example structure

```json
{
  "JavaScript Basics": [
    {
      "question": "What does `typeof []` return?",
      "options": ["array", "object", "undefined", "function"],
      "answer": 1,
      "explanation": "In JavaScript, arrays are objects."
    }
  ]
}
```

Categories currently included:

- JavaScript Basics
- Node.js Fundamentals
- General Programming

## Scripts

From `package.json`:

- `npm start` — runs `node index.js`
- `npm test` — runs the Node.js test runner with `node --test`

## Contributing

Contributions are welcome. If you'd like to help improve the quiz, consider:

- adding more questions
- improving category coverage
- refining terminal UX
- extending tests

Before opening a pull request, make sure the project still runs correctly and tests pass:

```bash
npm test
```

## License

MIT
