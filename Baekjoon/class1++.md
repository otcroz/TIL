```
repeat = []
strList = []

limit = int(input())

# 2차원 배열
for i in range(0, limit):
    inputNum, inputStr = input().split(" ")  # 숫자, 문자열 넣고
    repeat.append(int(inputNum))  # 숫자 리스트에
    strList.append(inputStr)  # 문자열 리스트에

# 전체 반복 횟수
for i in range(0, limit):
    # 각 문자열 repeat
    for j in range(0, len(strList[i])):
        # 문자열의 수만큼 repeat
        for k in range(0, repeat[i]):
            print(strList[i][j], end="")
    print()
```
```
test = ""
testCase = []
previous = ""
score = 0
sum = 0

limit = int(input())

for i in range(0, limit):
    test = input()
    testCase.append(test)

for i in range(0, limit):
    for k in range(0, len(testCase[i])):
        # 처음
        if k == 0:
            if testCase[i][0] == "O":
                score += 1
                sum += score
        # 처음이 아닐 때
        else:
            if testCase[i][k] == "O":
                if previous == "O":
                    score += 1
                else:
                    score = 1
                sum += score
            else:
                score = 0
        previous = testCase[i][k]
    print(sum)
    sum = 0
    score = 0
```
```
inputStr = []
text = ""

text = input().strip()
inputStr = text.split()

print(len(inputStr))
```
##### strip() 와 strip(" ")의 차이
- strip()는 공백을 제외하고 문자열을 나눈다.
- strip(" ")는 공백도 문자열로 취급하여 문자열을 나눈다.

```
print("\    /\\")
print(" )  ( ')")
print("(  /  )")
print(" \(__)|")
```
```
print("|\_/|")
print("|q p|   /}")
print("( 0 )\"\"\"\\")
print("|\"^\"`    |")
print("||_/=\\\\__|")
```
```
nums = []
mul = 1
res = [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

for i in range(0, 3):
    num = int(input())
    nums.append(num)
    mul *= nums[i]

strSum = str(mul)

for i in range(0, len(strSum)):
    if strSum[i] == "0":
        res[0] += 1
    elif strSum[i] == "1":
        res[1] += 1
    elif strSum[i] == "2":
        res[2] += 1
    elif strSum[i] == "3":
        res[3] += 1
    elif strSum[i] == "4":
        res[4] += 1
    elif strSum[i] == "5":
        res[5] += 1
    elif strSum[i] == "6":
        res[6] += 1
    elif strSum[i] == "7":
        res[7] += 1
    elif strSum[i] == "8":
        res[8] += 1
    elif strSum[i] == "9":
        res[9] += 1

for i in range(0, len(res)):
    print(res[i])
```
```
inputNums = []
res = []
count = 0

for i in range(0, 10):  # 값 입력받기
    num = int(input())
    inputNums.append(num)

for i in range(0, 10):  # 42로 나누기
    mod = inputNums[i] % 42
    res.append(mod)

# 다른 나머지의 수 찾기
res.sort()

for i in range(0, 9):
    if res[i] != res[i + 1]:
        count += 1

count += 1
print(count)
```
```
limit, num = map(int, input().split())
list1 = list(map(int, input().split()))

for i in range(0, limit):
    if list1[i] < num:
        print(list1[i], end=" ")
```
``` 
inputStr = input().upper()
uniqueStr = list(set(inputStr))

countList = []
for i in uniqueStr:
    count = inputStr.count(i)
    countList.append(count)

if countList.count(max(countList)) > 1:
    print('?')
else:
    maxIndex = countList.index(max(countList))
    print(uniqueStr[maxIndex])
```
```
# 숫자 입력
n1, n2 = input().split()
# 숫자 거꾸로
rev_n1 = n1[::-1]
rev_n2 = n2[::-1]
# 큰 거 고르기
if int(rev_n1) < int(rev_n2):
    print(rev_n2)
else:
    print(rev_n1)
```
```
year = int(input())

if (year % 4 == 0 and year % 100 != 0) or (year % 400 == 0):
    print(1)
else:
    print(0) 

```
```
alphabet = []

for i in range(0, 26):
    alphabet.append(-1)

word = input()

for i in range(0, len(word)):
    index = int(ord(word[i])) - 97
    if alphabet[index] != -1:  # 이미 알파벳 존재하면 break
        continue
    alphabet[index] = i

for i in range(0, 26):
    print(alphabet[i])
```
```
hour, min = map(int, input().split())

# 분 구분하기
if min - 45 < 0:
    min = min + 60 - 45
    if hour == 0:
        hour = 23
    else:
        hour -= 1
else:
    min -= 45

print(hour, min)
```
```
num = int(input())

for i in range(0, num):
    for k in range(0, num - 1 - i):
        print(" ", end="")
    for k in range(0, i + 1):
        print("*", end="")
    print()
```
```
num = int(input())
score = list(map(int, input().split()))

# 점수 중 최댓값
max = 0
for i in range(0, len(score)):
    if score[max] < score[i]:
        max = i

res = []
# 각 점수에 점수/최댓값*100
for i in range(0, len(score)):
    res.append(score[i] / score[max] * 100)

# 평균
avg = sum(res) / len(res)
print(avg)
```
