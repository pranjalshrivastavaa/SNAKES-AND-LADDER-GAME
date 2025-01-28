# SNAKES-AND-LADDER-GAME
snakes_ladders = {
    3: 22, 5: 8, 11: 26, 17: 4, 19: 7,
    20: 29, 27: 1, 21: 9, 34: 16, 25: 30,
    # Add more as needed
}

#List for Player Positions
player_positions = [1, 1]  # Two players starting at position 1
#DICE ROLL
 import random
 dice_roll = random.randint(1, 6)
 #Movement: Update player position, check for snakes or ladders, and adjust accordingly.
 def move_player(player_idx, roll):
    new_pos = player_positions[player_idx] + roll
    if new_pos > 100:
        return  # Do not move if it exceeds the last cell
    player_positions[player_idx] = snakes_ladders.get(new_pos, new_pos)
    ```


