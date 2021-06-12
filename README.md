# 8thjune2021_devops

# day3
# task
import subprocess
import os
import platform
from getmac import get_mac_address as y1
from datetime import datetime
from psutil import virtual_memory
user_input='''
Press 1 to Check current Time and Date :- 
Press 2 to Check RAM Size of Your current OS  :- 
Press 3 to Know Name of Your current OS :- 
Press 4 to Check What is MAC Address of Your laptop/PC/VM/CloudVM :- 
Press 5 to create one directory in your Desktop :- 
Press 6 to Restart Your current OS :- 
Press 7 to Print list of all available Wifi in your laptop Range :-
Press 8 to Run another code in Your current folder  :-  
'''
print(user_input)          #print data for user
user_choice=input()        #Taking input from user
print("You entered = ",user_choice)


if user_choice == '1' :
    # datetime object containing current date and time
    x = datetime.now()
    print("Date and Time = ", x)

elif user_choice == '2' :
    y = virtual_memory()
    x = y.total
    print("Size of RAM is :", x)

elif user_choice == '3' :
    x= os.name
    print("Your OS name is : ", x)

elif user_choice == '4' :
    x= y1()
    print("Your Mac address is : ",x)

elif user_choice == '5' :
    print("Enter name for folder") 
    z=input()
    os.chdir(r"C:\Users\vinay\Desktop")   #Change vinay according to your user name
    os.makedirs(z)
    print("New DIR created")

elif user_choice == '6' :
    os.system("shutdown /r")

elif user_choice == '7' :
    x = subprocess.check_output(['netsh','wlan','show','network'])
    x = x.decode('ascii')
    x = x.replace("\r","")
    print("Available Wifi are : " , x)

elif user_choice == '8' :
    import task1day1

else :
    print("Not a valid input")
   
