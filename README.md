# 깃 사용법

---
```plaintext
기본적으로 깃을 사용할때는 
vscode를 열고 
vscode내부 터미널을 사용하여 깃을 사용함이 현재 사용하고 있는 
데이터를 기록하고 추가적인 작업을 하는데 효율적이다.
(버전관리)


명령등

git init --  1 버전 관리를 하겠다고 선언함.
git config --global core.autocrlf true   --윈도우는 true
				--Mac 은 input 이라고 써야함.

git config --global user.name 'Jhfruit7353'
git config --global user.email 'Jhfruit7353@gmail.com'
git config --global --list

user.name=Jhfruit7353
user.email=jhfruit7353@gmail.com
core.autocrlf=true
위와 같이 나옴.


=====================================
```
# git clone으로 vscode열기


터미널에서 바탕화면으로 이동.
C://....../Desktop/ 에서 또는 다음 폴더 안에들어가서

git clone 나의 github repositories 주소 기입

데이터 로딩중...

완료되면 

code . 엔터 ---vscode가 새창으로 열림.

code . -r    -- 현재 있는창의 프로젝트를 새창으로 연다.



git status     현재 작업한 내용의 관리 상태. 프로젝트 구조가 확인됨.

git add .

git status    ---add를 하고 status를 하면 프로젝트 색이 녹색으로 변함.
초록색으로 색이 변하면 이제부터 git에서 버전 관리 하겠다는 의미.


git commit -m 'Start project'       -이름은 시작이니ㅏ start라고 한것임.

==commit같은 경우 버전을생성 추가하는 요소임.

추가한 버전을 확인하려면 
git log 하면됨.



---

# 이제 깃허브에 내가 작성한 프로젝틀를 공유하게 만드는 작업.

```plaintext
git-hub 에 우측 상단 

your repositories 클릭

new로 저장소 만들기

Repositories name에 이름 작성

추가로 다른부분들은 건드릴것은 없다.
일반적으론 공개 저장소
중요한 내용은 private저장소로 저장.

저장소를 만들고 만들어진 저장소의 주소 복사

터미널로 돌아와서 

 원격저장소로 연결(git-hub에서 저장소하나 생성해야함.)
git remote add origin https://github.com/Jhfruit7353/starbucks.git

위의 의미는 remote - 원격저장소
origin - 저장소 이름을 origin이라는 이름으로 저장.하고 뒤에 저장소 주소 작성함.

그럼 git-hub에 인증하라는 문구가 브라우저로 뜸.
인증완료하고 

git push origin master 
하면 
Everything up-to-date<==============이런 문구 뜨면 업로드 완료됨.



---
수정후 업로드

git status

git add .
git status 

git commit -m '뱃지 이미지 수정'

git log

--------------------------------------------------------------------
commit 1921952be354c13e16eeea11ac5e2c1e535cfc1c (HEAD -> master)
Author: faceman7353@gmail.com <faceman7353@gmail.com>
Date:   Fri Mar 18 17:05:23 2022 +0900

    뱃지 이미지 수정

commit 575bc24b03b5bc375d95e2f8e4fd6b33b850fc0c (origin/master)
Author: faceman7353@gmail.com <faceman7353@gmail.com>
Date:   Fri Mar 18 16:21:01 2022 +0900
---
 수정후 git log 사용하면 위와 같이 나옴.


commit 1921952be354c13e16eeea11ac5e2c1e535cfc1c (HEAD -> master)
==> HEAD 라고 써있는 부분이 최신버전을뜻함.

그리고 이렇게 수정후 버전을 git hub에 업로드 해야하는데 
버전을 생성할때마다 push를 할필요는 없다.
이때 사용하는 것이 markdown

index.html 주변에
README.md 라는 파일만듬.


=======================================
master - 하나의 줄기이다.

branch 확인
git branch

PS C:\Users\jhfru\Desktop\tmp> git branch -a
* master
  remotes/origin/master
  -->원격저장소에 있는 브렌치까지 확인 가능 -a 사용


PS C:\Users\jhfru\Desktop\tmp> git branch signin  --브랜치 signin이라는 브랜치 개설

PS C:\Users\jhfru\Desktop\tmp> git branch
* master
  signin

PS C:\Users\jhfru\Desktop\tmp> git checkout signin
Switched to branch 'signin'
====>이것은 브랜치가 master -> signin으로 환경이 바뀐것임.

여기서 index.html주변에 signin이라는 폴더 하나 생성
signin폴더 안에 index.html파일 생성

그리고 파일을 작성하기전 git에 signin이라는 변경사항을 먼저 추가 해주어야한다.

git status
git add .
git status 

git commit -m '로그인 페이지 시작하기'

여기서 master라는 브랜치와 
signin이라는 브랜치는 각각 다른 브랜치이기때문에 
signin에서 내용을 마무리 하면 
master와 병합을 시켜야함.
그 전까지는 master와는 연결이 안되있기때문에 수정사항이 적용되지 않음.


작업하던 프로젝트를 git저장소에 올릴때
git push origin 브랜치 이름
                     master
                     signin   등 맞는 이름을 넣어야함.


==========================================
commit 6d44bd2107fc7e2d203ded84afe13f00308ebf93 (HEAD -> master)
Author: faceman7353@gmail.com <faceman7353@gmail.com>
Date:   Sat Mar 19 09:38:12 2022 +0900

    3

commit ad121df725db42624ded5b7722d2cc29a1337fb6
Author: faceman7353@gmail.com <faceman7353@gmail.com>
Date:   Sat Mar 19 09:37:41 2022 +0900

    2

commit 4d1ed4b343038887dc7e284bd78ef130fe49f713
Author: faceman7353@gmail.com <faceman7353@gmail.com>
Date:   Sat Mar 19 09:37:12 2022 +0900

   1

위 작업을 통해 1,2,3 의 내용이있는 버전이있고  3이라는 버전이 최신 버전,
그런데 만약 2라는 버전으로 돌아가고싶을때 

git reset --hard HEAD~1

PS C:\Users\jhfru\Desktop\git-practice> git reset --hard HEAD~1  
HEAD is now at ad121df 2 

위와 같이 나오면서 버전이 2로 바뀜.


그런데 다시 원래 전버전으로 다시 돌아가고 싶을때는 한번은 다시 돌아갈수있다.
(다른 입력사항이 없을시.)

git reset --hard ORIG_HEAD   ---다시 전버전으로 돌아가는 내용.



==============================================

브랜치 생성

git branch 생성할 브랜치 이름/
ex) git branch purple

git branch
-->PS C:\Users\jhfru\Desktop\git-practice> git branch
* master
  purple

purple이라는 브랜치로 이동

git checkout purple.


브랜치 삭제

git branch -d 삭제할 브랜치 이름
> git branch -D purple 과같이 하면됨.

브랜치 생성과 동시에 이동하는 방법.
>git checkout -b yellow
===========================================

원격저장소에 있는 내용을 가져와서 작업하는 방법

pull
-> 원격저장소에서  local저장소로 당겨옴.
>git pull origin master
push
-> local저장소에서 원격저장소로 밀어냄.
>git push origin master



===========================================
원격 저장소로 연결

> git remote add origin https://github.com/faceman7353/git-practice.

원격저장소에 내용 업로드

> git push origin master    (master 는 현재 업로드될 내용의 브랜치)


==============================================
git error

https://somjang.tistory.com/entry/Git-rejected-master-master-non-fast-forward-%ED%95%B4%EA%B2%B0-%EB%B0%A9%EB%B2%95
============================================

```
