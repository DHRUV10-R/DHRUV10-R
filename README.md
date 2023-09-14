PYTHON PROGRAMMING 

1.

# program to illustrate the use of exception handling
numerator=(int)(input("ENTER INTEGER NUMBER "))
denominator=(int)(input("ENTER INTEGER NUMBER "))
try:
    result=numerator/denominator
    print(numerator,"/",denominator,"is",result)
except:
    print("ERROR:  DENOMINATOR CANNOT BE 0.")

2.

#program to illustrate the use of raise exception
try:
    x=int(input('ENTER NUMBER UPTO 100:'))
    if x>100:
          raise ValueError(x)
except ValueError:
    print(x,"is out of allowed range")
else:
    print(x,"is within the allowed range")

3.

#Catching specific exceptions
try:
    a=int(input("ENTER VALUE OF a:"))
    b=int(input("ENTER VALUE OF b:"))
    c=a/b
    print("THE ANSWER OF DIVIDE BY b: ",c)
except ValueError:
    print("ENTERED VALUE IS WRONG")
except ZeroDivisionError:
    print("CAN'T DIVIDE BY ZERO")

4.

#Program to illustrate the use of exception
def simple_interest(amount,year,rate):
    try:
        if rate>100:
            raise ValueError(rate)
        interest=(amount*year*rate)/100
        print('THE SIMPLE INTEREST IS',interest)
        return interest
    except ValueError:
        print('INTEREST RATE IS OUT OF RANGE',rate)

print('Case 1')
simple_interest(800,6,8)
print('Case 2')
simple_interest(800,6,800)

5.

import mysql.connector

con=mysql.connector.connect (host='localhost', database='student35_fycs', user='root', password='123456')

if con.is_connected():
    print("Connection establised")
else:
     print("Connection failed")

cur=con.cursor()

cur.execute("select * from studinfo")

data=cur.fetchone ()
print(data)

print("Total Rows retrieved:", cur.rowcount)

data=cur.fetchmany (4) 
for row in data:
    print(row)

print("Total Rows retrieved:", cur.rowcount)

con.close()

6.

from datetime import datetime
timestamp=15468754216
date_time=datetime.fromtimestamp(timestamp)
print("Date time object: ",date_time)
d=date_time.strftime("%H:%M:%S")
print("Output2: ",d)
d=date_time.strftime("%d%b%Y")
print("Output3: ",d)
d=date_time.strftime("%d%B%Y")
print("Output4: ",d)
d=date_time.strftime("%I%p")
print("Output5: ",d)

#strftime
from datetime import datetime
now=datetime.now()
year=now.strftime("%Y")
print("Year: ",year)
month=now.strftime("%m")
print("Month: ",month)
day=now.strftime("%d")
print("Day: ",day)
time=now.strftime("%H:%M:%S")
print("Time: ",time)
date_time=now.strftime("%m/%d/%Y,%H:%M:%S")
print("date_time: ",date_time)

7.

#program to synchronization by using lock
from threading import*
import time
l=Lock()
def wish(name,age):
    for i in range(3):
        l.acquire()
        print("Hi",name)
        time.sleep(2)
        print("Your age is",age)
        l.release()
t1=Thread(target=wish, args=("Dhruv","18"))
t2=Thread(target=wish, args=("Sahil","18"))
t1.start()
t2.start()          

8.

#Creating thread using thread module
import _thread    #import thread module
import time      #import time module
def cal_square(num):  #define
    print(" Calculate the square root of the given number")
    for n in num:
       time.sleep(0.3)      #iteration it waits for 0.3 times
       print('Square is : ',n *n)
def cal_cube(num):
    print(" Calculate the cube of the given number")
    for n in num:
       time.sleep(0.3)      #iteration it waits for 0.3 times
       print('Square is : ',n *n*n)
arr=[4,5,6,7,2]
t1=time.time()
cal_square(arr)
cal_cube(arr)
print("Total time taken by threads is: ",time.time()-t1)

9.

#program to run writing string
myfile=open("D:\\adv python\\name2.txt","a")
ans='y'
while ans=='y':
    bno=int(input("enter book number "))
    bname=input("enter book name  ")
    author=input("enter author name ")
    price=int(input("enter book price "))
    brec=str(bno)+","+bname+","+author+","+str(price)+"\n"
    myfile.write(brec)
    ans=input("add more ?")
myfile.close()

10.

#program to display using append mode
myfile=open("D:\\adv python\\write1.txt","a")
for i in range(3):
    name= input("Enter name to store :")
    myfile.write(name)
    myfile.write('\n')
myfile.close()
print("\nData saved successfully...")

11.

