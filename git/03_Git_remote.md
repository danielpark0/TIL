## 03. Git Remote

- `git remote` : Remote Repository 주소 등록 (여기서는 GitHub Repo)
  - `git remote origin add origin (주소)` : Remte Repo 주소를  origin 이라는 별칭으로 등록
  - `git remote -v` : 등록된 Remote 주소 확인

- `git push (별칭) (브랜치이름)` : 별칭으로 브랜치를 push (전송)
  - `git push origin master` : origin으로 master 브랜치 push

- `git clone (주소)` : 주소로부터 Repo 가져오기
- `git pull (별칭) (브랜치이름)`  : 별칭으로부터 브랜치를 pull(내려받기)