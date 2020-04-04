# git

## create branch & checkout

```command
git checkout -b $brand_name
```

## commit 수정

누락 된 파일 추가 또는 기존 파일 및 설명을 수정이 필요한 경우

```command
git commit --amend
```

## commit 되돌리기

### revert

원격 저장소에 이미 반영된 경우, 특정 commit 내용을 삭제한 새로운 commit 생성

```command
git revert $commit1 $commit2
```

### reset

로컬 저장소에서 작업하는 경우, 이전 commit 이력을 삭제

```command
git reset $commit
```

### stash

A, B Branch 가 있는 상태에서

B Branch에서 작업하는 중에 B Branch에서 작업한 내용을 저장하고

A Branch checkout 이 필요한 경우

```shell
git stash list
git stash save
git stash apply
git stash drop
git stash pop
```

### fetch

remote 와 현재 작업 중인 local 소스와 비교 하고 싶을때

```shell
git fetch
git diff HEAD origin/master
```

pull은 HEAD 위치가 remote와 local이 같고, fetch는 다르다.

### tag

```shell
git tag {tag name} [branch name]or[commit no]

# annotated tag
git tag -a {tag name} [branch name]or[commit no] -m {message}

# annotated tag 정보 상세 보기
git tag -v {tag name}

# tag push to remote
git push --tags

# delete tag
git tag -d {tag name}
```
