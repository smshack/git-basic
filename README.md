# 깃이란
- [git 공식 사이트](https://git-scm.com/ "공식 사이트를 확인하자")
## 형상 관리 도구중 하나
- 버전 관리 시스템
- 소스코드를 효과적으로 관리할 수 있게 해주는 무료 , 공개 소프트웨어

## 깃의 장점
- 소스코드를 주고 받을 필요 없이, 같은 파일을 여러 명이 동시에 작업하는 병렬 개발이 가능
- 즉 브랜치를 통해 개발한 뒤 본 프로그램에 합치는 방식으로 개발을 진행 가능
 - 분산 버전관리이기 때문에 인터넷이 연결되지 않은 곳에서도 개발을 진행할 수 있으며, 중앙 저장소가 날라가버려도 다시 원상복구할 수 있습니다. 
- 팀 프로젝트가 아닌, 개인 프로젝트일지라도 GIT을 통해 버전 관리를 하면 체계적인 개발이 가능해지고, 프로그램이나 패치를 배포하는 과정도 간단해집니다. (pull을 통한 업데이트, patch 파일 배포) 
---

### git : 형상 관리 도구
- 프로젝트를 진행하면서 소스 코드를 USB나 메일로 주고받는 건 엄청난 낭비 임과 동시에 보안성 위험이 있다.   그렇기 때문에 프로젝트를 진행 함에 있어 형상 관리 도구를 사용 한다.
- 형상 관리 도구를 사용하면 변경을 쉽게 되돌릴 수 있다. 소스코드를 과거의 특정 시점으로 되돌리거나, 특정 시점의 변경 사항을 취소하거나, 두 버전의 소스 코드를 비교하는 등의 일이 가능하다.
### github: 형상 관리 도구(버전 관리) 웹 호스팅 서비스
- 협업하고 있는 코드를 저장할 서버가 필요
- 버전 관리 시스템을 지원하는 웹호스팅 서비스의 기능을 통해, push, pull request 같은 이벤트에 반응하여 자동으로 작업(배포 등)을 실행하게 할수 있다

## 깃 관련 용어
- Repository(레퍼지토리): 저장소를 의미하며, 저장소는 히스토리, 태크, 소스의 가지치기 혹은 branch에 따라 버전을 저장한다 -저장소를 통해 작업자가 변경한 모든 히스토리를 확인 가능
- working tree: 저장소를 어느 한 시점을 바라보는 작업자의 현재 시점
- staging area: 저장소에 커밋하기 전에 커밋을 준비하는 위치
- commit: 현재 변경된 작업을 상태를 점검을 마치면 확정하고 저장소에 저장하는 작업
- head: 현재 작업중인 branch를 가리킴
- brance: 가지 또는 분기점을 의미하며, 작업을 할 때 현재 상태를 복사하여 branch에서 작업을 한 후에 완전하다 싶을 때 merge를 하여 작업을 한다
- merge: 다른 branch의 내용을 현재 branch로 가져와 합치는 작업
![git-flow](/images/git-flow.jfif)

# git workflow
![git-flow](/images/git-flow.png)

![git-status](/images/git-status.png)

- working: 우리가 작업하고 있는 공간
    - untracked: .gitignore
    - tracked: modify,add, -
- staging area: 작업 후 버전 히스토리에 저장할 준비가 된 파일을 옮겨 놓는 공간
- git : 버전의 히스토리를 가지고 있는 공간
- remote: 원격 저장소
1. working에서 작업 후 staging으로 추가 (git add)
2. staging에서 작업한걸 git 히스토리에 저장(git commit)
    - commit 된 버전 히스토리는 checkout 명령어로 다시 돌아갈수 있음(3 -> 1 로 원하는 버전으로 수정 가능)
3. 원격 저장소로 업로드(git push)
4. 원격 저장소에서 로컬로 다시 받기 (git pull)

---
## 깃 초기화 하기

> git init 
.git 디렉터리 생성

![gitfilelist](/images/gitfilelist.png)
## 깃 삭제 하기
> rm -rf .git

## 깃 단축키 설정
> git config --global alias.st status

![git-alias](/images/git-alias.png)


## 깃 기초 명령어
- 깃 상태 확인
> git status

![git-status1](/images/git-status1.png)

> git add 파일

- git add 로 추가시 스테이징으로 파일이 올라간걸 확인 가능

![git-status2](/images/git-status2.png)

> git rm --cached 파일명

- staging 에서 다시 working으로 돌리기

![git-status3](/images/git-status3.png)


## 깃 파일 제외 파일
.gitignore

![gitignore](/images/gitignore.png)

## 이전 버전 비교 하기
> git diff 파일명

![git diff](/images/git-diff.png)

## 커밋으로 스테이징에 있는 파일을 git 레퍼지토리로 옮겨줌
> git commit -m '커밋 메시지'

## 깃 로그 확인
> git log

## 원격 저장소에 푸시
> git push origin [브런치]

## 원격 저장소에서 로컬로 pull
>  git pull origin [브런치]
  
## 커밋 수정
### 이전 커밋으로 돌리기 작업내용 유지
> git reset --soft 58cfa445927e1af97b1eedd53385f10cedc544ca

### 다시 커밋

## 그냥 push 할경우 충돌로 오류 발생
> git push -f origin main

## 커밋 메시지 변경
> git commit --amend
> git push -f origin main
    

## 브랜치란?
- 깃은 동시에 여러 개발자들이 프로젝트에서 각기 다른 기능을 개발할 수 있도록 브랜치 기능을 제공
- 서로 다른 브랜치는 작업을 함에 있어서 서로에게 영향을 받지 않는다는 점에서 마음 놓고 서로 다른 개발 작업을 수행 가능
![git branch](/images/git-branch.jfif)
- 기본적으로 git 저장소를 만들면 자동으로 마스터 브랜치가 생성
- 이 브랜치는 일반적으로 배포가 가능한 수준의 안정화된 버전을 포함하고 있음
- 별도의 브랜치를 만들어 사용하고자 한다면 체크 아웃 명령어를 사용

- 브런치 확인
> git branch

- 브런치 생성
> git branch develop1

- 브런치 변경
> git checkout develop1

```
마스터와 develop 충돌 시켜보자
```