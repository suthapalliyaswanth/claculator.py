# claculator.py
from tkinter import *
root = Tk()
root.title('simple calculator')

e = Entry(root,width=35,borderwidth=5)
e.grid(row=0, column=0, columnspan=3,padx=10,pady=10)

def num(n):
     current = e.get()
     e.delete(0,END)
     e.insert(0,str(current)+str(n))

def add():
    first_number = e.get()
    global f_num
    f_num=first_number
    global ch
    ch = 'add'
    e.delete(0,END)

def sub():
    first_number = e.get()
    global f_num
    f_num =first_number
    global ch
    ch = 'sub'
    e.delete(0,END)

def mul():
    first_number = e.get()
    global f_num
    f_num =first_number
    global ch
    ch = 'mul'
    e.delete(0,END)

def div():
    first_number = e.get()
    global f_num
    f_num =first_number
    global ch
    ch = 'div'
    e.delete(0,END)

def equal():
    second_number = e.get()
    e.delete(0, END)
    if ch=='add':
        e.insert(0, int(f_num) + int(second_number))
    if ch=='sub':
        e.insert(0, int(f_num) - int(second_number))
    if ch=='mul':
        e.insert(0, int(f_num) * int(second_number))
    if ch=='div':
        e.insert(0, int(f_num) / int(second_number))
def clear():
    e.delete(0,END)


# buttons

but_1 = Button(root, text='1', padx=40,pady=20,command= lambda : num(1))
but_2 = Button(root, text='2', padx=40,pady=20,command= lambda : num(2))
but_3 = Button(root, text='3', padx=40,pady=20,command= lambda : num(3))
but_4 = Button(root, text='4', padx=40,pady=20,command= lambda : num(4))
but_5 = Button(root, text='5', padx=40,pady=20,command= lambda : num(5))
but_6 = Button(root, text='6', padx=40,pady=20,command= lambda : num(6))
but_7 = Button(root, text='7', padx=40,pady=20,command= lambda : num(7))
but_8 = Button(root, text='8', padx=40,pady=20,command= lambda : num(8))
but_9 = Button(root, text='9', padx=40,pady=20,command= lambda : num(9))
but_0 = Button(root, text='0', padx=40,pady=20,command= lambda : num(0))
but_sum = Button(root, text='+', padx=40,pady=20,command=add)
but_equal = Button(root, text='=', padx=90, pady=20, command=equal)
but_clear = Button(root, text='clear', padx=80, pady=20, command=clear)
but_sub = Button(root, text='-', padx=40,pady=20,command=sub)
but_mul = Button(root, text='*', padx=40,pady=20,command=mul)
but_div = Button(root, text='/', padx=40,pady=20,command=div)

but_1.grid(row=3, column=0)
but_2.grid(row=3, column=1)
but_3.grid(row=3, column=2)

but_4.grid(row=2, column=0)
but_5.grid(row=2, column=1)
but_6.grid(row=2, column=2)

but_7.grid(row=1, column=0)
but_8.grid(row=1, column=1)
but_9.grid(row=1, column=2)

but_0.grid(row=4, column=0)
but_clear.grid(row=4, column=1, columnspan=2)
but_sum.grid(row=5, column=0)
but_equal.grid(row=5, column=1, columnspan=2)
but_sub.grid(row=6, column=0)
but_mul.grid(row=6, column=1)
but_div.grid(row=6, column=2)

root.mainloop()
