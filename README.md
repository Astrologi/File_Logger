# File_Logger
# Assignment 10
# Author: Jonathan Hilton
# 11/08/2020


import os

# Greet user
print("Welcome to File Logger!")

# receive input for directory
userDirectory = input("Please enter the directory: ")

# receive input for .txt file name
userFile = input("Please enter the text file name: ")

# receive user's name
userName = input("Please enter your name: ")

# receive user's address
userAddress = input("Please put in your street address: ")

# receive user's phone number
userPNumber = input("Please enter your phone number: ")

# combine the user's name, address and phone number into a comma separated list
userInfo = (userName + ", " + userAddress + ", " + userPNumber)

# combine user's directory and file path into a string
userPath = (userDirectory+userFile)

# create empty string to change integer and string inputs
userString = ""

# change inputs from user that were combined into list into a string
for ele in userInfo:

    userString += ele

# check directory validity and prompt user
if os.path.isdir(userDirectory):

    print("Directory Exists")

# check path validity and prompt user
if os.path.exists(userPath):

    print("Complete path exists")

# open file and write user inputs into file
with open(userPath, 'w') as fileHandle:

    fileHandle.write(userString)

# open file and read user inputs back to terminal
with open(userPath, "r") as fileHandle:
    file_info = fileHandle.read()

    print("The following info has been saved to " + userPath)
    print(file_info)

# prompt user to hit enter to exit
exit_ = input("Press 'enter' to exit...")

# exit and close the file after user hits enter
if exit_ == "":

    print("Thank you for using File Logger!")

    fileHandle.close()
