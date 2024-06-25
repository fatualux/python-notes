# Tkinter Demo

Here are some other useful widgets, and examples of usage.

```python

import tkinter as tk
from tkinter import messagebox

# Create a new window and configure it
window = tk.Tk()
window.title("Widget Examples")
window.minsize(width=600, height=600)

# Labels
label = tk.Label(window, text="This is new text", font=("Arial", 14))
label.pack(pady=10)

# Buttons
def action():
    print("Button Clicked")

button = tk.Button(window, text="Click Me", command=action)
button.pack(pady=10)

# Entries
entry = tk.Entry(window, width=30)
entry.insert(tk.END, string="Some text to begin with.")
entry.pack(pady=10)

# Text
text = tk.Text(window, height=5, width=30)
text.focus()
text.insert(tk.END, "Example of multi-line text entry.")
text.pack(pady=10)

# Spinbox
def spinbox_used():
    print(spinbox.get())

spinbox = tk.Spinbox(window, from_=0, to=10, width=5, command=spinbox_used)
spinbox.pack(pady=10)

# Scale
def scale_used(value):
    print(value)

scale = tk.Scale(window, from_=0, to=100, command=scale_used)
scale.pack(pady=10)

# Checkbutton
def checkbutton_used():
    print(checked_state.get())

checked_state = tk.IntVar()
checkbutton = tk.Checkbutton(window, text="Is On?", variable=checked_state, command=checkbutton_used)
checkbutton.pack(pady=10)

# Radiobutton
def radio_used():
    print(radio_state.get())

radio_state = tk.IntVar()
radiobutton1 = tk.Radiobutton(window, text="Option1", value=1, variable=radio_state, command=radio_used)
radiobutton2 = tk.Radiobutton(window, text="Option2", value=2, variable=radio_state, command=radio_used)
radiobutton1.pack(pady=5)
radiobutton2.pack(pady=5)

# Listbox
def listbox_used(event):
    print(listbox.get(listbox.curselection()))

listbox = tk.Listbox(window, height=4)
fruits = ["Apple", "Pear", "Orange", "Banana"]
for item in fruits:
    listbox.insert(tk.END, item)
listbox.bind("<<ListboxSelect>>", listbox_used)
listbox.pack(pady=10)

# Canvas
canvas = tk.Canvas(window, width=200, height=100)
canvas.create_line(0, 0, 200, 100)
canvas.create_rectangle(50, 20, 150, 80, fill="blue")
canvas.pack(pady=10)

# Frame
frame = tk.Frame(window, borderwidth=2, relief="sunken")
frame.pack(pady=10, fill="x")
frame_label = tk.Label(frame, text="Frame Example")
frame_label.pack()

# Menu
def show_info():
    messagebox.showinfo("Information", "This is a Tkinter application")

menu = tk.Menu(window)
window.config(menu=menu)

file_menu = tk.Menu(menu, tearoff=0)
menu.add_cascade(label="File", menu=file_menu)
file_menu.add_command(label="Open", command=show_info)
file_menu.add_command(label="Save", command=show_info)
file_menu.add_separator()
file_menu.add_command(label="Exit", command=window.quit)

help_menu = tk.Menu(menu, tearoff=0)
menu.add_cascade(label="Help", menu=help_menu)
help_menu.add_command(label="About", command=show_info)

window.mainloop()
```
