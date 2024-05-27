# Calculator
//this repo is created by Shatha Bandr

from tkinter import *

expression = ''

def press(userInput):
     global expression
     expression = expression + str(userInput)
     equation.set(expression)

def equalPress():
     try:
      global expreesion
      result = str(eval(expression))
      equation.set(result)
     except:
         equation.set("Error")
def clear():
    global expression
    expression = ""
    equation.set("")
gui = Tk()

gui.title("Simple Calculator")

gui.geometry("280x250")

titleLabel = Label(gui, text="Simple Calc", fg="brown", font=("Century 20 bold"))
titleLabel.grid(columnspan=4, pady=20)

equation = StringVar()

expressionfield = Entry(gui, textvariable = equation)
expressionfield.grid(columnspan=4,padx = 5,  pady=10, ipadx = 70)

btn1 = Button(gui, text=' 1 ',command = lambda: press(1), height= 1, width = 7)
btn1.grid(row=2, column=0)

btn2 = Button(gui, text='2',command = lambda: press(2), height= 1, width = 7 )
btn2.grid(row=2, column=1)

btn3 = Button(gui, text='3', command = lambda: press(3), height= 1, width = 7 )
btn3.grid(row=2, column=2)

btn4 = Button(gui, text='4', command = lambda: press(4),height= 1, width = 7 )
btn4.grid(row=3, column=0)

btn5 = Button(gui, text='5', command = lambda: press(5), height= 1, width = 7 )
btn5.grid(row=3, column=1)

btn6 = Button(gui, text='6',command = lambda: press(6), height= 1, width = 7 )
btn6.grid(row=3, column=2)

btn7 = Button(gui, text='7',command = lambda: press(7), height= 1, width = 7 )
btn7.grid(row=4, column=0)

btn8 = Button(gui, text='8', command = lambda: press(8),height= 1, width = 8 )
btn8.grid(row=4, column=1)

btn9 = Button(gui, text='9',command = lambda: press(9), height= 1, width = 8 )
btn9.grid(row=4, column=2)

btn0 = Button(gui, text='0',command = lambda: press(0), height= 1, width = 8 )
btn0.grid(row=5, column=0)

dotBtn = Button(gui, text='.',command = lambda: press('.'), height= 1, width = 8 )
dotBtn.grid(row=5, column=1)

equalBtn = Button(gui, text= '=',command = equalPress,height = 1, width = 8, bg= "brown", fg = "White")
equalBtn.grid(row =5, column = 2)

plusBtn = Button(gui, text = "+" ,command = lambda: press('+'), height= 1, width= 8)
plusBtn.grid(row = 2, column = 3)

minusBtn = Button(gui, text = '-',command = lambda: press('-'), height = 1, width = 8)
minusBtn.grid(row = 3, column = 3)

multipleBtn = Button(gui, text = '*', command = lambda: press('*'),height = 1, width = 8)
multipleBtn.grid(row = 4, column = 3)

divideBtn = Button(gui, text = '/', command = lambda: press('/'), height = 1, width = 8)
divideBtn.grid(row = 5 , column = 3)

clearBtn = Button(gui, text = 'C',command = clear, height = 1, width = 8)
clearBtn.grid(row = 6 , column = 0)


gui.mainloop()
