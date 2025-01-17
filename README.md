### 1. 작업 폴더 생성하기

### 2. 작업 폴더에 들어가서 깃허브 레포지토리 클론(복제)하기
git clone https://github.com/cj2174/3team-project.git

### 3. 클론 완료 후, 원격 연결 상태 확인
git remote -v
정상 출력 결과 :
origin  https://github.com/cj2174/3team-project.git (fetch)
origin  https://github.com/cj2174/3team-project.git (push)


### 4. 새 브랜치 만들기
ex) ActI_Scene1을 맡았다면:
git checkout -b feature/scene1

만든 새 브랜치를 원격저장소에 push(업로드)하기
git push -u origin feature/scene1
브랜치 규칙은 feature/작업내용
ex) feature/scene2


### 5. 작업 완료 후 푸시하기
맡은 작업을 수정했다면, 변경 사항을 저장소에 올리기!

변경 사항 스테이지에 추가
git add .

변경 내용 커밋하기
git commit -m "수정한 내용 작성"
* 커밋 메세지는 작업 내용을 간단, 명확하게 작성
ex) Update Scene1 어쩌구저쩌구

수정한 내용 푸시하기
git push

### 6. Github에 접속해서 Pull Request(PR) 생성해서 병합 요청하기
Pull Request 생성 방법
- 깃허브 레포지토리로 이동.
- "Pull Requests" 탭 클릭.
- "New Pull Request" 버튼 클릭.
- 작업한 브랜치(feature/scene1)와 병합 대상 브랜치(main)를 선택.
- PR 제목과 내용을 작성:
- 제목: 작업 내용을 요약 (예: Update Scene 1 dialogue).
- 내용: 변경 사항에 대한 자세한 설명 추가.
- "Create Pull Request" 버튼 클릭.
- 팀원들은 PR 내용을 확인하고 리뷰를 남길 수 있음.
- 리뷰가 완료되면 main 브랜치로 병합!

** 성공적으로 작업 병합이 되었다면, 원격 브랜치 삭제해서 정리하기

원격 브랜치 삭제(깃허브에서)
git push origin --delete feature/scene1

로컬 브랜치 삭제(내 컴퓨터에서)
git branch -d feature/scene1
