- git 프로그램을 운영체제에 맞게 다운로드한 후 이용.

깃 초기세팅
--------------------

```git
git config --global user.name "자기이름"

git config --global user.email "자기 깃허브 이메일"

git config --list
-> user.name, user.email만 잘 들어갔는지 확인 
```

깃 프로젝트 올리기 [ 최초 ]
-----------------------------

```git
git init
// git 저장소 생성

git add .
// 어떤 파일을 추가할 지 추려본다.

git status
// 상태를 알려줌 [ 필수는 아니다 ]

git commit -m "first commit"
// 히스토리를 만든다. ( 최종, 진짜최종, 진짜최종최종.... )

git remote add origin [깃허브저장소 주소]
// 해당 원격 레포지토리와 연결하겠다.

git remote -v
// 연결이 됐는지 확인한다.

git push origin [브랜치명]
// 특정 브랜치로 코드를 보낸다. [ 최초에는 브랜치명이 master이다. ]

```

깃 프로젝트 올리기 [ 추가 시 ]
------------------------------

```git
git add [파일]
// 올리고 싶은 파일을 add 한다.

git status
// add 된 상태를 확인

git commit -m "커밋 메세지"
// 히스토리를 만든다.

git push origin [브랜치명]
// 브랜치로 코드를 보낸다.
```

협업에서의 깃허브
-----------------------------

```git
git clone "회사 프로젝트 url" "폴더명"
// 회사의 프로젝트를 내 컴퓨터로 내려받는다.

작업을 한다.

git checkout -b "브랜치명"
// 신입을 위한 별도의 브랜치로 이동한다.

git push origin freshman
// 별도의 브랜치에 올려준다.

웹사이트로 돌아오면 had recent pushes less than ~ 생긴다.
신입사원은 compare and pull request를 누른다.
작성 후 create pull request를 누른다. ( Pull Request : 마스터로 갈 수 있게 허락해주세요 ㅠㅠ )

담당자가 Pull request를 확인하고 괜찮으면 Merge pull request를 누른다,
[ 해당 버튼에는 큰 책임이 누른다. 누르면 프로젝트에 합쳐짐... ]
[ 보라색이 나오면 merge 된 것임 ]

누군가 merge하고 나면 메인의 코드가 달라지게 된다.

동기화를 시켜야 하는데, 여태까지 해 둔 코드를 저장해야 한다.
git add [파일]

git commit -m "커밋 메세지"

이 상태에서 push는 안하고

git pull origin master [ 메인 브랜치로부터 코드를 받아온다. ] 
```
