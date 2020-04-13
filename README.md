# gpCalc

# POLY GP CALCULATOR CODE

import time

def slow(x):
    """This is a function that helps delay the
    program execution.
    usage: slow(_x_)
    _x_ = ___the lenght of time in seconds"""
    time.sleep(x)
    pass

#------START----------

print('\t\t GP CALC (WELCOME...)')

slow(1)

noc = int(input('PLEASE INPUT THE NUMBER OF COURSES OFFERED: '))

numberOfCourse = list(range(noc))

#-----EMPTY LIST FOR CREDIT LOAD (cl) AND GRADE (gd)-------

cl = []

gd = []

#-----EMPTY LIST FOR MULTIPLICATION OF BOTH cl AND gd (multCL_GD)--------

multCL_GD = []

for loop in numberOfCourse:
    #------INPUTS (BOTH CREDIT LOAD AND GRADE)---------
    print('COURSE {0}: '.format(loop + 1))
    creditLoad = int(input('CREDIT LOAD: '))
    grade = input('GRADE: ')
    if grade == 'a' or grade == 'A':
        grade = 4.00
    elif grade == 'ab' or grade == 'AB':
        grade = 3.50
    elif grade == 'b' or grade == 'B':
        grade = 3.25
    elif grade == 'bc' or grade == 'BC':
        grade = 3.00
    elif grade == 'c' or grade == 'C':
        grade = 2.75
    elif grade == 'cd' or grade == 'CD':
        grade = 2.50
    elif grade == 'd' or grade == 'D':
        grade = 2.25
    elif grade == 'p' or grade == 'P':
        grade = 2.00
    elif grade == 'f3' or grade == 'F3':
        grade = 1.75
    elif grade == 'f2' or grade == 'F2':
        grade = 1.50
    elif grade == 'f1' or grade == 'F1':
        grade = 1.00
    elif grade == 'f0' or grade == 'F0':
        grade = 0.5
    else:
        grade = 0
        print('ERROR/WRONG INPUT')
    #-----APPEND INPUTS TO VARIOUS EMPTY LIST-----
    cl.append(creditLoad)
    gd.append(grade)
    multCL_GD.append(creditLoad * grade)
    pass

#-------DELAY----------

for a in range(3):
    print('.', end=' ')
    slow(1)
    pass

#------CALCULATIONS---------

totalCreditLoad = sum(cl)

print('\nTOTAL CREDIT LOAD: {0}'.format(totalCreditLoad))

totalGradePoint = sum(gd)

totalMultCL_GD = sum(multCL_GD)

GP = totalMultCL_GD / totalCreditLoad

slow(1)

#-----FINAL RESULT------

print("SEMESTER GP = {0}".format(round(GP,2)))

if GP >= 3.50:
    print('===========')
    print('DISTINCTION')
    print('===========')
elif GP >= 3.00:
    print('------------')
    print('UPPER CREDIT')
    print('------------')
elif GP >= 2.50:
    print('------------')
    print('LOWER CREDIT')
    print('------------')
elif GP >= 2.00:
    print('....')
    print('PASS')
    print('....')
else:
    print('****')
    print('FAIL')
    print('****')
