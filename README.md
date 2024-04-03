import os
import tkinter as tk
from tkinter import filedialog

def list_files():
    directory = filedialog.askdirectory()
    files = os.listdir(directory)
    file_list.delete(0, tk.END)
    for file in files:
        file_list.insert(tk.END, file)

# Create the main window
root = tk.Tk()
root.title("File List Manager")

# Create a button to trigger file listing
list_button = tk.Button(root, text="List Files", command=list_files)
list_button.pack(pady=10)

# Create a listbox to display the file names
file_list = tk.Listbox(root, width=50)
file_list.pack()

# Run the GUI
root.mainloop()
