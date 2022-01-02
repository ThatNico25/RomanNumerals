from tkinter import *
import tkinter as tk

root = tk.Tk()
icon = PhotoImage(file = 'icon.png')
root.iconphoto(False, icon)
root.title('RomanNumerals')
root.config(bg='lightblue')
w = Canvas(root, width=500, height=0)
w.pack()

valnumber = tk.StringVar(root)
valletter = tk.StringVar(root)
valresult = tk.StringVar(root)

class RomanNumerals:
    def to_roman(number):
        try:
            val = int(valnumber.get())

            if val >= 4000 or val <=0:
                valresult.set("Error")
                return

            letter = ""
            number_m = int(0)
            number_cm = int(0)
            number_d = int(0)
            number_cd = int(0)
            number_c = int(0)
            number_xc = int(0)
            number_l = int(0)
            number_xl = int(0)
            number_x = int(0)
            number_remain = int(0)

            # M (1000)
            number_m = int(val / 1000) 
            if number_m >= 1:
                for x in range(number_m):
                    letter += "M"
            else:  
                number_m = 0

            # CM (900)
            number_cm = (val / 1000) - (number_m)
            if number_cm > 0.899 and number_cm <= 1:
                letter += "CM"
            else:  
                number_cm = 0

            # D (500)
            number_d = (val / 500) - number_m*2 - (round(number_cm)*1.8)
            if number_d >= 1:
                for x in range(int(number_d)):
                    letter += "D"
            else:  
                number_d = 0
            number_d = int((number_d))

            # CD (400)
            number_cd = (val / 500) - number_m*2 - (round(number_cm)*1.8)
            if number_cd > 0.79999 and number_cd <= 1:
                letter += "CD"
            else:
                number_cd = 0

            # -- C (100) --
            number_c = (val / 100) - (number_m*10) - (round(number_cm)*9) - (number_d*5) - (round(number_cd)*4)
            if number_c >= 1:
                for x in range(int(number_c)):
                    letter += "C"
            else:
                number_c = 0  
            number_c = int((number_c))

            # XC (90)
            number_xc = (val / 100) - (number_m*10) - (round(number_cm)*9) - (number_d*5) - (round(number_cd)*4) - number_c
            if number_xc > 0.899999 and number_xc <= 1:
                letter += "XC"
            else:
                number_xc = 0

            # L (50)
            number_l = (val / 50) - (number_m*20) - (round(number_cm)*18) - (number_d*10) - (round(number_cd)*8) - (number_c*2) - (round(number_xc)*1.8)
            if number_l >= 1:
                for x in range(int(number_l)):
                    letter += "L"
            else:
                number_l = 0
            number_l = int(number_l)

            # XL (40)
            number_xl = (val / 50) - (number_m*20) - (round(number_cm)*18) - (number_d*10) - (round(number_cd)*8) - (number_c*2) - (round(number_xc)*1.8) - number_l
            if number_xl >= 0.799999 and number_xl <= 1:
                letter += "XL"
            else:
                number_xl = 0

            # -- X (10) --
            number_x = (val / 10) - (number_m*100) - (round(number_cm)*90) - (number_d*50) - (round(number_cd)*40) - (number_c*10) - (round(number_xc)*9)- (number_l*5) - (round(number_xl)*4) 
            for x in range(int(number_x)):
                letter += "X"

            # Below 10    
            number_remain = val % 10
            switcher={
                9:"IX",
                8:"VIII",
                7:"VII",
                6:"VI",
                5:"V",
                4:"IV",
                3:"III",
                2:"II",
                1:"I"
            }

            if number_remain > 0 and number_remain < 10:
                letter += switcher.get(number_remain, "nope")

            valresult.set(letter)
            return letter
        except:
            valresult.set("Error")
            return
 
    def from_roman(number):

        roman_num = valletter.get().upper()
        nb = 0
        isException = False
        count = 0

        for x in range(len(roman_num)):

            # Check if there is 4 of the same letter
            if roman_num[x:x+1] == roman_num[x+1:x+2]:
                count += 1
            else:
                count = 0

            if count == 3:
                valresult.set("Error")
                return

            # Transform letter into number
            if isException:
                isException = False   
            elif roman_num[x:x+2] == "CM":
                nb += 900
                isException = True    
            elif roman_num[x:x+2] == "CD":
                nb += 400
                isException = True       
            elif roman_num[x:x+2] == "XC":
                nb += 90
                isException = True   
            elif roman_num[x:x+2] == "XL":
                nb += 40
                isException = True   
            elif roman_num[x:x+1] == "M":
                nb += 1000
            elif roman_num[x:x+1] == "D":
                nb += 500
            elif roman_num[x:x+1] == "C":
                nb += 100
            elif roman_num[x:x+1] == "L":
                nb += 50
            elif roman_num[x:x+1] == "X":
                nb += 10
            elif roman_num[x:x+2] == "IX":
                nb += 9
                valresult.set(nb)
                return nb
            elif roman_num[x:x+4] == "VIII":
                nb += 8
                valresult.set(nb)
                return nb
            elif roman_num[x:x+3] == "VII":
                nb += 7
                valresult.set(nb)
                return nb
            elif roman_num[x:x+2] == "VI":
                nb += 6
                valresult.set(nb)
                return nb
            elif roman_num[x:x+1] == "V":
                nb += 5
                valresult.set(nb)
                return nb
            elif roman_num[x:x+2] == "IV":
                nb += 4
                valresult.set(nb)
                return nb
            elif roman_num[x:x+3] == "III":
                nb += 3
                valresult.set(nb)
                return nb
            elif roman_num[x:x+2] == "II":
                nb += 2
                valresult.set(nb)
                return nb
            elif roman_num[x:x+1] == "I":
                nb += 1
                valresult.set(nb)
                return nb
            else:
                valresult.set("Error")
                return

        valresult.set(nb)
        return nb

info = Message(root, text = 'The number is between 1 and 3999!', width=200)
info.config(bg='lightblue')
info.pack()

messageVar1 = Message(root, text = 'Result')
messageVar1.config(bg='lightblue')
messageVar1.pack()

result = Entry(root,textvariable=valresult, width=15,fg="red",bd=3,selectbackground='green', state='disabled').pack()

messageVar2 = Message(root, text = 'To Roman', width=100)
messageVar2.config(bg='lightblue')
messageVar2.pack()
tk.Label(root, text='Number')
e1 = Entry(root,textvariable = valnumber,width=25,fg="blue",bd=3,selectbackground='violet').pack()
button1 = tk.Button(root, 
                text='Submit', 
                fg='White', 
                bg= 'dark green',
                height = 1, 
                width = 10, 
                command= lambda:RomanNumerals.to_roman(e1)).pack()

messageVar3 = Message(root, text = "To Number", width=100)
messageVar3.config(bg='lightblue')
messageVar3.pack()
tk.Label(root, text='Letter')
e2 = Entry(root,textvariable = valletter,width=25,fg="blue",bd=3,selectbackground='violet').pack()
button2 = tk.Button(root, 
                text='Submit', 
                fg='White', 
                bg= 'dark green',
                height = 1, 
                width = 10, 
                command= lambda:RomanNumerals.from_roman(e2)).pack()

author = Message(root, text = 'Mabe by Nicolas Poulin', width=150)
author.config(bg='lightblue')
author.pack()

root.mainloop()