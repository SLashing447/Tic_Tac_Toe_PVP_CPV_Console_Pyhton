# Tic_Tac_Toe_PVP_CPV_Console_Pyhton
import random
global d
def entrance_game():
    a = int(input("Enter \"1\" for PVP\n"
                  "Enter \"2\" for CVP\n"))
    if a == 1:
        comp = random.randint(0, 2)
        if comp == 0:
            print("X Won the toss")
            game_Input(True)
        else:
            print("O Won the toss")
            game_Input(False)
    elif a == 2:
        comp = random.randint(0, 2)
        if comp == 0:
            print("X won the toss")
            Computer_Versus_Player(True)
        else:
            print("O won the toss")
            Computer_Versus_Player(False)
def game_Input(X_turn):
    board = ['_','_','_','_','_','_','_','_','_']
    Board_print(board)
    y=0
    while y<=8:
        if X_turn:
            print("X's Turn...")
            print("Enter box number")
            q = int(input())
            if board[q]=="X" or board[q]=="O":
                continue
            else:
                board[q]="X"
                X_turn=False
                win_Check(board)
        else:
            print("O's Turn...")
            print("Enter box number")
            z = int (input())
            if board[z]=="X" or board[z]=="O":
                continue
            else:
                board[z]="O"
                X_turn=True
                win_Check(board)
        Board_print(board)
        y = y + 1
def win_Check(board):
    if (board[0]=="X" and board[1]=="X" and board[2]=="X") or (board[3]=="X" and board[4]=="X" and board[5]=="X") or (board[6]=="X" and board[7]=="X" and board[8]=="X"):
        print("---X won the game---")
        Board_print(board)
        win_State = True
    elif(board[0]=="X" and board[3]=="X" and board[6]=="X") or (board[1]=="X" and board[4]=="X" and board[7]=="X") or (board[2]=="X" and board[5]=="X" and board[8]=="X"):
        print("---X won the game---")
        Board_print(board)
        win_State = True
    elif(board[0]=="X" and board[4]=="X" and board[8]=="X") or (board[2]=="X" and board[4]=="X" and board[6]=="X"):
        print("---X won the game---")
        Board_print(board)
        win_State = True
    if (board[0]=="O" and board[1]=="O" and board[2]=="O") or (board[3]=="O" and board[4]=="O" and board[5]=="O") or (board[6]=="O" and board[7]=="O" and board[8]=="O"):
        print("---O won the game--")
        Board_print(board)
        win_State = True
    elif(board[0]=="O" and board[3]=="O" and board[6]=="O") or (board[1]=="O" and board[4]=="O" and board[7]=="O") or (board[2]=="O" and board[5]=="O" and board[8]=="O"):
        print("---O won the game--")
        Board_print(board)
        win_State = True
    elif(board[0]=="O" and board[4]=="O" and board[8]=="O") or (board[2]=="O" and board[4]=="O" and board[6]=="O"):
        print("---O won the game--")
        Board_print(board)
        win_State = True
    else:
        win_State=False
    if win_State:
        print("Enter \"1\" to play again\n"
              "Enter \"2\" to Exit")
        sh = int(input())
        if sh==1:
            entrance_game()
        else:
            exit()
def Computer_Versus_Player(X_turn):
    board = ['_', '_', '_', '_', '_', '_', '_', '_', '_']
    Board_print(board)
    zoo = 0
    while zoo <= 8:
        if X_turn:
            print("X's Turn...")
            print("Enter box number")
            w = int(input())
            if board[w] == "X" or board[w] == "O":
                continue
            else:
                board[w] = "X"
                X_turn = False
                win_Check(board)
        else:
          re=random.randint(0, 8)
          if board[re] == "X" or board[re] == "O":
            continue
          else:
            board[re] = "O"
            X_turn = True
            win_Check(board)
        Board_print(board)
        zoo = zoo + 1
def Board_print(board):
    print("This is the board...")
    print(board[0] + "|" + board[1] + "|" + board[2])
    print(board[3] + "|" + board[4] + "|" + board[5])
    print(board[6] + "|" + board[7] + "|" + board[8])
entrance_game()
