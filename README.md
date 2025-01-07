# number-guessing-game.py
It is a game ,which you should geuss the number 
import random

def welcome_message():
    print("👋 Welcome to the Number Guessing Challenge!")
    print("Your task is to guess the secret number. Let's see how good you are!")
    print("Choose your difficulty level:")
    print("1 - Easy (Range: 1 to 10)")
    print("2 - Medium (Range: 1 to 50)")
    print("3 - Hard (Range: 1 to 100)")

def get_difficulty():
    while True:
        try:
            level = int(input("Enter your choice (1, 2, or 3): "))
            if level == 1:
                return 10
            elif level == 2:
                return 50
            elif level == 3:
                return 100
            else:
                print("Invalid choice. Please choose 1, 2, or 3.")
        except ValueError:
            print("Please enter a valid number.")

def play_game():
    welcome_message()
    max_number = get_difficulty()
    secret_number = random.randint(1, max_number)
    attempts = 0
    print(f"\nGreat! I'm thinking of a number between 1 and {max_number}. Can you guess it?")
    
    while True:
        try:
            guess = int(input("Your guess: "))
            attempts += 1
            if guess < secret_number:
                print("Too low! Try again.")
            elif guess > secret_number:
                print("Too high! Try again.")
            else:
                print(f"🎉 Congratulations! You guessed it in {attempts} attempts.")
                break
        except ValueError:
            print("Please enter a valid number.")

def main():
    play_game()
    while True:
        replay = input("Do you want to play again? (yes/no): ").lower()
        if replay == "yes":
            play_game()
        elif replay == "no":
            print("Thanks for playing! Goodbye! 👋")
            break
        else:
            print("Please answer with 'yes' or 'no'.")

if __name__ == "__main__":
    main()
