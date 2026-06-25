# Quiz CLI

## Project Overview

Quiz CLI is an interactive command-line quiz game for learning JavaScript and Node.js fundamentals. It presents multiple-choice questions by category, tracks the user's score, shows explanations for answers, and lets players replay the quiz from the terminal.

The project is designed as a lightweight educational app and also demonstrates common Node.js concepts such as ES modules, file loading, async/await, and terminal input handling.

## Features

- Interactive terminal-based quiz experience
- Multiple categories:
  - JavaScript Basics
  - Node.js Fundamentals
  - General Programming
- Configurable number of questions per round
- Randomized question order
- Score tracking with final results summary
- Explanations shown after each answer
- Review of incorrect answers at the end
- Colorized terminal output
- Replay support after each quiz session

## Tech Stack

- **Language:** JavaScript (ES Modules)
- **Runtime:** Node.js >= 18
- **Built-in Node APIs:**
  - `node:fs/promises`
  - `node:path`
  - `node:url`
  - `node:readline`
- **Testing:** Node test runner (`node --test`)
- **No external dependencies**

## Installation / Setup

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd readme-creator
   ```

2. Install dependencies:

   This project does not use external npm packages, so there is nothing to install. You can still run `npm install` if you want npm to create a lockfile locally, but it is not required for the app to work.

3. Make sure you have Node.js 18 or newer installed.

4. Start the quiz:

   ```bash
   npm start
   ```

## Configuration

This repository does not currently require environment variables or external service configuration.

Quiz content is stored in:

- `data/questions.json`

To change or extend the quiz, edit that file and add or modify categories and questions.

## Usage Examples

### Start the application

```bash
npm start
```

### Run the tests

```bash
npm test
```

### Quiz flow

1. Launch the app.
2. Choose a category.
3. Choose how many questions to answer.
4. Answer each multiple-choice question by entering the option number.
5. Review your score and incorrect answers.
6. Choose whether to play again.

## File Structure

- `index.js` → application entry point and main quiz loop
- `src/quiz.js` → quiz logic, scoring, progress, and results rendering
- `src/input.js` → terminal input helpers built on `readline`
- `src/colors.js` → ANSI color utility functions for terminal output
- `data/questions.json` → quiz categories, questions, answer keys, and explanations
- `package.json` → project metadata, scripts, and Node.js engine requirement

## Running Tests

The repository includes a test script placeholder using the built-in Node.js test runner:

```bash
npm test
```

At the time of analysis, no dedicated test files were present in the repository, so this command will only work once tests are added.

## Contributing

Potential contribution areas include:

- Adding more quiz categories and questions
- Improving terminal UI/UX
- Adding automated tests
- Expanding score analytics or difficulty levels

If you contribute, keep the project dependency-free unless a new dependency is clearly justified.
