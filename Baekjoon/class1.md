```
list1 = []
list2 = []
inputList = []

num = int(input())

for i in range(0, num):
    inputNum = input()
    inputList = inputNum.split(" ")
    
    list1.append(int(inputList[0]))
    
    list2.append(int(inputList[1]))

for i in range(0, num):
    print(list1[i] + list2[i])
```
```
list1 = []

for i in range(0,9):
    n = int(input())
    list1.append(n)

max = list1[0]
maxIndex = 0
for i in range(0,9):
    if(max < list1[i]):
        max = list1[i]
        maxIndex = i

print(max)
print(maxIndex+1)
```
```
list1 = []
n = int(input())
sum = 0

inputNum = input()
list1 = inputNum.split(" ")

for i in range(0,n):
    sum += int(list[i])

avg = sum / n
print("%f" % avg)
```
```
list1 = []
list2 = []

count=0
while True:
    try:
        a, b = input().split(" ")
        list1.append(int(a))
        list2.append(int(b))
        count+=1
    except:
        break

for i in range(0,count):    
    print(list1[i] + list2[i])
```
```
num = int(input())
sum = 0

list1 = input()

for i in range(0, num):
    sum += int(list1[i])

print(sum)
```
```
list1 = []
list2 = []

while True:
    a, b = input().split(" ")

    if int(a) == 0 & int(b) == 0:
        break

    list1.append(int(a))
    list2.append(int(b))

for i in range(0, len(list1)):
    print(list1[i] + list2[i])
```
```
num = int(input())

for i in range(0, num):
    for k in range(0, i + 1):
        print("*", end="")
    print()
```
```
num = int(input())

for i in range(1, 10):
    print("%d * %d = %d" % (num, i, num * i))
```
```
num = int(input())
for i in range(1, num + 1):
    print(i)
```
```
num = int(input())
for i in range(num, 0, -1):
    print(i)
```

```
n = ord(input())
print(ord(chr(n)))
```
```
num = int(input())

nums = input().split(" ")

maxIndex = 0
minIndex = 0
for i in range(0, num):
    if int(nums[maxIndex]) < int(nums[i]):
        maxIndex = i
    if int(nums[minIndex]) > int(nums[i]):
        minIndex = i

print(int(nums[minIndex]), int(nums[maxIndex]))
```
```
a, b = input().split(" ")
aa = int(a)
bb = int(b)
print(aa + bb)
print(aa - bb)
print(aa * bb)
print(int(aa / bb))
print(aa % bb)
```
```
music = []

music = list(map(int, input().split(" ")))


if music == sorted(music):
    print("ascending")
elif music == sorted(music, reverse=True):
    print("descending")
else:
    print("mixed")
```

```
a, b = input().split(" ")
print(int(a) / int(b))
```
```
repeat = []
list1 = []

t = int(input())
for i in range(0, t):
    inputStr = input().split(" ")
    repeat.append(int(inputStr[0]))
    list1.append(inputStr[1])

for i in range(0, t):
    for k in range(0, repeat[i]):
        for j in range(0, len(list1[i])):
            print(list1[i][j], end="")
```
