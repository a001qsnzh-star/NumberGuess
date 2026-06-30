import random
import turtle


target_answer = 0

target_answer = random.randint(1,200)

count_guesses = 0

correct = False
guess = ""
guess_int = 0

x = -100
y = 200
turtle.up()
turtle.goto(x,y)
turtle.down()
turtle.write("I've thought of a number, guess what's it?",\
font=("Arial", 15, "bold"))

def turtle_position():
    turtle.up()
    turtle. goto(x, y)
    turtle.down()

y = y- 40
turtle.up()
turtle. goto(x, y)
turtle.down()

low_bound = 1
high_bound = 200

while not correct:
    guess = turtle.textinput("Guessing Game!", "Please enter a number between \
1 and 200")
    guess_int = int(guess)
    count_guesses = count_guesses + 1
    

    if guess_int < 1 or guess_int > 200:
        turtle. write("please enter a number between 1 and 200, try agin!",\
        font=("Arial", 15, "bold"))
        y = y- 40
        turtle_position()
        
    elif guess_int < target_answer:
        if guess_int > low_bound:
            low_bound = guess_int
        turtle. write("It's between "+ str(low_bound)+ " and "+ str(high_bound)\
                      + ", try agian!", font=("Arial", 15, "bold"))
        y = y- 40
        turtle_position()
        
    elif guess_int > target_answer:
        if guess_int < high_bound:
            high_bound = guess_int
        turtle. write("It's between "+ str(low_bound)+ " and "+ str(high_bound)\
                      + ", try agin!", font=("Arial", 15, "bold"))
        y = y- 40
        turtle_position()
        
    else:
        x = x-150
        turtle_position()
        
        turtle. write("Your right! It is "+ guess +" !. It took you " + \
                      str(count_guesses)+" guesses to get the answer!",\
        font=("Arial", 20, "bold"))
        correct = True

# NumberGuess
