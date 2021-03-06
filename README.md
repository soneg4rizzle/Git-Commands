# Git-Commands

> Frequently used Git commands

## #1. git init : 프로젝트 폴더 초기화(저장소 만들기)

`git init`으로 내 프로젝트 폴더에서 로컬 Git 저장소를 설정합니다.

```
$ git init

mkdir [디렉토리 이름]             // 디렉토리 생성
cd [디렉토리 이름]                // 해당 디렉토리로 이동
toudch [파일 이름]               // 파일 생성
echo ["글자"] >> [파일명]        // 파일에 글자 추가
git init // 로컬 저장소 생성 (디렉토리 하위에 .git 디렉토리 생성)
```

## #2. git status

> 저장소의 상태를 확인하기 위해 사용하는 명령어로 현재 브랜치의 이름과 추가·변경된 파일 및 디렉토리 목록을 표시합니다.

```HTML
$ git status
```

## #3. git add

> 파일이나 디렉토리의 변경사항을 인덱스에 추가합니다.
> 다음 변경(commit)을 기록할 때까지의 변경기록을 모아놓기 위해 사용합니다.

① 작업 디렉토리의 변경 내용의 일부만 스테이징 영역에 넘기고 싶을 때는 수정한 파일이나 디렉토리의 경로를 인자로 넘깁니다.

```HTML
$ git add <파일/디렉토리 경로>
```

② 현재 디렉토리의 모든 변경 내용을 스테이징 영역으로 넘기고 싶을 때는, .을 인자로 넘김니다.

```HTML
$ git add .
```

③ 작업 디렉토리 내의 모든 변경 내용을 몽땅 스테이징 영역으로 넘기고 싶을 때는, -A 옵션을 사용합니다.

```HTML
$ git add -A
```

## #4. git commit

> 스테이지 올라가 있는 변경 사항을 이력에 추가합니다.
> `-m` 옵션을 사용하여 commit에 대한 정보 작성

```HTML
$ git commit -m "[커밋에 대한 메세지 작성]"
```

## #5. git log

> `git log` 커밋 히스토리를 조회할 수 있는 명령어입니다.

```HTML
$ git log
```

> 지금까지의 커밋 기록을 모두 출력하며 가장 최근 내역이 맨 위에 표현됩니다.

```HTML
$ git log --oneline
```

> 커밋된 로그 내역을 커밋섬과 커밋이름과 함께 한 줄로 간단하게 표현합니다.

## #6. git reset

> 특정 커밋까지 이력을 초기화합니다. 작업 후 커밋한 이력을 되돌릴 때 사용합니다.
> **주의** : 이전 이력이 지워지기 때문에 주의가 필요합니다.

```HTML
$ git reset [커밋 아이디] --mixed # 예) d781824f .. (커밋 아이디의 앞 7자리정도만 복사하면 된다.)
```

> mixed 옵션을 쓰면 HEAD가 특정 커밋(과거 또는 미래)을 새롭게 가리키게 됩니다. 그리고 staging area도 해당 커밋의 모습과 동일하게 변합니다. 하지만 현재 작업 중인 working directory는 아무런 영향을 받지 않습니다.

```HTML
$ git reset [커밋 아이디] --hard
```

> hard 옵션을 쓰면 HEAD가 특정 커밋(과거 또는 미래)을 새롭게 가리키게 됩니다. 그리고 staging area와 현재 작업 중인 working directory도 해당 커밋의 모습과 동일하게 변합니다.

```HTML
$ git reset [커밋 아이디] --soft
```

> —soft 옵션을 쓰면 HEAD가 특정 커밋(과거 또는 미래)을 새롭게 가리키게 됩니다. 하지만 현재 작업 중인 working directory와 staging area는 아무런 영향을 받지 않습니다.

| Git Reset의 3가지 옵션 |             1             |             2             |             3             |
| :--------------------: | :-----------------------: | :-----------------------: | :-----------------------: |
|                        |          --soft           |     --mixed(default)      |          --hard           |
|          HEAD          | 지정한 커밋으로 이동한다. | 지정한 커밋으로 이동한다. | 지정한 커밋으로 이동한다. |
| HEAD가 가리키는 Branch |     HEAD와 같이 이동      |     HEAD와 같이 이동      |     HEAD와 같이 이동      |
|      Staging Area      |           변화X           | 지정한 commit과 동일 내용 | 지정한 commit과 동일 내용 |
|   Working Directory    |           변화X           |           변화X           | 지정한 commit과 동일 내용 |
|        주 용도         |        branch 이동        |   Staging Area에서 빼기   |      commit 되돌리기      |

## #7. git revert

> 특정 커밋을 취소하는 새로운 커밋을 만드는 명령어입니다.
> 일반적으로 특정 버전이 문제가 발생 시 문제가 생긴 커밋을 `revert`합니다.
> 원상복구한 상태로 계속해서 작업을 이어나가고 문제를 수정하면 다시 커밋하는 방식으로 사용합니다.

```HTML
git revert [커밋 아이디]
```

## 참고

> [코드잇](https://blog.naver.com/PostView.naver?blogId=codeitofficial&logNo=221950118036&redirect=Dlog&widgetTypeCall=true&directAccess=false) > [Git/Github 안내서][https://subicura.com/git/guide/basic.html]
