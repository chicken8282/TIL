# 개발자로 성장하기
## 개발자로 성장하기

1. 순서가
    1. 있는
2. 리스트

- 순서가
  - 없는
- 리스트

```python
print("hello")
```

어떤 텍스트 안에
`print("hello")`
코드를 포함하고 싶다.

[클릭하면 구글로 이동](https://www.google.com/)

![이미지](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSz431yZ4IjKOx_ZtPgFKZr3EHl5Ko8V2LJFi9U2klVAB8rnG5c9x4ddmpTsDnUojXK4KK8Y5i21nR-2THUrZFQSaO2oDAjYm08FKxXns2p)

![이미지](images.webp)

**굵게**

*기울임*

~~취소~~

---

본문2

| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |

:joy:
:boom:
:

`touch`: 파일 생성
`mkdir`: 새 디렉토리 생성
`ls`: 현재 작업 중인 디렉토리 내부의 폴더/파일 목록을 출력
`cd`: 현재 작업 중인 디렉토리를 변경 (위치 변경)
`start`: 폴더/파일을 열기 (Mac에서는 open을 사용)
`rm`: 파일 삭제 (디렉토리 삭제는 -r 옵션을 추가 사용)
`pwd`: 현재 작업 중인 폴더(디렉토리)의 절대 경로를 출력

`Working Directory`: 실제 작업 중인 파일들이 위치하는 영역
Staging Area: Working Directory에서 변경된 파일 중, 다음 버전에 포함시킬 파일들을 선택적으로 추가하거나 제외할 수 있는 중간 준비 영역
`Repository`: 버전 이력과 파일들이 영구적으로 저장되는 영역, 모든 버전과 변경 이력이 기록됨
`commit`: 변경된 파일들을 저장하는 행위, 'snapshot' 이라고도 함

`git init`: 로컬 저장소 설정(초기화)
-> git의 버전 관리를 시작할 디렉토리에서 진행
`git add`: 변경사항이 있는 파일을 staging area에 추가
`git commit`: staging area에 있는 파일들을 저장소에 기록
-> 해당 시점의 버전을 생성하고 변경 이력을 남기는 것

`git rm -cashed test.txt` -> staging area에서 다시 working directory로 이동
`git commit -m sample.txt` -> staging area에서 repository로 커밋

# git 로컬 저장소 내에 또다른 git 로컬 저장소 만들지 말 것

`git commit --amend`
1. commit 메시지 수정 -> 아무거나 누른 뒤 수정 후 esc -> :wq 입력
2. commit 전체 수정

`git remote add origin remote_repo_url`: 원격 저장소 추가

`git push origin(원격저장소 이름) master(branch 이름)` : 로컬저장소 -> 원격저장소로 커밋이 올라가는 것

`git pull origin master`: 원격저장소의 변경사항만을 받아옴 (업데이트)

`git clone remote_repo_rul` : 원격 저장소 전체를 복제 (다운로드)
# clone으로 받은 프로젝트는 이미 git init이 되어 있음

`git remote -v`: 현재 로컬 저장소에 등록된 원격 저장소 목록 보기

`git remote rm 원격_저장소_이름`: 현재 로컬 저장소에 등록된 원격 저장소 삭제

`git revert <commit id>`: commit을 없었던 일로 만드는 작업
- 프로젝트 기록에서 commit을 없었던 일로 처리 후 그 결과를 새로운 commit으로 추가함

- 변경 사항을 안전하게 실행 취소할 수 있도록 도와주는 순방향 실행 취소 작업

- commit 기록에서 commit을 삭제하거나 분리하는 대신, 지정된 변경 사항을 반전시키는 새commit을 생성

- git에서 기록이 손실되는 것을 방지하여 기록의 무결성과 협업의 신뢰성을 높임

`git reset [옵션] <commit id>`: 특정 commit으로 되돌아 갔을 때, 되돌아간 commit 이후의 commit은 모두 삭제

# 옵션
- `--soft`
  - 삭제된 commit의 기록을 staging area에 남김
- `--mixed`
  - 삭제된 commit의 기록을 working directory에 남김 (기본 옵션 값)
- `--hard`
  - 삭제된 commit의 기록을 남기지 않음

`git reflog`
- HEAD가 이전에 가리켰던 모든 commit을 보여줌
- reset의 --hard 옵션을 통해 지워진 commit도 reflog로 조회하여 복구 가능

`git reset --hard<복구하고자 하는 commitID>`

`git restore`: Modified 상태의 파일 되돌리기
- 원래 파일로 덮어쓰는 원리이기 때문에 수정한 내용은 전부 사라짐
# git restore를 통해 수정 취소 후에는 해당 내용을 복원할 수 없음

`git rm --cached`: Staging Area에서 Working Directory로 되돌리기
-> git 저장소에 "commit이 없는 경우"

`git restore --staged`: Staging Area에서 Working Directory로 되돌리기
-> git 저장소에 "commit이 존재하는 경우"

