Hangman Game
-
Hangman is a classic word guessing game where the player attempts to uncover a hidden word by guessing one letter at a time. Each incorrect guess adds a part to the hangman drawing. The player wins by revealing the entire word before the drawing is completed.

-

Objectives and win/lose conditions:
-
Objective: Guess the hidden word by entering letters before running out of allowed wrong guesses or time.

Win: Reveal all letters in the word before wrong-limit/time runs out.

Lose: Reach the wrong guesses limit or the time limit before the word is completed.

-

Technology Stack
-
PHP

HTML

CSS 

JavaScript

-

Team Members and Contributions
-
Rafael Villacrusis: TESTER/BACKEND

Jr Maderal: FRONTEND/BACKEND

Ethan Henares: FRONTEND

Jhian Barnacha: TESTER/FRONTEND

Genel Padrique: TESTER

-

How to Play
-
1.Open the game in a browser (see How to Run below).

2.Choose a category (animals, country,fruits, food, sports).

3.Guess letters by clicking the letter buttons. Correct letters are revealed in the word display.

4.If you reveal all letters before the wrong-limit/time runs out, you win.

-

Controls: click/tap the letters or press the letter buttons on-screen.

-

Game mechanics:
-
-Category selects a word bank.

-Each wrong guess increments the hangman stage.

-Only have a limited allowed wrong guesses.

-and it has a time limit.

How to Run the Program (local)
-
Requirements:

PHP 8.0 or higher

A web server (e.g. built-in PHP server, XAMPP, MAMP, WAMP)

Browser (Chrome, Opera, Edge etc...)

-

Steps:
-
1.Place the project folder in your web server document root (e.g. htdocs/(filename)

2.Ensure leaderboard.json exists in the same directory as the main PHP file. If it's not there, the app will create it automatically.

3.Open Xampp and then Start APACHE

4.Open your browser then type "http://localhost/hangman/game.php"

5.Play the game.

-

Video Demonstration: https://drive.google.com/drive/folders/1xEazBseknSM6fitZW7ZdsoP3RDF_rCNw?usp=sharing

-

Source Code: https://drive.google.com/drive/folders/15-B_hoCoKRI30-SqJiI9vJLdTV3ag2-D?usp=sharing

-

Technical Documentation
-

Encapsulation
-
Each class encapsulates its data and operations: DiffBase variants hide their word lists and expose methods (getRand, wrongLimit, limitTime) to interact with that data. HangGame keeps all game state and methods to mutate state (guess, hintUse).

Session persistence is performed with serialize/unserialize so the HangGame instance keeps its state across requests.

-

Abstraction
-
DiffBase defines the abstraction of a difficulty profile; consumes only its public methods and does not depend on internal arrays being modified externally.

Consumers (the controller code creating HangGame) only need a DiffBase object and do not need to know implementation details of each difficulty class.

-

Inheritance
-
EasyDiff, MedDiff, HardDiff inherit from DiffBase, reusing logic and specializing data.

- 

Polymorphism               
-
HangGame accepts DiffBase and works with any subclass at runtime. The getDifficulty factory returns the appropriate subclass instance based on the input.
