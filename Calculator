import tkinter as tk
from math import sqrt

class CalculatorApp(tk.Tk):
    def __init__(self):
        super().__init__()
        self.title("Calculator")
        self.geometry("370x500")

        # Font for buttons and heading
        button_font = ("Comic Sans MS", 14)

        self.result_var = tk.StringVar()

        # Create the calculator widgets
        self.create_widgets(button_font)

    def create_widgets(self, button_font):
        # Entry widget to display the result with Comic Sans MS font
        self.result_entry = tk.Entry(self, textvariable=self.result_var, font=("Comic Sans MS", 20))
        self.result_entry.grid(row=0, column=0, columnspan=4, padx=10, pady=10)

        # Calculator buttons with colors
        buttons = [
            ('7', '#FFD700'), ('8', '#FFD700'), ('9', '#FFD700'), ('/', '#FFA07A'),
            ('4', '#FFD700'), ('5', '#FFD700'), ('6', '#FFD700'), ('*', '#FFA07A'),
            ('1', '#FFD700'), ('2', '#FFD700'), ('3', '#FFD700'), ('-', '#FFA07A'),
            ('0', '#FFD700'), ('.', '#FFD700'), ('=', '#98FB98'), ('+', '#FFA07A'),
            ('√', '#87CEFA'), ('x^2', '#87CEFA'), ('C', '#FF6347'), ('CE', '#FF6347')
        ]

        # Function to handle button clicks
        def on_button_click(value):
            current_value = self.result_var.get()

            if value == '=':
                try:
                    result = eval(current_value)
                    self.result_var.set(str(result))
                except Exception as e:
                    self.result_var.set("Error")
            elif value == '√':
                try:
                    result = sqrt(float(current_value))
                    self.result_var.set(str(result))
                except Exception as e:
                    self.result_var.set("Error")
            elif value == 'C':
                self.result_var.set('')
            elif value == 'CE':
                self.result_var.set(current_value[:-1])
            elif value == 'x^2':
                try:
                    number = float(current_value)
                    result = number ** 2
                    self.result_var.set(str(result))
                except Exception as e:
                    self.result_var.set("Error")
            elif value == '.':
                # Check if a decimal point is already present in the current value
                if '.' not in current_value:
                    self.result_var.set(current_value + '.')
            else:
                self.result_var.set(current_value + value)

        # Create buttons and arrange them on the grid
        row = 1
        col = 0
        for button_text, bg_color in buttons:
            tk.Button(self, text=button_text, width=5, height=2, font=button_font,
                      command=lambda value=button_text: on_button_click(value), bg=bg_color).grid(row=row, column=col, padx=5, pady=5)
            col += 1
            if col > 3:
                col = 0
                row += 1

if __name__ == "__main__":
    app = CalculatorApp()
    app.mainloop()
