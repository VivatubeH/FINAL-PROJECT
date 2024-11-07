1. 깃허브 원격 레포지토리 만들기 ( 팀 리더의 역할 )

2. 팀원 초대하기 [ 멤버들을 초대한다. ]

3. 프로젝트를 초기세팅하고 원격 레포지토리에 올려준다. [ 로컬에서 만들어준다. ]
```git
git init

git add [추가하고싶은파일]

git commit -m "첫 커밋 메세지"

git remote add origin "원격저장소 링크"

git push origin master
// 최초에는 master 브랜치 [ master에는 완벽한 코드만 올린다. 유저가 사용하는 코드 ]
```

4. 브랜치의 복사본을 만든다. develop이라는 [ 개발자가 사용할 연습장 ]
```git
git checkout -b develop
// develop 브랜치 생성 [ master에서 checkout 했으니 완전히 같은 버전 ]

git push --set-upstream origin develop
// 로컬에서 만든 develop을 원격 repo에 올린다.
```

5. master와 develop 브랜치로 브랜치가 2개 존재하는지 확인한다.

6. master 브랜치를 잠군다. ( 보호한다. )
- 원격 github에서 protect this bracnch를 누른다.
```
lock branch [ 개개인이 git push를 못하도록 lock branch를 한다. ]
require a pull request before merging [ merging 전에 pull request를 필수로 한다. ]
```

7. 깃허브에서 Projects -> Link a project -> create new project [ 추천은 board 타입 ]
```
각자 해야할 일을 관리하기 좋다.
[ Todo: 해야할 일, In Progress : 하고 있는 일, Done : 끝난 일 ]

Add item으로 추가하고 나면 assign을 할 수 있다. [ 팀원의 상태 확인 가능 ]
convert to issue하면 이슈 등록창이 열린다.

해당 이슈로부터 브랜치를 만들 수 있다.
브랜치명은 스스로 정하고 change branch source로 master가 아닌 develop으로 설정을 변경한다. [ 안하면 conflict 난리남 ]
이후 나오는 명령어로 세팅을 한다.
```
