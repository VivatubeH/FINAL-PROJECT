# Git

+ 분산형 소스버전 관리 도구
+ 사용 목적
  - 소스 코드의 변경이력을 저장/관리한다.
  - 여러 개발자가 협업해서 소프트웨어를 개발할 수 있도록 지원한다.
  - 문제발생시 특정 시점으로 코드를 되돌릴 수 있다.

+ 파일 상태
  - Untracked(추적되지 않음)
    * git이 버전관리 하지 않는 상태이다. ( 파일을 새로 생성하면 모든 파일은 Untracked 상태 )
    * git add 명령을 실행해서 Staged 상태로 변경하면 추적이 가능해진다.
      
  - Unmodified(수정되지 않음)
    * 이미 로컬 저장소에 커밋이 완료된 파일이다.
    * 작업 디렉토리에서 변경한 내용이 없는 파일이다.
      
  - Modified(수정됨)
    * 이미 로컬 저장소에 커밋이 완료된 파일이다.
    * 작업 디렉토리에서 파일의 내용을 수정했지만 staged 영역에 올려지지 않은 파일이다.
    * 로컬 저장소에 영구적으로 변경이력을 저장하기 위해서는 git add 명령어로 staged 상태로 변경해야 한다.
      
  - Staged(스테이징 영역에 위치함)
    * 커밋 준비가 완료된 파일이다.
    * git commit을 실행해서 최종적으로 변경이력을 로컬 저장소에 저장시킨다.

+ 파일 상태와 관련된 주요 명령어
  - 로컬 저장소 생성 및 초기화
    * git init
      + 로컬 저장소를 생성하고 초기화한다.
      + 프로젝트를 생성하고, 해당 프로젝트가 위치한 폴더에서 이 명령어를 실행하면 해당 프로젝트의 버전을 관리하는 로컬 저장소가 생성된다.
      + 해당 폴더에 .git 폴더가 생성된다.
      + 인텔리제이에서는 Create Git repository가 체크되어 있으면, 자동으로 git init을 실행한 것과 똑같은 결과를 낳는다.
      + 새로 만들면 intellij에서 git에 올릴 지 물어보는데 add를 눌러준다.
     
    * git clone 원격저장소 URL
      + 원격저장소(github에 다른 개발자 혹은 자신이 생성해 놓은 저장소)를 복제해서 로컬 저장소를 생성한다.
      + 프로젝트를 만든 1명을 제외한 사람들은 git clone으로 가져와야 한다.
     
  - 파일의 상태 관리
    * git status
      + 파일의 현재 상태(수정여부, 추적여부)를 조회한다.
    * git add 파일명
      + 파일을 스테이징영역에 추가한다.
      + 추적되지 않음 파일, 수정된 파일을 커밋하기 위해서는 이 명령어를 실행해서 staged 상태로 변경해야 한다.
    * git commit -m "커밋메세지"
      + staged 상태의 파일을 로컬 저장소에 저장시킨다.

  - 브랜치 관리
   * git checkout -b 브랜치명
     + 새로운 브랜치를 만들고 해당 브랜치로 이동한다.
   * git checkout 브랜치명
     + 지정된 브랜치로 이동한다.
   * git merger 브랜치명
     + 지정된 브랜치를 현재 브랜치에 병합시킨다.

  - 원격저장소와 동기화
    * git push origin 브랜치명
      + 로컬 저장소에 커밋된 브랜치의 내용을 원격 저장소에 업로드한다.
    * git pull origin 브랜치명
      + 원격 저장소의 변경된 사항을 로컬 저장소에 가져와서 병합시킨다.

대략적인 인텔리제이 + 깃허브 협업 실행 흐름 
-----------------------------------------------------

* 인텔리제이의 manage remote에서 원격 저장소 url을 입력해서 연결한다.
* push는 로컬에서 원격으로 저장하는 것이다.
* 다른 팀원들은 clone repository를 눌러서 깃허브 주소를 입력하고 clone을 하면 해당 프로젝트를 그대로 가져온다.
* 내가 개발하는 영역은 무조건 branch를 새로 만든다. [ 코딩은 develop이 아닌 자기가 만든 barnch에서만 한다. ] [ 위에 표시됨 ]
* 작은 기능 단위로 commit을 하고, 커밋이 됐으면 push를 한다. [ 내 개발 영역으로 ]
* 우측 아래에 Create pull request가 뜨는데 pull request ( 병합 요청서 )를 작성할 수 있다.
* 관리하는 사람이 문제가 없을 때 Merge pull request와 confirm을 하면 병합이 된다.
   
* 새로운 기능을 개발하기 전에 develop로 checkout(이동)을 한다.
* 그 상태에서 Update Project를 실행한다. (Merge ok를 누른다. )
* develop는 update할 때만 써야한다. develop인 상태에서는 코딩하면 안됨.
* 이후에 새 기능 개발을 시작하는데 New branch를 만든다.
* 내가 개발하는 게 커밋이 되야지만 브랜치 이동을 할 수 있다.

# git flow 협업 전략

- git과 github를 이용한 협업방식 중에서 가장 일반적인 협업방법이다. 
- git flow 협업에서는 main, develop, feature, release, hotfix 브랜치를 운영해서 프로젝트의 모든 단계에서 버전 관리 작업을 수행한다.
- 브랜치 [ 우리는 위의 main, develop, featur 브랜치만 사용한다. ]
  + main 브랜치
    * 현재 실제로 운영환경에서 서비스 중인 버전이 유지되는 브랜치다.
      
  + develop 브랜치
    * 개발중인 기능들이 통합되는 브랜치다.
    * 모든 신규 기능은 develop 브랜치에서 시작해서 새로운 기능을 위한 feature/xxx 브랜치를 생성해서 개발하고 개발이 완료되면 develop 브랜치에 병합된다.
      
  + feature 브랜치
    * 새로운 기능을 개발할 때 사용되는 브랜치다.
    * 새로운 기능을 개발할 때마다 develop 브랜치에서 분기해서 새로운 feature/xxx 브랜치를 생성한다.
    * 개발이 완료되면 feature/xxx 브랜치를 github에 push하고 pull request 작성 후 develop에 병합한다.

  + release 브랜치
    * 릴리스 준비가 완료된 버전을 관리하는 브랜치다.
    * develop 브랜치에서 병합과 테스트가 완료되면 develop 브랜치에서 분기해서 release/x.x.x 브랜치를 생성해서 릴리스 준비를 마친다.
    * 릴리스 준비가 완료되면 main 브랜치에 병합해서 배포한다.
  
  + hotfix 브랜치
    * 운영중인 코드에 긴급 수정사항이 발생했을 때 사용되는 브랜치다.
    * main 브랜치에서 분기하여 hotfix/xxx 버그수정 브랜치를 생성한다.
    * 버그 수정이 완료되면 develop 브랜치와 main 브랜치에 병합한다.

# 개발 협업하기
  + 프로젝트 생성
    1. 팀장이 신규 프로젝트 생성한다.
       * 프로젝트 생성시 로컬저장소를 만든다.
       * 로컬 저장소에 커밋한다. [ 새로 만들 때 커밋을 한 번 하고 이름을 변경할 수 있다. ]
       * 브랜치명을 master에서 develop으로 변경한다. 
    2. 팀장이 github에 원격 저장소를 생성한다.
       * Git -> Manage Reomote에서 원격 저장소의 URL을 추가한다.
    3. 팀장이 원격저장소에 push한다.
       * intelli에서 develop을 push한다. [ 그러면 원격저장소에 소스가 올라간다. ]
      
  + 개발자 ( 팀원 )
    1. 개발자는 원격저장소를 복제한다.
       * 인텔리제이 프로젝트의 초기화면에서 Clone Repository를 선택한다.
       * URL을 입력해야 하는데, 팀장이 만든 원격 저장소의 URL을 복사해서 붙여넣는다.
       * 프로젝트가 그대로 복제된다.
    2. 새로운 기능 개발하기
       * develop 브랜치에서 분기해서 feature/xxx 브랜치를 생성한다.
       * 현재 브랜치가 feature/xxx로 변경된 것을 확인하고, 신규 기능을 개발한다. [ 가장 중요 ]
    3. 신규 기능을 원격저장소에 저장하기
       * 현재 브랜치가 feature/xxx 상태에서 메뉴바 상단의 자기 저장소를 클릭하고 commit을 누른다.
       * 커밋 메세지를 작성하고, commit and push 버튼을 클릭해서 로컬저장소에 저장(commit)시키고 원격저장소에 저장(push)시킨다.
    4. develop 브랜치에 feature/xxx 브랜치의 내용을 병합하기
       * intellij혹은 github사이트에서 pull request를 작성한다. [ 가능하면 github 사이트에서 작성하기 (compare and pull request) ]
       * github 사이트의 pull request 메뉴를 클릭하고 선택한 다음, 검토 후 merge pull request > confirm merge 버튼을 클릭해서 develop 브랜치에 병합시키다.
    5. 원격저장소의 develop과 로컬저장소의 develop 동기화하기
       * intellij에서 현재 브랜치를 develop로 변경한다. [ checkout으로 이동가능 ]
       * update project를 실행해서 원격 저장소의 develop의 갱신내용을 내려받아서 로컬 저장소의 develop에 병합시킨다.

### 팀장 및 개발자는 새로운 신규 기능을 개발할 때마다 5 -> 2 -> 3 -> 4 번 순서로 작업을 반복한다.

## 현재 브랜치의 작업 내용을 로컬 저장소의 임시저장소에 저장하기

  * 기능을 개발하던 도중에 develop 브랜치와 동기화가 필요한 경우 사용한다.

  1. 현재 브랜치의 작업내용을 임시저장소에 저장시키기
     + git stash
  2. 로컬저장소 develop 브랜치로 이동시키기
     + git checkout develop
  3. 원격저장소 develop 브랜치의 최신 내용을 내려받기 ( 원격 develop와 로컬 develop을 동기화함 )
     + git pull origin ( origin은 원격저장소의 이름이다. )
  4. 동기화 완료 후 작업 중인 feature/xxx 브랜치로 이동하기
     + git checkout feature/xxx
  5. 동기화된 로컬 develop의 내용을 feature/xxx에 병합하기
     + git merge develop
  6. 임시 저장한 작업내용을 복원하기
     + git stash apply
