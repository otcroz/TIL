## 깃허브 기본 문법 공부하기
#### 깃허브 기본 3원칙: add, commit, push
```
$ git add 파일이름 또는 폴더
$ git commit -m "메시지 내용"
$ git push 
```

#### 중앙저장소 복제하기
```
$ git clone 저장소.git
```

#### 깃의 상태 확인하기
현재 나의 위치 확인(main, branch 등) 
```
$ git status
```

### 깃 충돌 해결하기

```
$ git pull --rebase origin master(main)
```
```-rebase``` 옵션: 중앙 저장소의 커밋 이력을 사용자 커밋 이력 앞에 끼워 놓음<br>
- 불필요한 병합 커밋을 한 번 더 하는 번거로움 → ```--rebase``` 옵션 사용
- master(main) 브랜치에 하나하나 대입과 대조를 하며 커밋 이력 재배열, 경우에 따라 버그 발견


### 브랜치로 만들기
```
$ git checkout -b 브랜치 이름 master/main(최상위 브랜치)
$ git push -u origin 브랜치 이름

```
```
$ git branch 브랜치 이름
$ git push -u origin 브랜치 이름
```
