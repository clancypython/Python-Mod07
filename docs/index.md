#Assignment 07
**Dev:** *Cheng Ka Ho*
**Date** *24 May 2023*


'''
# ---------------------------------------------------------------------------- #
# Title: Assignment 06
# Description: Pickling and Error Handing within Python
# ChangeLog (Who,When,What):
# RRoot,1.1.2030,Created started script
# Cheng Ka Ho, 16 May 2023,Added code to complete assignment 6
# ------------------------------------- #

import pickle  # Imports code from another code file

# Data -------------------------------------------- #
strAppData = 'AppData.dat'
lstToDo = []

# Processing -------------------------------------- #
def save_data_to_file(file_name, list_of_data):
    """ Saves string data to a file

     :param data: (string) with data to save
     :param file_name: (string) with name of file
     :return: nothing
     """
    file = open(file_name, "ab")
    pickle.dump(list_of_data, file)
    file.close()

def read_data_from_file(file_name):
    """ Reads rows of data from a file into a list

        :param file_name: (string) with name of file
        :return: (list) with rows of data read from the file
        """
    file = open(file_name, "rb")
    list_of_data = pickle.load(file)
    file.close()
    return list_of_data

# Presentation ------------------------------------ #
# Request a Number, Task, and Priority from user, then store it in a list object
strName = str(input("Enter your Name: ")).strip()
intID = str(input("Enter your ID "))

try:
    intID = int(intID)
    print(intID)
# except ValueError:  # Ensure the user inputs an integer
#     print("Please enter an integer")
except Exception as e:  # Other errors that would occur at this step
    print("ID is NOT a number")
    print("Details as below:")
    print(e.__doc__)
    print(e.__str__())

lstToDo = [strName, intID]

save_data_to_file(strAppData, lstToDo)

print(read_data_from_file(strAppData))



'''

