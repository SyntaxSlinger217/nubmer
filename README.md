# nubmer
randomnumb
import random

class GuessingGame:
    def __init__(self, lower_bound, upper_bound, max_attempts):
        self.lower_bound = lower_bound
        self.upper_bound = upper_bound
        self.max_attempts = max_attempts
        self.secret_number = random.randint(self.lower_bound, self.upper_bound)

    def play(self):
        print(f"Welcome to the Guessing Game! I'm thinking of a number between {self.lower_bound} and {self.upper_bound}.")
        print(f"You have {self.max_attempts} attempts to guess it.")

        for attempt in range(1, self.max_attempts + 1):
            guess = int(input(f"Attempt {attempt}: Your guess: "))

            if guess < self.secret_number:
                print("Too low! Try again.")
            elif guess > self.secret_number:
                print("Too high! Try again.")
            else:
                print(f"Congratulations! You guessed the number {self.secret_number} in {attempt} attempts!")
                break
        else:
            print(f"Sorry, you've used all {self.max_attempts} attempts. The number was {self.secret_number}.")

if __name__ == "__main__":
    lower_bound = int(input("Enter the lower bound of the range: "))
    upper_bound = int(input("Enter the upper bound of the range: "))
    max_attempts = int(input("Enter the maximum number of attempts: "))

    game = GuessingGame(lower_bound, upper_bound, max_attempts)
    game.play()
