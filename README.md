# Multiple server with infinite capacity - (M/M/c):(oo/FIFO)
## Aim :
To find (a) average number of materials in the system (b) average number of materials in the conveyor (c) waiting time of each material in the system (d) waiting time of each material in the conveyor, if the arrival  of materials follow poisson process with the mean interval time 10 seconds, serivice time of two lathe machine follow exponential distribution with mean serice time 1 second and average service time of robot is 7seconds.
## Software required :
Visual components and Python
## Theory:
Queuing are the most frequently encountered problems in everyday life. For example, queue at a cafeteria, library, bank, etc. Common to all of these cases are the arrivals of objects requiring service and the attendant delays when the service mechanism is busy. Waiting lines cannot be eliminated completely, but suitable techniques can be used to reduce the waiting time of an object in the system. A long waiting line may result in loss of customers to an organization. Waiting time can be reduced by providing additional service facilities, but it may result in an increase in the idle time of the service mechanism.
![image](https://github.com/harshi1111/Muttiple-capacity-with-infinite-capacity/assets/84671735/e10c0989-f479-4998-8ff7-1f4e3e07456a)
## Procedure :
Thus the average number of materials in the system and conveyor, waiting time of each material in the system and conveyor is found successfully.
## Experiment:
![image](https://github.com/harshi1111/Muttiple-capacity-with-infinite-capacity/assets/84671735/55afa820-5ebe-45f6-a680-1b3466dd3742)
![image](https://github.com/harshi1111/Muttiple-capacity-with-infinite-capacity/assets/84671735/42083e83-e37c-4673-860c-21530cec1f50)
## Program :
```
DEVOLOPED BY : HARSHITHA V
REGISTER NO  : 23002305
```
```
import math
arr_time=float(input("Enter the mean inter arrival time of objects from Feeder (in secs): "))
ser_time=float(input("Enter the mean  inter service time of Lathe Machine (in secs) :  "))
Robot_time=float(input("Enter the Additional time taken for the Robot (in secs) :  "))
c=int(input("Number of service centre :  "))
lam=1/arr_time
mu=1/(ser_time+Robot_time)
print("--------------------------------------------------------------")
print("Multiple Server with Infinite Capacity - (M/M/c):(oo/FIFO)")
print("--------------------------------------------------------------")
print("The mean arrival rate per second : %0.2f "%lam)
print("The mean service rate per second : %0.2f "%mu)
rho=lam/(c*mu)
sum=(lam/mu)**c*(1/(1-rho))/math.factorial(c)
for i in range(0,c):
    sum=sum+(lam/mu)**i/math.factorial(i)
P0=1/sum
if (rho<1):
    Lq=(P0/math.factorial(c))*(1/c)*(lam/mu)**(c+1)/(1-rho)**2
    Ls=Lq+lam/mu
    Ws=Ls/lam
    Wq=Lq/lam
    print("Average number of objects in the system : %0.2f "%Ls)
    print("Average number of objects in the conveyor :  %0.2f "%Lq)
    print("Average waiting time of an object in the system : %0.2f secs"%Ws)
    print("Average waiting time of an object in the conveyor : %0.2f secs"%Wq)
    print("Probability that the system is busy : %0.2f "%(rho))
    print("Probability that the system is empty : %0.2f "%(1-rho))
else:
    print("Warning! Objects Over flow will happen in the conveyor")
print("--------------------------------------------------------------")
```
## Output :
![image](https://github.com/harshi1111/Muttiple-capacity-with-infinite-capacity/assets/84671735/d19aae80-b821-4db2-aa74-66f9bf41b891)
## Result : 
Thus the average number of materials in the system and conveyor, waiting time of each material in the system and conveyor is found successfully.
