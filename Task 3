import tkinter as tk
import random
import string
from tkinter import messagebox

def generate_password():
    try:
        password_length = int(length_entry.get())
        if password_length <= 0:
            messagebox.showerror("Error", "Password length must be greater than 0")
            return

        password_characters = string.ascii_letters + string.digits + string.punctuation
        password = ''.join(random.choice(password_characters) for _ in range(password_length))
        password_label.config(text=f"Generated Password: {password}")
    except ValueError:
        messagebox.showerror("Error", "Please enter a valid password length")
root = tk.Tk()
root.title("Password Generator")
length_label = tk.Label(root, text="Enter password length:")
length_label.pack()
length_entry = tk.Entry(root)
length_entry.pack()

generate_button = tk.Button(root, text="Generate Password", command=generate_password)
generate_button.pack()
password_label = tk.Label(root, text="")
password_label.pack()
root.mainloop()
