# PythonErrorHandling


Errors in Python

    Errors are inevitable in Python, no matter how long you have been programming. So it is best to get comfortable with this fact and learn
    how to handle these errors. 
    
    Error handling includes a couple techniques, one of which involving the 'try' and 'except' keyword.
    
    while True:
        try:
            age = int(input("what is your age? "))
            print(age)
        except:
            print("please enter a number")
        else:
            print("thank you!")
            break
    
    This instructs the program to continuously try the code within the try block and if anything does not follow the desired input, it will print
    the message within the except block. The else statement will execute if the try statement received appropriate input, printing the message
    within its code block, and then breaking the while loop. 
    
    You can also specify what kind of error your except statement should handle:
    
     while True:
        try:
            age = int(input("what is your age? "))
            10/age
        except ValueError:
            print("please enter a number")
        except ZeroDivisionError: 
            print("please enter age higher than 0")
        else:
            print("thank you!")
            break
       
Error Handling I

    Imagine you are writing a basic function, such as a custom sum function:
    
        def sum(num1, num2):
            try:
                return num1 + num2
            except TypeError as err:
                print("please enter numbers " + err)
                
        print(sum(1, '2'))
                
     Exception handling in this situation allows for the user to be displayed what exactly went wrong with their program. The output would result 
     in the error message "please enter numbers" as well as the actual error message displayed in the console. You can also handle multiple errors
     in an except statement:
     
     
        def sum(num1, num2):
            try:
                return num1 + num2
            except (TypeError, ZeroDivision) as err:
                print(err)
                

Error Handling II

    There is one last branch of the try except, that being the finally statement:
    
        while True:
        try:
            age = int(input("what is your age? "))
            10/age
        except ValueError:
            print("please enter a number")
            continue
        except ZeroDivisionError: 
            print("please enter age higher than 0")
            break
        else:
            print("thank you!")
            break
        finally:
            print("ok, I am finally done")
            
     This is useful because after all these attempts for appropriate input, we may want to keep track of the fact that something is attempting
     to break our program. You may notice the continue and break keywords, this is based on the severity of the error. For value errors, we want
     to continue and allow the user to enter another input. With the zero division error, we've told the loop to break.
     
Error Handling III

    Sometimes, there are errors and exceptions that are so severe that we want our program to stop outright. In that case, we can choose to use
    the except block, or we can use the 'raise' keyword, in conjuction with an error type, and a message:
      
      while True:
        try:
            age = int(input("what is your age? "))
            10/age
            raise Exception("hey cut it out")
        except ZeroDivisionError: 
            print("please enter age higher than 0")
            break
        else:
            print("thank you!")
            break
        finally:
            print("ok, I am finally done")
            
     In this version of our while loop, we've instructed our program to throw an error if there is an exception and print "hey cut it out" in the
     console as an error message.
    
For more information on try and except:
https://www.w3schools.com/python/python_try_except.asp
    
