# Olesia Kniazeva

## Contact Information
- **Location:** Daqing, China
- **Phone:** +7 963-157-52-69
- **Email:** knyazevaolesiya@gmail.com
- **Github:** [OlesiaKniazeva](https://github.com/OlesiaKniazeva)
- **LinkedIn:** [olesia-kniazeva](https://www.linkedin.com/in/olesia-kniazeva/)

## Summary

Hi! I'm Olesia, and I love building things for the web. My programming journey started at École 42, where I fell in love with coding while learning C. What began as figuring out how to make computers follow my commands has grown into a passion for creating websites and applications.

What makes my approach unique is how my programming skills are complemented by my design background. After getting comfortable with coding, I spent 4 months diving into design at Gorbunov Bureau. This experience taught me valuable principles about user experience and visual communication that I apply to my development work.

These days, I'm all about TypeScript and React, building modern web applications that combine clean code with thoughtful design. I'm excited about creating intuitive interfaces and learning best practices in frontend development.

I thrive on continuous learning - from exploring new programming concepts to engaging in weekly English book discussions. While I'm particularly drawn to frontend development, I'm comfortable working with backend technologies too. What really drives me is the process of turning ideas into working solutions.

## Technical Skills
- **Languages:** JavaScript, TypeScript, C/C++, Python
- **Frontend:** React.js, HTML5, CSS3
- **Backend:** Node.js
- **Testing:** Jest
- **Build Tools:** Webpack, Vite
- **Other Tools:** Git, Docker, Linux
- **Databases:** SQL
- **Design Tools:** Adobe Photoshop, Figma, Tableau, D3.js

## Code Examples

### Chess Pieces Coverage Calculator (Yandex Algorithm Contest)
**Problem:** Calculate the number of unattacked squares on a chessboard (8x8) with rooks and bishops. Each piece attacks along its valid movement paths until it encounters another piece.
- Rooks attack horizontally and vertically
- Bishops attack diagonally
- Need to count squares that are not under attack by any piece

**Solution Approach:**
```javascript
const fs = require("node:fs");

program();

/**
 * R — rook — ладья — horisontal, vertical lines
 * B — bishop — слон — dioganals
 * chess board size 8 * 8
 */

function getInput() {
  let fileContent = fs.readFileSync("./input.txt", "utf8");

  const result = fileContent.toString().split("\n");

  const rooks = [];
  const bishops = [];
  const board = Array(8)
    .fill(0)
    .map(() => Array(8).fill(0));

  result.forEach((line, idx) => {
    for (let i = 0; i < 8; ++i) {
      if (line[i] === "R") {
        rooks.push([i, idx]);
        board[idx][i] = 2;
      }
      if (line[i] === "B") {
        bishops.push([i, idx]);
        board[idx][i] = 2;
      }
    }
  });

  return [rooks, bishops, board];
}

function sendOutput(result) {
  fs.writeFileSync("output.txt", result.toString());
}

function program() {
  const [rooks, bishops, board] = getInput();

  const result = countFreeBoardSquares(rooks, bishops, board);

  sendOutput(result);
}

/**
 *
 * @param {Array<Array<number>>} rooks
 * @param {Array<Array<number>>} bishops
 * @param {Array<Array<boolean>>} board
 * @returns {number}
 */
function countFreeBoardSquares(rooks, bishops, board) {
  for (let rook of rooks) {
    let curX = rook[0];
    let curY = rook[1];

    move(curX, curY, board, ["up"]);
    move(curX, curY, board, ["down"]);
    move(curX, curY, board, ["right"]);
    move(curX, curY, board, ["left"]);
  }

  for (let bishop of bishops) {
    let curX = bishop[0];
    let curY = bishop[1];

    move(curX, curY, board, ["up", "left"]);
    move(curX, curY, board, ["up", "right"]);
    move(curX, curY, board, ["down", "right"]);
    move(curX, curY, board, ["down", "left"]);
  }

  let freeSquares = board.reduce((total, line) => {
    return (
      total +
      line.reduce((count, square) => (square === 0 ? count + 1 : count), 0)
    );
  }, 0);

  return freeSquares;
}

function move(curX, curY, board, moveTypes) {
  moveTypes.forEach((moveType) => {
    if (moveType === "up") {
      --curY;
    } else if (moveType === "down") {
      ++curY;
    } else if (moveType === "right") {
      ++curX;
    } else if (moveType === "left") {
      --curX;
    }
  });

  if (curX < 0 || curY < 0 || curX > 7 || curY > 7 || board[curY][curX] === 2) {
    return;
  }
  board[curY][curX] = 1;
  return move(curX, curY, board, moveTypes);
}

module.exports = { countFreeBoardSquares };

```

## Projects

### Nature Gifts – Restaurant Website
*Tech Stack: JavaScript, HTML & CSS, Webpack*  
[Live Demo](https://olesiakniazeva.github.io/restaurant-site/)

Single-page web application showcasing restaurant information, location, and menu.

**Key Achievements:**
- Implemented responsive user interface with adaptive navigation
- Developed modular architecture with dynamic content management
- Successfully deployed on GitHub Pages
- Gained practical experience with DOM manipulation and Webpack bundling

### Tic-Tac-Toe Game
*Tech Stack: JavaScript, HTML & CSS, Jest*  
[Live Demo](https://olesiakniazeva.github.io/Tic-Tac-Toe/)

Browser-based interactive game with customizable features.

**Key Features:**
- Implemented using Factory Pattern and IIFE for optimal code structure
- Added player customization and victory animations
- Developed comprehensive test suite using Jest
- Enhanced JavaScript development and testing skills

### Shell Command Line Interpreter
*Tech Stack: C, Make*  
[GitHub Repository](https://github.com/OlesiaKniazeva/Minishell_21)

A Bash-compatible command-line shell with comprehensive functionality.

**Key Implementations:**
- Developed robust command-line parser handling complex syntax
- Implemented core shell commands (echo, pwd, export, unset, env, exit)
- Added complete signal handling functionality
- Integrated support for pipes, redirects, and environment variables

## Professional Experience

### Internet Ads Assessor | Lionbridge
*2017 - 2020*
- Evaluated Google search results for relevance and accuracy
- Contributed to search engine algorithm improvements
- Enhanced user experience through detailed result analysis

## Education

### Ecole 42
*2021 - 2023*  
International coding school
- Completed extensive programming curriculum
- Focused on practical project-based learning
- Developed strong problem-solving skills

### Perm State University
*2013 - 2017*  
Bachelor of Science in Biology

## Languages
- **English:** 
  - Practical Level: B2 Upper-Intermediate
  - Certification: EF SET Certificate 82/100 (C2 Proficient)
  - Active participant in weekly English reading club, discussing literature and improving communication skills
  - Regularly consume professional and entertainment content in English (technical documentation, articles, media)
  - Maintain all professional documentation and personal notes in English
  - Daily practice through technical writing and communication
- **Chinese:** HSK2 level
- **Russian:** Native

## Certifications
- **Yandex Algorithms Training 5.0** - Yandex (Apr 2024)
  - Completed advanced algorithms and data structures course
  - Skills: Problem-solving, Algorithmic thinking, Data structures

- **Python Core** - EPAM Systems (Feb 2023)
  - Comprehensive Python programming course
  - Focus on core concepts and best practices

- **Docker Basics** - Karpov.courses (Nov 2022)
  - Container technology fundamentals
  - Docker deployment and management

- **Interactive SQL Course** - Stepik (Aug 2022)
  - Database design and management
  - Complex SQL queries and optimization

- **Modern C++ Development**
  - Yellow Belt - Coursera (Mar 2022)
  - White Belt - Coursera (Jan 2022)
  - Focus on modern C++ features and best practices

- **Gorbunov Bureau Design Course** (4 months)
  - Data Visualization and Design Principles
  - Experience with Tableau and D3.js
