# guess-number-in-python
#Guess number 


import random
# core logic of the game
print('Welcome to the number guess game')
print('Enter your numbers from 1 to 20')
print('*' * 30)
print('you have only 3 chances to guess correct no: ')
print('*' * 30)
wallet=0
play_again= True
while play_again:
    if wallet <10:
        amt=int(input('Kindly recharge with min 10/per game: '))
        wallet+=amt
       
    if wallet<=10:
        print('Insufficient Recharge amount to play the game: ')
    if wallet > 9:
        print('10 Rs deducted for this game')
        wallet-=10
        c_guess = random.randint(1,20)
        for chance in range (1,4):
          u_guess= int(input('enter a guess: '))
          if u_guess== c_guess:
            # True Part
            print('Congratz,you guessed correctly')
            if chance==1:
                print('you have won 100 Rs')
                wallet+=100
            elif chance==2:
                print('you have won 80 Rs')
                wallet+=80
            else:
                print('you have won 60 Rs')
                wallet+=60
            break
             #Default
          else:
           print('sorry,you guess is wrong')
           # Provide hint
           if u_guess < c_guess:
              print('I am thinking of a bigger number')
           else:
                print('I am thinking of a smaller number')
    choice=input('Do you want to play again [yes/no]: ')
    if choice !='yes':
     play_again= False
     wd=input('Do you want to withdraw [yes/no]: ')
     if wd=='yes':
        wd_amt=int(input('Enter the amount: ' ))
        if wd_amt <=wallet:
           print(f'{wd_amt} is transferred to: ')
           wallet -= wd_amt
     else:
           print(' Thanks for the donation ')
print('Thanks for playing')
