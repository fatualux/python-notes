# Tkinter Library

Tkinter is the standard Python library for creating graphical user interfaces (GUIs). It provides a set of tools to develop desktop applications with widgets like buttons, labels, text boxes, and more.

## Key Concepts

### 1. **Main Window**

- **Overview**: The root window is the main container for any Tkinter application.
- **Features**:
  - Acts as the primary window for the application.
  - Can be customized with size, title, and more.
- **Example**:
  ```python
  import tkinter as tk

  root = tk.Tk()
  root.title("My Application")
  root.geometry("400x300")
  root.mainloop()
  ```

### 2. **Widgets**

- **Overview**: Building blocks for the GUI, such as buttons, labels, entries, etc.
- **Features**:
  - Each widget has methods for customization, placement, and event handling.
  - Widgets are placed using layout managers: `.pack()`, `.grid()`, and `.place()`.
- **Example**:
  ```python
  import tkinter as tk

  root = tk.Tk()

  label = tk.Label(root, text="Hello, Tkinter!")
  label.pack()

  button = tk.Button(root, text="Click Me", command=lambda: print("Button Clicked"))
  button.pack()

  root.mainloop()
  ```

### 3. **Event Handling**

- **Overview**: Binding actions to user interactions like clicks, keypresses, etc.
- **Features**:
  - Use the `.bind()` method to attach events to widgets.
  - Common events include `<Button-1>`, `<KeyPress>`, etc.
- **Example**:
  ```python
  import tkinter as tk

  def on_key(event):
      print(f"Key pressed: {event.char}")

  root = tk.Tk()
  root.bind("<KeyPress>", on_key)

  root.mainloop()
  ```

### 4. **Layout Management**

- **Overview**: Positioning widgets within the main window.
- **Features**:
  - **Pack**: Stacks widgets vertically or horizontally.
  - **Grid**: Places widgets in a 2D grid.
  - **Place**: Absolute positioning using x and y coordinates.
- **Example**:
  ```python
  import tkinter as tk

  root = tk.Tk()

  # Pack example
  label1 = tk.Label(root, text="Label 1")
  label1.pack(side="top")

  # Grid example
  label2 = tk.Label(root, text="Label 2")
  label2.grid(row=0, column=0)

  # Place example
  label3 = tk.Label(root, text="Label 3")
  label3.place(x=100, y=100)

  root.mainloop()
  ```

### 5. **Dialogs**

- **Overview**: Built-in pop-up dialogs for file selection, messages, and more.
- **Features**:
  - Common dialogs include `messagebox`, `filedialog`, etc.
- **Example**:
  ```python
  import tkinter as tk
  from tkinter import messagebox, filedialog

  root = tk.Tk()

  # Messagebox example
  messagebox.showinfo("Info", "This is a messagebox")

  # File dialog example
  file_path = filedialog.askopenfilename()
  print(f"Selected file: {file_path}")

  root.mainloop()
  ```

### 6. **Canvas**

- **Overview**: A versatile widget for drawing shapes, creating images, and other custom graphics.
- **Features**:
  - Supports shapes like rectangles, lines, ovals, and more.
  - Allows embedding other widgets and images.
- **Example**:
  ```python
  import tkinter as tk

  root = tk.Tk()

  canvas = tk.Canvas(root, width=200, height=200)
  canvas.pack()

  # Drawing shapes
  canvas.create_rectangle(50, 50, 150, 150, fill="blue")
  canvas.create_line(0, 0, 200, 200, fill="red", width=5)

  root.mainloop()
  ```
