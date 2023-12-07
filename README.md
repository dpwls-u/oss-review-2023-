* * *
# 🖥OSS 교과목 내용(Git & GitHub)의 정리
* * *
## ▲ 깃설정에대해 알아보자

> 깃설정
> 
    $ git config --global user.name ~~

    $ git config --global user.email ~~
    
    $ git config --global core.autocrlf true
    
    $ git config --global core.safecrlf false
    
    $ git config --global core.editor 'code --wait'
    
    $ git config --global init.defalutBranch main

    물론이죠! 명령어들을 간결하게 요약해보겠습니다.
    
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

 이 명령어들은 Git을 사용하여 원격 저장소와 로컬 저장소 간에 변경 사항을 주고받을 때 사용하는 기본적인 명령어들입니다.

## ▲ 기말고사 범위 내용
```
<다양한 브랜치 병합>
- 기준 브랜치에서 hotfix 브랜치 병합
- 무조건 3-way 병합 수행
- fast-foward인 경우에만 병합 진행
- 현재 브랜치에서 커밋 하나만 생성해서 병합

*응애* //옆으로 기운? 글씨
_응애s_
**응애s**  //두꺼운 글씨
__응애s__ 
~~응애~~ //취소선? 그어짐
```
## ▲ 커밋 메시지 수정

- 최신 커밋 메시지 수정
  - *$ git commit --amend -m 'new message'*
- 편집기로 최신 커밋 메시지 수정
  - *$ git commit --amend*
- 파일 수정 후 추가, 메시지 수정 없이 최신 커밋으로 수정
  - *$ git commit --amend--no-edit*
- 이전 커밋 HEAD~2..HEAD까지 각각의 커밋을 수정
  - *$ git rebase--interactive HEaD~3*

* * *
***
*****
- - -
---


>ㅇㅇ
>>ㅇㅇ
>>>ㅇㅇㅇㅇ
>>>
>>>* * *
>>
>>


