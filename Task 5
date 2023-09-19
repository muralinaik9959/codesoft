import tkinter as tk
from tkinter import messagebox

contacts = {}

def add_contact():
    name = name_entry.get()
    phone = phone_entry.get()
    email = email_entry.get()
    address = address_entry.get()

    if name.strip() == "":
        messagebox.showerror("Error", "Name field cannot be empty")
        return

    contacts[name] = {"Phone": phone, "Email": email, "Address": address}
    clear_fields()
    update_contact_list()

def clear_fields():
    name_entry.delete(0, tk.END)
    phone_entry.delete(0, tk.END)
    email_entry.delete(0, tk.END)
    address_entry.delete(0, tk.END)

def update_contact_list():
    contact_listbox.delete(0, tk.END)
    for name in contacts:
        contact_listbox.insert(tk.END, name)

def view_contact():
    selected_contact = contact_listbox.get(tk.ACTIVE)
    if selected_contact:
        details = contacts[selected_contact]
        messagebox.showinfo("Contact Details", f"Name: {selected_contact}\nPhone: {details['Phone']}\nEmail: {details['Email']}\nAddress: {details['Address']}")
    else:
        messagebox.showwarning("Warning", "Please select a contact to view")

def search_contact():
    search_term = search_entry.get()
    search_results.delete(0, tk.END)
    for name in contacts:
        if search_term.lower() in name.lower() or search_term in contacts[name]["Phone"]:
            search_results.insert(tk.END, name)

def update_contact():
    selected_contact = contact_listbox.get(tk.ACTIVE)
    if selected_contact:
        new_phone = phone_entry.get()
        new_email = email_entry.get()
        new_address = address_entry.get()

        contacts[selected_contact]["Phone"] = new_phone
        contacts[selected_contact]["Email"] = new_email
        contacts[selected_contact]["Address"] = new_address

        clear_fields()
        update_contact_list()
    else:
        messagebox.showwarning("Warning", "Please select a contact to update")


def delete_contact():
    selected_contact = contact_listbox.get(tk.ACTIVE)
    if selected_contact:
        del contacts[selected_contact]
        clear_fields()
        update_contact_list()
    else:
        messagebox.showwarning("Warning", "Please select a contact to delete")

root = tk.Tk()
root.title("Contact Manager")
name_label = tk.Label(root, text="Name:")
name_label.grid(row=0, column=0)
name_entry = tk.Entry(root)
name_entry.grid(row=0, column=1)

phone_label = tk.Label(root, text="Phone:")
phone_label.grid(row=1, column=0)
phone_entry = tk.Entry(root)
phone_entry.grid(row=1, column=1)

email_label = tk.Label(root, text="Email:")
email_label.grid(row=2, column=0)
email_entry = tk.Entry(root)
email_entry.grid(row=2, column=1)

address_label = tk.Label(root, text="Address:")
address_label.grid(row=3, column=0)
address_entry = tk.Entry(root)
address_entry.grid(row=3, column=1)


add_button = tk.Button(root, text="Add Contact", command=add_contact)
add_button.grid(row=4, column=0, columnspan=2)

view_button = tk.Button(root, text="View Contact", command=view_contact)
view_button.grid(row=5, column=0, columnspan=2)

search_label = tk.Label(root, text="Search:")
search_label.grid(row=6, column=0)
search_entry = tk.Entry(root)
search_entry.grid(row=6, column=1)

search_button = tk.Button(root, text="Search", command=search_contact)
search_button.grid(row=7, column=0, columnspan=2)

update_button = tk.Button(root, text="Update Contact", command=update_contact)
update_button.grid(row=8, column=0, columnspan=2)

delete_button = tk.Button(root, text="Delete Contact", command=delete_contact)
delete_button.grid(row=9, column=0, columnspan=2)


contact_listbox = tk.Listbox(root)
contact_listbox.grid(row=0, column=2, rowspan=10)
search_results = tk.Listbox(root)
search_results.grid(row=0, column=3, rowspan=10)
root.mainloop()
