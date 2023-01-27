from tkinter import*
from random import choice

def resta():
    global player
    k=choice(Players)
    for i in range(3):
        for j in range(3):
            Buttons[i][j]['text']=""
    player=k
    la.config(text=player+"'s Turn")
    for m in range(3):
        for n in range(3):
            Buttons[m][n].config(bg="Light yellow")

def check():
    x=0
    a=0
    Lii=[Buttons[0][0],Buttons[1][1],Buttons[2][2],Buttons[0][2],Buttons[1][1],Buttons[2][0]]
    for i in range(3):
        if Buttons[0][i]['text']==Buttons[1][i]['text']==Buttons[2][i]['text'] !="":
            for k in range(3):
                Buttons[k][i].config(bg='Green')
            return True
    for j in range(3):
        if Buttons[j][0]['text']==Buttons[j][1]['text']==Buttons[j][2]['text'] !="":
            for k in range(3):
                Buttons[j][k].config(bg='Green')
            return True


    if Buttons[0][0]['text']==Buttons[1][1]['text']==Buttons[2][2]['text']!="":
        for i in range(3):
            Lii[i].config(bg='Green')
        return True
    if Buttons[0][2]['text']==Buttons[1][1]['text']==Buttons[2][0]['text']!="":
        for i in range(3,6):
            Lii[i].config(bg="Green")
        return True
    for m in range(3):
        for n in range(3):
            if Buttons[m][n]['text'] != "":
                a += 1
    if a == 9:
        for m in range(3):
            for n in range(3):
                Buttons[m][n].config(bg="Yellow")
        return 'Tie'
    elif x==0:
        return False

def click(r,c):
    global player
    if Buttons[r][c]['text']=="" and check()is False:
        if player==Players[0]:
            Buttons[r][c]['text']=player
            if check()is False:
                player=Players[1]
                la.config(text=Players[1]+"'s Turn")
            elif check()is True:
                la.config(text=Players[0]+' Won!')
            elif check() is 'Tie':
                la.config(text="Game Tied!")
        else:
            Buttons[r][c]['text'] = player
            if check() is False:
                player = Players[0]
                la.config(text=Players[0] + "'s Turn")
            elif check() is True:
                la.config(text=Players[1] + ' Won!')
            elif check() is 'Tie':
                la.config(text="Game Tied!")

window=Tk()
Players=['X','O']
player=choice(Players)
Buttons=[[0,0,0],[0,0,0],[0,0,0]]

la=Label(text=player+"'s Turn",font=("consolas",25))
la.pack(side='top')
Re=Button(text="restart",font=('consolas',15),command=resta)
Re.pack(side='top')

Fr=Frame(window)
Fr.pack()

for i in range(3):
    for j in range(3):
        Buttons[i][j]=Button(Fr,text="",font=('consolas',15),width=7,height=3,bg='light yellow',command= lambda ro=i,co=j: click(ro,co))
        Buttons[i][j].grid(row=i,column=j)
window.mainloop()

l=[('b',1),('a',2),('c',3)]
l.sort(key=lambda x:x[1])
print(l)
