# ******************* PYTHON CALCULATOR USING TKINTER *******************
# ******************* LET'S GET STARTED ********************
from tkinter import *
import tkinter.font as font

root = Tk()  # FOR CREATING MAIN WINDOW
root.geometry("365x432")  # FOR GIVING SIZE TO THE MAIN WINDOW
root.resizable(0, 0)  # TO PREVENT RESIZING THE MAIN WINDOW
root.title("Calculator")  # FOR GIVING TITLE TO THE MAIN WINDOW

# FUNCTION FOR BUTTONS


def button_click(item):
    global expressions
    expressions = expressions + str(item)
    input_text.set(expressions)

# FUNCTION FOR CLEARING RESULT SCREEN


def button_clear():
    global expressions
    expressions = ""
    input_text.set("")

# FUNCTION FOR CALCULATION RESULT


def button_equal():
    global expressions
    calculated_result = str(eval(expressions))
    input_text.set(calculated_result)
    expressions = ""


expressions = ""  # TO TEMPORARILY STORE THE MATHEMATICAL EXPRESSION

input_text = StringVar()  # TO STORE THE MATHEMATICAL EXPRESSION AFTER ARITHMETIC OPERATIONS 

# FOR CHANGING THE FONT SIZE OF LETTERS AND DIGITS
font_size = font.Font(size=18)

# CREATING FRAME FOR THE INPUT FIELD

input_frame = Frame(root, width=270, height=50, highlightbackground="black",
                    highlightcolor="black", highlightthickness=2)
input_frame.pack(side=TOP)

# CREATING INPUT FIELD INTO THE INPUT FRAME

input_field = Entry(input_frame, font=("bold", 20), textvariable=input_text,
                    width=21, bg="#aaa", justify="right")
input_field.pack(ipady=10)

# CREATING BUTTONS FRAME BELOW INPUT FRAME
button_frame = Frame(root, width=380, height=270, bg="grey")
button_frame.pack()

# CREATING BUTTONS INTO BUTTON FRAME
# FIRST ROW
clear = Button(button_frame, text="C", fg="black", width=16, height=2, bg="#eee",
               cursor="exchange", command=lambda: button_clear())
clear.grid(row=0, column=0, columnspan=3, padx=1, pady=1)
clear['font'] = font_size

divide = Button(button_frame, text="/", fg="black", width=4, height=2, bg="#eee",
                command=lambda: button_click('/'))
divide.grid(row=0, column=3, padx=1, pady=1)
divide['font'] = font_size

# SECOND ROW

seven = Button(button_frame, text="7", fg="black", width=4, height=2, bg="#fff",
               command=lambda: button_click(7))
seven.grid(row=1, column=0, padx=1, pady=1)
seven['font'] = font_size

eight = Button(button_frame, text="8", fg="black", width=4, height=2, bg="#fff",
               command=lambda: button_click(8))
eight.grid(row=1, column=1, padx=1, pady=1)
eight['font'] = font_size

nine = Button(button_frame, text="9", fg="black", width=4, height=2, bg="#fff",
              command=lambda: button_click(9))
nine.grid(row=1, column=2, padx=1, pady=1)
nine['font'] = font_size

multiply = Button(button_frame, text="*", fg="black", width=4, height=2, bg="#eee",
                  command=lambda: button_click('*'))
multiply.grid(row=1, column=3, padx=1, pady=1)
multiply['font'] = font_size

# THIRD ROW

four = Button(button_frame, text="4", fg="black", width=4, height=2, bg="#fff",
              command=lambda: button_click(4))
four.grid(row=2, column=0, padx=1, pady=1)
four['font'] = font_size

five = Button(button_frame, text="5", fg="black", width=4, height=2, bg="#fff",
              command=lambda: button_click(5))
five.grid(row=2, column=1, padx=1, pady=1)
five['font'] = font_size

six = Button(button_frame, text="6", fg="black", width=4, height=2, bg="#fff",
             command=lambda: button_click(6))
six.grid(row=2, column=2, padx=1, pady=1)
six['font'] = font_size

minus = Button(button_frame, text="-", fg="black", width=4, height=2, bg="#eee",
               command=lambda: button_click('-'))
minus.grid(row=2, column=3, padx=1, pady=1)
minus['font'] = font_size

# FOURTH ROW

one = Button(button_frame, text="1", fg="black", width=4, height=2, bg="#fff",
             command=lambda: button_click(1))
one.grid(row=3, column=0, padx=1, pady=1)
one['font'] = font_size

two = Button(button_frame, text="2", fg="black", width=4, height=2, bg="#fff",
             command=lambda: button_click(2))
two.grid(row=3, column=1, padx=1, pady=1)
two['font'] = font_size

three = Button(button_frame, text="3", fg="black", width=4, height=2, bg="#fff",
               command=lambda: button_click(3))
three.grid(row=3, column=2, padx=1, pady=1)
three['font'] = font_size

plus = Button(button_frame, text="+", fg="black", width=4, height=2, bg="#eee",
              command=lambda: button_click('+'))
plus.grid(row=3, column=3, padx=1, pady=1)
plus['font'] = font_size

# FIFTH ROW

zero = Button(button_frame, text="0", fg="black", width=4, height=2, bg="#fff",
              command=lambda: button_click(0))
zero.grid(row=4, column=0, padx=1, pady=1)
zero['font'] = font_size

dot = Button(button_frame, text=".", fg="black", width=4, height=2, bg="#fff",
             command=lambda: button_click('.'))
dot.grid(row=4, column=1, padx=1, pady=1)
dot['font'] = font_size

equal = Button(button_frame, text="=", fg="black", width=10, height=2, bg="#eee",
               cursor="plus", command=lambda: button_equal())
equal.grid(row=4, column=2, columnspan=2, padx=1, pady=1)
equal['font'] = font_size

root.mainloop()
