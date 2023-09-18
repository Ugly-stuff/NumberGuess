// Generate a random number between 1 and 100
const randomNumber = Math.floor(Math.random() * 100) + 1;

let numberOfGuesses = 0; // Initialize the number of guesses
let userScore = 100; // Initialize the user's score

console.log("Welcome to the Number Guessing Game! Guess a number between 1 and 100.");

const readline = require('readline');
const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout
});

function askUserForGuess() {
  rl.question("Enter your guess: ", (userInput) => {
    const userGuess = parseInt(userInput);

    if (isNaN(userGuess) || userGuess < 1 || userGuess > 100) {
      console.log("Please enter a valid number between 1 and 100.");
      askUserForGuess(); // Ask again for a valid guess
      return;
    }

    numberOfGuesses++; // Increment the number of guesses
    const difference = Math.abs(userGuess - randomNumber);

    if (difference === 0) {
      console.log(`Congratulations! You guessed the number ${randomNumber} in ${numberOfGuesses} guesses. Your score is ${userScore}.`);
      rl.close(); // End the game
    } else {
      if (difference <= 10) {
        console.log("Hot");
      } else {
        console.log("Cold");
      }

      // Adjust the user's score based on the difference between the guess and the actual number
      userScore -= 10;

      if (userGuess < randomNumber) {
        console.log("Try a larger number.");
      } else {
        console.log("Try a smaller number.");
      }

      console.log(`Your score is now ${userScore}.`);
      askUserForGuess(); // Ask the user for another guess
    }
  });
}

askUserForGuess(); // Start the game by asking for the first guess
