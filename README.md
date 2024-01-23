# narges-ghaedamini
پروژه لاکپشت با زبان پایتون
@narges13801373

import turtle
import random
import winsound

Score=0
s=turtle.Screen()
s.setup(600,600)
s.title('  بازي لاکپشت ')
s.bgcolor('pink')
#ترسيم ديوار
wall=turtle.Turtle()
wall.up()
wall.goto(-275,275)
wall.down()
wall.width(4)
for i in range(4):
    wall.fd(550)
    wall.rt(90)
wall.ht()
#ايجاد شخصيت بازي
laki=turtle.Turtle()
laki.shape('turtle')
laki.color('darkgreen')
laki.shapesize(3)
laki.up()
#ايجاد شخصيت توپ
ball=turtle.Turtle()
ball.shape('circle')
ball.color('red')
ball.up()
ball.goto(random.randint(-260,260),random.randint(-260,260))
#چاپ امتياز
wr=turtle.Turtle()
wr.up()
wr.goto(-270,275)
wr.ht()
wr.color('purple')
wr.write('امتياز='+str(Score),font=('b koodak',12,'bold'))
#توابع حرکت لاکپشت با کيبورد
def move_right():
    laki.right(30)
def move_left():
    laki.left(30)
s.listen()
s.onkey(move_right,'Right')
s.onkey(move_left,'Left')
#حرکت مداوم
while True:
 laki.fd(1)
 if laki.xcor()>270 or laki.xcor()<-270 or laki.ycor()>270 or laki.ycor()<-270:
     laki.right(180)
     Score=Score-4
     wr.clear()
     wr.write('امتياز='+str(Score),font=('b koodak',12,'bold'))
 if laki.distance(ball)<15:
     ball.goto(random.randint(-260,260),random.randint(-260,260))
     Score=Score+8
     wr.clear()
     wr.write('امتياز='+str(Score),font=('b koodak',12,'bold'))
 if Score>=40:
     wr.goto(-75,0)
     wr.write(' تبريک برنده شدي ',font=('b koodak',30,'bold'))
     break
