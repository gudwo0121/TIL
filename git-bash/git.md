# Git

> 분산버전관리시스템

## git 저장소 만들기

```bash
$ git init
Initialized empty Git repository in C:/Users/student/Desktop/test/.git/

(master) $
```

* `.git` 폴더가 생성되며, 버전이 관리되는 저장소
* git bash에서는 `(master)` 로 브랜치가 표기 된다.

## 버전 만들기

### `add`

> ?

```bash
$ git add <파일/폴더/디렉토리>
$ git add . # 현재 디렉토리 변경 모두
$ git add a.txt   # 특정 파일
$ git add folder/ # 특정 폴더 
$ git add *.png   # 특정 확장자
```

#### 예시

```bash
$ touch a.txt
$ git status
On branch master

No commits yet
# 트래킹되지 않는 파일 / Working directory
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        a.txt

nothing added to commit but untracked files present (use "git add" to track)
$ git add a.txt
$ git status
On branch master

No commits yet
# 커밋될 변경사항들!!! (Staging area)
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   a.txt

```

### `commit` 

## 상태 관련 명령어

### `status`

### `log`

****

1. 가지치기 (branch)

-> 그 과정에서 나오는 충돌 (동일파일 수정후 머지할때)

-> 서로 다른 파일 수정 후 머지는 충돌 x 자동 머지 가능

-> master말고 sub만 수정해서 머지해도 가능

2. push
3. pull
4. clone
5. checkout -b
6. restore --staged
7. fork -> PR
8. reset / revert ??? 솔직히 잘모르겠음
9. touch .gitignore
10. gitignore.io 사이트가서 프로젝트 시작전 설정해줘야함 = 무시(안보여야하는) 파일

