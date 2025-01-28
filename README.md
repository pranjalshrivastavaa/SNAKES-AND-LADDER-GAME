# SNAKES-AND-LADDER-GAME


snakes_ladders = {
    3: 22, 5: 8, 11: 26, 17: 4, 19: 7,
    20: 29, 27: 1, 21: 9, 34: 16, 25: 30,
    # Add more as needed
}

#List for Player Positions
player_positions = [1, 1]  # Two players starting at position 1
#DICE ROL
import random
 dice_roll = random.randint(1, 6)
 #Movement: Update player position, check for snakes or ladders, and adjust accordingly.
 def move_player(player_idx, roll):
    new_pos = player_positions[player_idx] + roll
    if new_pos > 100:
        return  # Do not move if it exceeds the last cell
    player_positions[player_idx] = snakes_ladders.get(new_pos, new_pos)
    ```
Win Condition: Check if a player reaches position 100.
   if player_positions[player_idx] == 100:
    print(f"Player {player_idx + 1} wins!")

#Turtle Graphics :Drawing the Board: Use Turtle to create a grid with numbered cells
import turtle

def draw_board():
    turtle.speed(0)
    turtle.penup()
    for row in range(10):
        for col in range(10):
            x = col * 50
            y = row * 50
            turtle.goto(x, y)
            turtle.pendown()
            turtle.forward(50)
            turtle.right(90)
            turtle.forward(50)
            turtle.right(90)
            turtle.forward(50)
            turtle.right(90)
            turtle.forward(50)
            turtle.right(90)
            turtle.penup()
    turtle.hideturtle()
#Player Movement Animation: Use Turtle to animate a player moving on the board.

def move_turtle(player_turtle, position):
    row, col = divmod(position - 1, 10)
    x = col * 50 + 25
    y = row * 50 + 25
    player_turtle.goto(x, y)

    
#Game Loop Create a loop to manage turns, roll the dice, and move players.

def play_game():
    while True:
        for i in range(len(player_positions)):
            input(f"Player {i + 1}, press Enter to roll the dice...")
            roll = random.randint(1, 6)
            print(f"Player {i + 1} rolled: {roll}")
            move_player(i, roll)
            move_turtle(player_turtles[i], player_positions[i])
            if player_positions[i] == 100:
                print(f"Player {i + 1} wins!")
                return
