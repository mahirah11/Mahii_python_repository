# Mahii_python_repository_ for_game development...
import random

def get_computer_choice():
  """Generates a random choice for the computer."""
  choices = ["rock", "paper", "scissor"]
  return random.choice(choices)

def get_user_choice():
  """Gets the user's choice and validates it."""
  while True:
    user_choice = input("Enter your choice (rock, paper, scissor): ").lower()
    if user_choice in ["rock", "paper", "scissor"]:
      return user_choice
    else:
      print("Invalid choice. Please enter rock, paper, or scissor.")

def determine_winner(user_choice, computer_choice):
  """Determines the winner of the game."""
  if user_choice == computer_choice:
    return "It's a tie!"
  elif (
      (user_choice == "rock" and computer_choice == "scissor") or
      (user_choice == "paper" and computer_choice == "rock") or
      (user_choice == "scissor" and computer_choice == "paper")
  ):
    return "You win!"
  else:
    return "Computer wins!"

def play():
  """Plays a single round of Rock-paper-scissor."""
  computer_choice = get_computer_choice()
  user_choice = get_user_choice()
  print(f"You chose: {user_choice}")
  print(f"Computer chose: {computer_choice}")
  result = determine_winner(user_choice, computer_choice)
  print(result)

if __name__ == "__main__":
  play() 
