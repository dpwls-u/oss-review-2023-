* * *
# 🖥OSS 교과목 내용(Git & GitHub)의 정리
* * *
## ▲ 깃설정에대해 알아보자
```
< 깃 설정 명령 구조 >
  - $ git config --설정범위 설정변수 설정값
  -설정 범위
    - [--system | --global | --local]
  - --global인 경우 설정 파일
    - c:user[사용자-계정].gitconfig



- ㄹㄹㄹㄹ
- 

```
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


