*3학년 1학기 오픈소스 웹소프트웨어 강의에서 배운 HTML, CSS, JS 등 공부 내용 보관하는 리포지토리*

1. 민경이의 깃허브를 훔쳐왔기 때문에 
그쪽 리포지토리에 변경이 생기면 개인적으로 다시 패치해야 함
<Git Bash에서>
# 1️⃣ 원격 저장소의 최신 변경 사항을 가져오기 (업스트림과 동기화)
git pull upstream main --rebase
git pull upstream main && git push origin main
명령으로 업데이트된 부분을 다시 훔쳐올 수 있다

3. 민경이의 깃허브에 변경이 있는지 확인하려면
   git fetch upstream
   git status
   명령으로 변경 여부를 확인할 수 있다


4. 만약 충돌(conflict)이 발생하면 
git add .
git commit -m "충돌해결"
git push origin main 
이런 식으로 개인적으로 해결하거나 리포지토리를 다시 파면 된다
