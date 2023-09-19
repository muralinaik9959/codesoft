import tkinter as tk
import random
from tkinter import messagebox


user_score = 0
computer_score = 0

def determine_winner(user_choice, computer_choice):
    global user_score, computer_score
    if user_choice == computer_choice:
        return "It's a tie!", user_score, computer_score
    elif (
        (user_choice == "rock" and computer_choice == "scissors")
        or (user_choice == "scissors" and computer_choice == "paper")
        or (user_choice == "paper" and computer_choice == "rock")
    ):
        user_score += 1
        return "You win!", user_score, computer_score
    else:
        computer_score += 1
        return "Computer wins!", user_score, computer_score


def play_round(user_choice):
    choices = ["rock", "paper", "scissors"]
    computer_choice = random.choice(choices)

    result, user_score, computer_score = determine_winner(user_choice, computer_choice)
    result_label.config(text=f"Result: {result}")
    user_score_label.config(text=f"Your Score: {user_score}")
    computer_score_label.config(text=f"Computer Score: {computer_score}")

def reset_scores():
    global user_score, computer_score
    user_score = 0
    computer_score = 0
    user_score_label.config(text="Your Score: 0")
    computer_score_label.config(text="Computer Score: 0")


def play_again():
    user_choice_label.config(text="Your Choice: ")
    result_label.config(text="Result: ")
    computer_choice_label.config(text="Computer Choice: ")

root = tk.Tk()
root.title("Rock-Paper-Scissors Game")
user_choice_label = tk.Label(root, text="Your Choice: ")
user_choice_label.pack()

rock_button = tk.Button(root, text="Rock", command=lambda: play_round("rock"))
paper_button = tk.Button(root, text="Paper", command=lambda: play_round("paper"))
scissors_button = tk.Button(root, text="Scissors", command=lambda: play_round("scissors"))
rock_button.pack()
paper_button.pack()
scissors_button.pack()

result_label = tk.Label(root, text="Result: ")
result_label.pack()

computer_choice_label = tk.Label(root, text="Computer Choice: ")
computer_choice_label.pack()

user_score_label = tk.Label(root, text="Your Score: 0")
user_score_label.pack()

computer_score_label = tk.Label(root, text="Computer Score: 0")
computer_score_label.pack()

reset_button = tk.Button(root, text="Reset Scores", command=reset_scores)
reset_button.pack()

play_again_button = tk.Button(root, text="Play Again", command=play_again)
play_again_button.pack()
root.mainloop()
