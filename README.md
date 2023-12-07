* * *
# 🖥OSS 교과목 내용(Git & GitHub)의 정리
* * *
## ▲ 깃설정과 저장소 생성

> 깃설정
> 
 $ git config --global user.name ---- 사용자 이름

 $ git config --global user.email ----@gmail.com 사용자 전자메일

 $ git config --global core.autocrlf true 줄바꿈 자동변환

 $ git config --global core.safecrlf false 줄바꿈 안전 설정

 $ git config --global core.editor 'code --wait' 기본 편집기 설정

 $ git config --global init.defaultBranch main 기본 브랜치 이름

> 저장소 생성
>
git init : 현재 디렉토리를 git repository로 만들기 위해서 사용

git init basic : 현재 폴더 하부에 폴더 basic을 생성하고 git repository로 만들기 위해서 사용

> 저장소 생성 확인
> 
- $ cd basic 폴더 이동

- $ ls -al 파일 확인

## ▲ 깃커밋 로그
> 커밋(commit)

- 버전 관리 위해 현재 스테이지 영역의 내용에 대해 스냅샷 찍는 명령
- $ git commit   커밋 메시지를 입력할 기본 편집기 실행됨
  
  $ git commit -m ‘message'   커밋 메시지를 직접 입력 [-m | --message]
  
  $ git commit -a -m ‘message'    추가와 커밋을 함께 실행 [-a | --all]
  
  $ git commit -am ‘message'


> status 

- 파일 처음 생성:
    - **상태**: Untracked file (붉은 색 - 작업 디렉토리)

- 처음 add한 파일:
    - **상태**: A new file (녹색 - 스테이징 영역)

- 다시 수정한 파일:.
    - **상태**: Modified file (붉은 색 - 작업 디렉토리)
    - 작업 디렉토리의 파일이 수정됨

- 수정한 파일을 add:
    - **상태**: Modified file (녹색 - 스테이징 영역)
    - 스테이징 영역의 파일이 수정됨
 

## ▲ 파일 비교 diff

- 스테이징 영역 기준으로 작업 디렉토리 파일 비교
   - `git diff`: 스테이징 영역과 작업 디렉토리의 변경 사항을 비교합니다.

- 깃 저장소 기준으로 스테이징 영역 파일 비교
   - `git diff --staged HEAD`: 스테이징 영역과 최신 커밋(`HEAD`) 사이의 변경 사항을 비교합니다.
   - `git diff --staged HEAD~`: 스테이징 영역과 이전 커밋(`HEAD~`, 최신 커밋의 부모) 사이의 변경 사항을 비교합니다.

- 깃 저장소 기준으로 작업 디렉토리 파일 비교
   - `git diff HEAD`: 최신 커밋(`HEAD`)과 작업 디렉토리의 변경 사항을 비교합니다.

- 커밋 간의 파일 비교
   - `git diff HEAD~`: 최신 커밋(`HEAD`)과 그 이전 커밋(`HEAD~`) 사이의 변경 사항을 비교합니다.
   - `git diff 048171 0c747d`: 두 커밋 간의 변경 사항을 비교합니다. 여기서 `048171`과 `0c747d`는 각각 커밋의 해시 값이고, 해당 커밋들 간의 변경 사항을 보여줍니다.
   - `git diff HEAD^ HEAD`: 최신 커밋과 그 이전 커밋 간의 변경 사항을 비교합니다. `HEAD^`는 최신 커밋의 부모 커밋을 가리킵니다.

## ▲ 원격저장소
> 원격 저장소 복제
  - `git clone https://github.com/ai7dnn/repo-sync.git`: 원격 저장소를 로컬로 복제하여 가져옵니다.

> 원격 저장소에서 수정 사항 가져오기
 - `git pull origin main`: `origin` 원격 저장소의 `main` 브랜치에서 변경 사항을 가져와 현재 브랜치에 병합합니다.
  `git pull`: 기본 원격 저장소에서 변경 사항을 가져와 현재 브랜치에 병합합니다.

> 원격 저장소에서 수정 사항 가져와 병합
  - `git fetch origin main`: `origin` 원격 저장소의 `main` 브랜치에서 변경 사항을 가져옵니다.
  `git fetch`: 기본 원격 저장소에서 변경 사항을 가져옵니다.
  `git merge origin/main`: 가져온 변경 사항을 현재 브랜치에 병합합니다.

> 로컬 저장소 수정 사항을 원격 저장소에 보내기
 - `git push origin main`: 현재 브랜치의 변경 사항을 `origin` 원격 저장소의 `main` 브랜치에 보냅니다.
  `git push`: 설정된 기본 원격 저장소로 변경 사항을 보냅니다.

 원격 저장소와 로컬 저장소 간에 변경 사항을 주고받을 때 사용하는 기본적인 명령어들입니다.

## ▲ 브랜치 병합

> 일반적인 브랜치 병합
   - `git merge hotfix`: 기본적인 브랜치 병합 명령어로, fast-forward 또는 3-way merge 방식으로 병합합니다.

> 무조건 3-way 병합 수행 
   - `git merge --no-ff hotfix`: 항상 3-way merge 방식으로 브랜치를 병합합니다. Fast-forward가 되지 않도록 강제합니다.

> Fast-forward인 경우에만 병합 진행
   - `git merge --ff-only hotfix`: 가능한 경우에만 Fast-forward 병합을 진행하며, 그렇지 않으면 병합을 거부합니다.

> 현재 브랜치에서 커밋 하나만 생성해서 병합
   - `git merge --squash hotfix`: 브랜치를 병합하되, 하나의 커밋으로 압축하여 현재 브랜치에 적용합니다. 이를 통해 작업 히스토리를 간결하게 유지할 수 있습니다.

## ▲ 커밋 메시지 수정

- 최신 커밋 메시지 수정
  - *$ git commit --amend –m 'new message'*
- 편집기로 최신 커밋 메시지 수정
  - *$ git commit --amend*
- 파일 수정 후 추가, 메시지 수정 없이 최신 커밋으로 수정
  - *$ git commit --amend --no-edit*
- 이전 커밋 HEAD~2..HEAD까지 각각의 커밋을 수정
  - *$ git rebase --interactive HEAD~3*






