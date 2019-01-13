Seun Onile-ere (28/05/17) Task 2: Fireside_Fee_Calculator

This program is being created so that an entry fee can be calculated for each player attempting to enter the Fireside Annual Card Gaming Leauge,
subsequently displaying the fee required to enter in the appropriate currency.

#States that as long as the variable 'request' equates to the value 'True', the code wil continue to run
    request = True
    while request == True:
    #Displays the welcome message that associates the player with the context of the program    
     print ('---------->>>Welcome to the Fireside Fee Calculator<<<---------- \n')

    #Imports 're' (Regular Expression) to specifiy a set of strings that matches it for the email validation, subsequently defining the function 'email'
     import re
     def email():
    #Creates a while loop pertaining to a duration in time whilst the variable 'email' is equal to the value 'False'
         emails = False
         while emails == False:
    #Creates a presence check for the variable 'Email_Address', meaning whilst the user input in response to the prompt is equal to a blank space (''), the user will be prompted to re-enter         
             Email_Address = input('Please enter your Email Address.  \n')
             while Email_Address == '':
                 Email_Address = input('Unfortunately this input does not contain any notable data; please re-enter your Email Address:  \n')
    #Establishes the variable 'match' as the syntax for a permissible value, for the variable 'Emali_Address' (userinput, '@', userinput , '.', userinput)
             match = re.search(r'[\w.-]+@[\w.-]+.\w+', Email_Address )
    #States that if the variable 'match' equates to the aformentioned syntax, the variable email is 'False', but anything other than that causes the variable 'email' to remain 'True'       
             if match:
                 print('This email contains the appropriate syntax.  \n', match.group())
                 emails = True
             else:
                 print('Please input the appropriate syntax.  \n')
    #This closes the previously defined function 'email', ending the email validation segment of the program
     email()

    #Creates a while loop pertaining to a duration in time whilst the variable 'valid' is equal to the value 'False'
     valid = False
     while valid == False:
    #Gives the variable 'fee' a value of '10'     
         fee = 10
    #States that if the user input in response to the prompt is equal to 'C', then variable 'Skill_Level' will be appropriated the value 'Casual', 'valid' will equal 'True' and 'fee' = 'fee + 20'
         Skill_Level = input('Please enter either E to denote an Expert skill level, or C to denote a Casual skill level.  \n')
         if Skill_Level == 'C':
             Skill_Level = 'Casual'
             fee = fee + 20
             valid = True
    #Otherwise, if the user input in response to the prompt is equal to 'E', then variable 'Skill_Level' will be appropriated the value 'Expert', 'valid' will equal 'True' and 'fee' = 'fee + 35'
         elif Skill_Level == 'E':
             Skill_Level = 'Expert'
             fee = fee + 35
             valid = True
    #If the user input equates to neither 'E' or 'C', anything besides the options given will cause the program to request another input, finalising the skill level segment of the program.         
         else:
             Skill_Level = input('Please enter either C or E to illustrate your level of experience.  \n')

    #Creates a list of 3 values ('AU,'US','UK) within the variable 'Countries'
     Countries = ['AU','US','UK']
    #Creates a while loop pertaining to a duration in time whilst the variable 'valid' is equal to the value 'False'
     valid = False
     while valid == False:
    #States that if the user input in repsonse to the prompt is equal to the first item in the list ('AU'), the string 'Your payment will be in converted into Australlian Dollars' will be printed     
         Player_Country = input('Please enter either the UK, US or AU in capital letters, as your area of residence to dentote the United Kingdom, United States or Australlia respectively.  \n')
         if Player_Country == Countries[0]:
              print('Your payment will be in converted into Australlian Dollars')
    #The value within the variable 'fee' will thus be multiplied by 2, whilst the entrance fee is printed in conjuction with the correlating currency (AUD), causing 'valid' to equate to 'True'
              fee = fee * 2
              print ('Your entrance fee is',fee,'AUD')
              valid = True
    #Otherwise, if the user input in repsonse to the prompt is equal to the second item in the list ('US'), the string 'Your payment will be in converted into American Dollars' will be printed          
         elif Player_Country == Countries[1]:
              print('Your payment will be in converted into American Dollars')
    #The value within the variable 'fee' will thus be multiplied by 1.5, whilst the entrance fee is printed in conjuction with the correlating currency (USD), causing 'valid' to equate to 'True'          
              fee = fee * 1.5
              print ('Your entrance fee is',fee,'USD')
              valid = True
    #Contrarily, if the user input in repsonse to the prompt is equal to the last item in the list ('UK'), the string 'Your payment will be in converted into Pounds Sterling' will be printed
         elif Player_Country == Countries[2]:
              print('Your payment will be in converted into Pounds Sterling')
    #The value within the variable 'fee' will thus remain the same, whilst the entrance fee is printed in conjuction with the correlating currency (GBP), causing 'valid' to equate to 'True'          
              print ('Your entrance fee is',fee,'GBP')
              valid = True
    #If the user input equates to neither 'AU','US' or 'UK, than anything besides the options given will cause the program to request another input, finishing the regional segment of the program. 
         else:
             Player_Country = input('Please enter one of the given options of the UK, US or AU, as your country of residence.  \n')

    #Creates a while loop pertaining to a duration in time whilst the variable 'valid' is equal to the value 'False'
     valid = False
     while valid == False:
    #States that if the user input in response to the prompt is equal to 'No', then the string 'Thank you for your time, your Fireside Fee Calculator details have been safely secured' is printed
         Response = input('Do you wish to calculate another fee? If so, reply with "Yes" to restart the Fireside Fee Calculator, or "No" to end the program.  \n' )
         if Response == 'No':
            print ('Thank you for your time, your Fireside Fee Calculator details have been safely secured. The program will now return to the title message.  \n' )
    #Following the words 'The program will now return to the title message', the program will then print the intial welcome message ('---------->>>Welcome to the Fireside Fee Calculator<<<----------')
            print ('---------->>>Welcome to the Fireside Fee Calculator<<<---------- \n')
    #After the previous message has been printed, 'request' (the variable from the start of the program) will then equate to 'False', using the statement 'break' to terminate the loop 
            request = False
            break
    #Otherwise, if the user input in repsonse to the prompt is equal to 'Yes', then the string 'The program will now begin anew' will be printed, and 'valid' will equate to 'True'
         if Response == 'Yes':
             print ('The program will now begin anew \n')
             valid = True
    #Following the previous message having been printed, the statement 'continue' will then be used to return the control to the beginning of the program      
             continue
    #If the user input equates to neither 'Yes' or 'No', than anything besides the options given will cause the program to request another input, concluding the recapitulatory segment of the program       
         else:
            Response = input('Please enter either Yes or No to illustrate your choice  \n')
#This closes the previously defined function 'Calculator', fully encapsulating the program within the function of 'Calculator'
