# Word Scramble Game

## Project Description
This project implements a **Word Scramble Game** where the player must create valid words using a scrambled set of letters from a chosen word. The game focuses on reinforcing the following programming concepts:
- **File I/O**: Reading a dictionary file (`words.txt`) to fetch words.
- **Collections Framework**: Utilizing `Set` and `List` for efficient operations.
- **Encapsulation**: Using private fields and methods within classes.
- **String Manipulation**: Processing and validating user input.
- **Game Loops**: Continuous game logic with multiple options for user interaction.

Players can:
- View scrambled letters that can form multiple words.
- Guess words to score points, gaining more points the bigger the word.
- View the list of currently guessed words.
- Exit the game and view your final score.
## Project Guide

### Dependencies
To run this project, the following are required:
1. Java Development Kit installed.
2. A file named `words.txt` containing dictionary words, with only one word per line.
3. A command line to compile and run the Java program.

### How to Run the Project
1. Ensure `words.txt` is in the same directory as the `Project3` class file, otherwise the program will not work.
2. Compile the Java program in this order:
   ```bash
javac Project3.java
java Project3.java

### How to play the game
1. Compile and run the file
2. A mix of letters will appear on screen that form one or more words, up to 7 letters.
3. Type in words that can be made with these letters, if they are in the words.txt file you will be awarded points.

## Lessons Learned

- I had struggled to get the point system working when getting a bonus from a longer word. 
- I wanted to make it to where there was a command that could change the letters completely 
  if the player wanted new words, while keeping their points. 