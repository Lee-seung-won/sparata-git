# 👍 feature 브랜치를 main 브랜치 위로 rebase 하면서 충돌을 해결한 방법
``` shell
git checkout main
echo "반갑습니다, 여기는 main브랜치입니다!" > conflict_test.txt
git add conflict_test.txt
git commit -m "conflict_test.txt : modified main"
git checkout feature
echo "반갑습니다, 여기는 feature브랜치입니다!" > conflict_test.txt
git add conflict_test.txt
git commit -m "conflict_test.txt : modified feature"
git rebase main
#충돌 발생 -> main브랜치의 내용으로 conflict_test.txt수정
git add conflict_test.txt
git rebase --continue
git checkout main
git merge feature
#Fast Forward
```