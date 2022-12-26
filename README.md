# MasterMind-game
Mastermind game python code
Coded by Kavindu Sandaruwa

#--------------------------------------while for check play again condition-----------------------------------------------------------------
play_again = "yes"
while (play_again == "yes"):
    #-----------------------------------------------------------Kavindu Sandaruwan----------------------------------------------------
    #----------------------------------------------------------creating random list---------------------------------------------------
    import random
    number_list = [1,2,3,4,5,6]
    random_list = []
    #random.sample(list of numbers you want to select,numbers you want to get)
    random_list = (random.sample(number_list,4))
    #print(random_list)
    """ Here, a list is created that includes numbers from 1 to 6 and 4 numbers are randomly selected from it.
    The purpose of doing so is to avoid repeating the same number over and over again"""
    #-----------------------------------------------------------Creating variables----------------------------------------------------
    name = ""
    attempts = 1
    user_list = []
    zero_list = []
    result1 = ""
    result2 = ""
    result3 = ""
    result4 = ""
    play_again = ""
    score = 100
    try_again = 1
    #----------------------------------------------Taking user name and creating graphical user interface-------------------------------------
    print()
    name = str(input("Enter your name: "))
    print()
    print("__________________ Hi","<",name,">","Welcome to GameInt ___________________")
    print()
    print("Numbers to Guess - XXXX")
    print(f'Coded by Kavindu                                      Colour mapping:')
    print(f'                                                         1-White 2-Blue 3-Red')
    print(f'                                                         4-Yellow 5-Green 6-Purple')
    print()
    print("Note: When entering numbers please leave a space between two numbers ")
    print()
    print(f"Attempt No                     Guess                  Result")
    print("__________________________________________________________________________")
    print()
    """
    When 'f' is typed. we can type the code by leaving a space. Its like we are just writing.
    Just use {} when putting variables.
    """
    #----------------------------------------------------------Taking user inputs--------------------------------------------------
    while (attempts < 9):
        num1 ,num2 ,num3 ,num4 = input(str(attempts)+")"+" Enter your 4 digit guess:-  ").split()
        #print("                         ",result1,result2,result3,result4)  
        num1 = int(num1)
        num2 = int(num2)
        num3 = int(num3)
        num4 = int(num4)
        """The split() method splits a string into a list.
        You can specify the separator, default separator is any whitespace."""
         #---------------------------------------Check if user enterd wrong number-------------------------------------------------------- 
        if num1 > 6:
                print("...................The number you entered is incorrect!!!....................")
                continue
        elif num2 > 6:
                print("...................The number you entered is incorrect!!!....................")
                continue
        elif num3 > 6:
                print("...................The number you entered is incorrect!!!....................")
                continue
        elif num4 > 6:
                print("...................The 4number you entered is incorrect!!!....................")
                continue
        else:
                user_list = [num1,num2,num3,num4]
                print(user_list)
        if len(user_list) != 4:
            print("Out of range")
            break
        """'Break' in Python is a loop control statement. It is used to control the sequence of the loop.
        Suppose you want to terminate a loop and skip to the next code after the loop break will help you do that."""
        """The continue statement in Python returns the control to the beginning of the while loop.
        The continue statement rejects all the remaining statements in the current iteration of the
        loop and moves the control back to the top of the loop."""
        attempts = attempts + 1
        #If user enter zero list this programm will be ended
        zero_list = [0,0,0,0]
        if user_list == zero_list:
            print("You ended the game!!!")
            break
        """If user enterd 0000 game will be stoped."""
        #Compare user list and random list
        if user_list == random_list:
            print("-----------------------------------------------------> 1 1")
            print("                                                       1 1")
            score = 100 - 12.5 * (attempts - 1)
            print("You have scored",int(score),"points")
            print("Congratulations!!!  You have won the game...")
            break
        else:
            #Check first number...................................................
            if user_list[0] == random_list[0]:
                result1 = "1"              
            elif user_list[0] in random_list:
                result1 = "0"
            else:
                result1 = "."
            #Check second number...................................................
            if user_list[1] == random_list[1]:
                result2 = "1"                
            elif user_list[1] in random_list:
                result2 = "0"
            else:
                result2 = "."
            #Check third number...................................................
            if user_list[2] == random_list[2]:
                result3 = "1"               
            elif user_list[2] in random_list:
                result3 = "0"
            else:
                result3 = "."
            #Check fourth number.................................................
            if user_list[3] == random_list[3]:
                result4 = "1"                
            elif user_list[3] in random_list:
                result4 = "0"
            else:
                result4 = "."
        print("----------------------------------------------------->",result1,result3)
        print("                                                      ",result2,result4)        
    #Asking for another game.....................................................
    play_again = "no"
    print()
    play_again = str(input("Do you want to play another game(Yes/No)?_"))
    print("Thank you for playing...")


