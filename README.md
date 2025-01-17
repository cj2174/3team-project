## 1. 프로젝트 폴더 만들기
먼저, 프로젝트를 시작할 때 로컬 폴더를 생성하고 그 안에 Git을 초기화해야 합니다.

### 1.1 로컬 폴더 생성
mkdir 3team-project <br />
cd 3team-project<br />

### 1.2 Git 저장소 초기화
Git이 설치된 상태에서 git init 명령어로 프로젝트 디렉터리를 Git 저장소로 초기화합니다.<br />
git init <br /><br />

## 2. GitHub 레포지토리 연결

### 2.1 원격 저장소 연결
GitHub에서 만든 저장소의 URL을 복사하여 로컬 저장소에 연결합니다. 아래 명령어를 사용하여 원격 저장소와 연결합니다.<br />
git remote add origin https://github.com/yourusername/3team-project.git<br /><br />

## 3. 브랜치 관리
각 팀원이 작업할 때는 각자의 브랜치에서 작업을 해야 하고, 작업이 끝나면 PR(Pull Request)을 통해 main 브랜치에 병합합니다.<br /><br />

### 3.1 기본 브랜치 확인 (main)
레포지토리 생성 후, 기본 브랜치로 main이 설정됩니다. main 브랜치는 배포 가능한 안정적인 버전만 유지해야 하므로, 작업은 다른 브랜치에서 진행합니다.<br />
git checkout main  # main 브랜치로 이동

### 3.2 새 브랜치 생성
새로운 기능을 추가하거나 수정할 때는 main 브랜치를 기준으로 새 브랜치를 만듭니다. 브랜치 이름은 작업 내용에 맞게 짓습니다.<br />

예시<br />
feature/scene1 : 새로운 장면 추가<br />
bugfix/login-error : 로그인 오류 수정<br />
git checkout -b feature/scene1  # 새 브랜치 생성 후 이동<br />

### 3.3 브랜치 푸시 (원격 저장소에 업로드)
새로 만든 브랜치는 원격 저장소에 푸시해야 다른 팀원들도 작업할 수 있습니다.<br />
git push -u origin feature/scene1  # 원격 저장소에 브랜치 업로드<br /><br />

## 4. 작업 내용 커밋하기
작업을 하면서 변경된 파일을 커밋(저장)합니다. 커밋은 작업 단위로 묶어서 해야 관리가 용이합니다.<br /><br />

### 4.1 파일 변경 후 스테이지에 추가
git add .  # 모든 변경 사항을 스테이지에 추가<br />

### 4.2 커밋하기
작업 내용은 간단명료하게 커밋 메시지에 적어야 합니다.<br />
git commit -m "새로운 장면 추가"<br /><br />

## 5. GitHub에서 Pull Request (PR) 생성하기
자신의 브랜치에서 작업을 완료한 후, GitHub에서 main 브랜치로 변경 사항을 병합하려면 PR을 생성해야 합니다.<br />

### 5.1 PR 생성하기
GitHub에서 프로젝트의 레포지토리 페이지로 이동합니다.<br />
Pull Requests 탭을 클릭합니다.<br />
New Pull Request 버튼을 클릭합니다.<br />
**기준 브랜치(main)**와 병합하려는 브랜치(예: feature/scene1)를 선택합니다.<br />
PR 제목과 설명을 작성합니다. (작업 내용에 대해 간략하게 설명)<br />
Create Pull Request 버튼을 클릭하여 PR을 생성합니다.<br />

### 5.2 PR 리뷰 및 병합
PR을 생성하면 팀원들이 코드 리뷰를 할 수 있습니다. 리뷰가 끝난 후, Merge 버튼을 클릭하여 main 브랜치에 병합합니다.<br />

## 6. PR 병합 후 정리
병합이 완료되면 작업이 끝난 브랜치는 삭제해야 합니다.<br />

### 6.1 원격 브랜치 삭제
git push origin --delete feature/scene1  # 원격 브랜치 삭제 <br />

### 6.2 로컬 브랜치 삭제
git branch -d feature/scene1  # 로컬 브랜치 삭제<br /><br />

## 7. 기본적인 Git 명령어

#### 현재 브랜치 확인<br />
git branch

#### 원격 저장소 상태 확인<br />
git remote -v

#### 로컬 변경 사항 확인<br />
git status

#### 원격 저장소에서 최신 변경 사항 가져오기<br />
git pull origin main

#### 원격 저장소에 푸시하기<br />
git push

#### 로컬 저장소의 모든 커밋 로그 보기<br />
git log

#### 충돌 해결 후 커밋하기 충돌이 발생하면 충돌을 해결하고 변경된 파일을 스테이지에 추가 후 커밋합니다.<br />
git add .<br />
git commit -m "충돌 해결"<br /><br />

## 8. 협업 시 주의사항
작업하기 전: 항상 main 브랜치의 최신 버전을 받아서 작업을 시작하세요.<br />
작업 완료 후: 변경 사항을 PR을 통해 main 브랜치로 병합합니다.<br />
충돌 해결: 충돌이 발생하면 빠르게 해결하고 팀원들과 상의하세요.<br />
커밋 메시지: 커밋 메시지는 작업 내용을 간단하고 명확하게 작성하세요.<br />
