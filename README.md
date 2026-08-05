# teamAX

Git과 GitHub를 이용해 Issue, 브랜치, Pull Request, 리뷰, Merge 순서로 협업하는 실습 저장소입니다.

## 협업 순서

```text
Issue 등록
  -> main 최신화
  -> 작업 브랜치 생성
  -> 파일 수정
  -> add와 commit
  -> 작업 브랜치 push
  -> Pull Request 생성
  -> 리뷰와 수정
  -> main으로 Merge
  -> 로컬 main 최신화
```

## 작업 시작 명령

```bash
git switch main
git pull --rebase origin main
git switch -c feature/<이슈번호>-<작업명>
```

## 변경 확인과 커밋

```bash
git status
git diff
git add <파일명>
git diff --staged
git commit -m "feat: 작업 내용"
git push -u origin <작업브랜치명>
```

## 팀 규칙

- `main`에는 직접 push하지 않습니다.
- 작업을 시작하기 전에 Issue를 만듭니다.
- Issue마다 별도의 작업 브랜치를 사용합니다.
- 커밋 전 `git diff --staged`로 내용을 확인합니다.
- PR에는 작업 내용과 테스트 방법을 작성합니다.
- PR 본문에 `Closes #이슈번호`를 넣어 Issue와 연결합니다.
- 리뷰 수정은 같은 브랜치에 추가로 push합니다.

## 브랜치 이름

```text
feature/<issue>-<work>
fix/<issue>-<work>
docs/<issue>-<work>
test/<issue>-<work>
```

## 작업 문서

- [주문 기능](ORDER.md)
- [Issues](https://github.com/axjungeun/teamAX/issues)
- [Pull Requests](https://github.com/axjungeun/teamAX/pulls)

## Merge 후 정리

```bash
git switch main
git pull --rebase origin main
git branch -d <작업브랜치명>
git fetch --prune
git status
```
