import tkinter as tk
from tkinter import messagebox

def add_task():
    task = entry.get()
    if task:
        listbox.insert(tk.END, task)
        entry.delete(0, tk.END)
    else:
        messagebox.showwarning("Warning", "Please enter a task!")

def remove_task():
    try:
        selected_task = listbox.curselection()[0]
        listbox.delete(selected_task)
    except IndexError:
        messagebox.showwarning("Warning", "Please select a task to remove!")

def clear_tasks():
    listbox.delete(0, tk.END)

root = tk.Tk()
root.title("To-Do List")

frame = tk.Frame(root)
frame.pack(pady=10)

entry = tk.Entry(frame, font=("Helvetica", 14))
entry.pack(side=tk.LEFT, fill=tk.BOTH, expand=True)

add_button = tk.Button(frame, text="Add Task", font=("Helvetica", 12), command=add_task)
add_button.pack(side=tk.LEFT)

listbox = tk.Listbox(root, font=("Helvetica", 14), selectbackground="yellow")
listbox.pack(fill=tk.BOTH, expand=True)

remove_button = tk.Button(root, text="Remove Task", font=("Helvetica", 12), command=remove_task)
remove_button.pack()

clear_button = tk.Button(root, text="Clear All Tasks", font=("Helvetica", 12), command=clear_tasks)
clear_button.pack()

root.mainloop()
