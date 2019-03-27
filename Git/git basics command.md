# git

## create branch & checkout

```command
git checkout -b $brand_name
```
</br>

## commit 수정

누락 된 파일 추가 또는 기존 파일 및 설명을 수정이 필요한 경우

```command
git commit --amend
```
</br>

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
