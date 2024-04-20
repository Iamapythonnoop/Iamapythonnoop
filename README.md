# sussy machine to solve sudoku( I haven't finished it yet but 90 % of it.)


import numpy as np

a = []
for i in range(9):
    x = list(map(int,input().split(" ")))
    a.append(x)

def Valid(row,column,number):
    global a
    for i in range(len(a)):
        if a[row][i] == number:
            return False
    
    for i in range(len(a)):
        if a[i][column] == number:
            return False
    
    x = (row // 3) * 3
    y = (column // 3) * 3
    
    for i in range(0,3):
        for j in range(0,3):
            if a[x+i][y+j] == number:
                return False
    return True
def Solve():
    global a
    for row in range(len(a)):
        for column in range(len(a)):
            if a[row][column] == 0:
                for number in range(1,10):
                    if Valid(row,column,number):
                        a[row][column] = number
                        Solve()
                        a[row][column] = 0
                return
    print(np.matrix(a))
    b = input("more")
    if b == "N":
        return
    return
Solve()

<!---
Iamapythonnoop/Iamapythonnoop is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
