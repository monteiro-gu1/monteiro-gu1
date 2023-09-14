import random
# Define the game board
board = [[' ', ' ', ' '], [' ', ' ', ' '], [' ', ' ', ' ']]
# Define the player's position
player_x = 0
player_y = 0
# Define the dragon's position
dragon_x = random.randint(0, 2)
dragon_y = random.randint(0, 2)
# Define the treasure chest's position
treasure_x = random.randint(0, 2)
treasure_y = random.randint(0, 2)
# Define the game loop
while True:
    # Display the game board
    print_board(board)
    # Get the player's move
    move = input("Enter your move (w, a, s, d): ")
    # Update the player's position
    if move == "w":
        player_y -= 1
    elif move == "a":
        player_x -= 1
    elif move == "s":
        player_y += 1
    elif move == "d":
        player_x += 1
    # Check if the player has won
    if player_x == treasure_x and player_y == treasure_y:
        print("You win!")
        break
    # Check if the player has lost
    if player_x == dragon_x and player_y == dragon_y:
        print("You lose!")
        break
    # Update the dragon's position
    dragon_x = random.randint(0, 2)
    dragon_y = random.randint(0, 2)
# Define the function to print the game board
def print_board(board):
    for row in board:
        print(' | '.join(row))
