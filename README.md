sum = 0 
print() 
print("Welcome to 100 Game!") 
print("Two players start from 0 and alternatively add a number from 1 to 10 to the sum.") 
print("The player who reaches 100 wins.") 
print("*" * 50) 
print() 
 
 
def add_sum(x): 
    global sum 
    sum += x 
 
 
def is_winner(): 
    global sum 
    if sum >= 100: 
        return True 
    else: 
        return False 
 
 
def print_sum(): 
    global sum 
    print(f"SUM = {sum}") 
 
 
while True: 
    while True: 
        try: 
            p1 = int(input("Player 1's Move: ")) 
            break 
        except ValueError: 
            print("Invalid Input, Please Enter Values From 1 to 10") 
 
    while p1 > 100 - sum or p1 > 10: 
        print("Your number is bigger than the Remaining") 
        p1 = int(input("Player 1's Move: ")) 
    add_sum(p1) 
    print_sum() 
    if is_winner(): 
        print("Player 1 Wins!") 
        break 
 
    while True: 
        try: 
            p2 = int(input("Player 2's Move: ")) 
            break 
        except ValueError: 
            print("Invalid Input, Please Enter Values From 1 to 10") 
 
    while p2 > 100 - sum or p2 > 10: 
        print("Your number is bigger than the Remaining") 
        p1 = int(input("Player 2's Move: ")) 
    add_sum(p2) 
    print_sum() 
    if is_winner(): 
        print("Player 2 Wins!") 
        break
