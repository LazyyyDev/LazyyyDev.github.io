---
layout: post
title: "깃(Git) 자주 사용하는 명령어"
tags: [Git, Git command]
comments: true
---

Git을 이제 본격적으로 사용해서 프로젝트를 진행해볼 생각입니다.   
이에 앞서, git bash를 사용하기위해 기본적으로 익혀둬야할 명령어를 공부하려고 합니다.

---
### **설정 및 기본 명령어** 

- 전역 사용자명/이메일 구성하기
    ```
    git config --global user.name "my name"
    git config --global user.email "my email"
    ```
    
- 저장소별 사용자명/이메일 구성하기
    ```
    cd my repo
    git config user.name "my name"
    git config user.email "my email"
    ```

- 전역 설정 정보 조회
    ```
    git config --global --list
    ```

- 저장소별 설정 정보 조회
    ```
    git config --list
    ```

- 새로운 저장소 초기화
    ```
    mkdir /path/Dir
    cd /path/Dir
    git init
    ```

- 저장소 복제
    ```
    git clone <repo url>  -  저장소 이름과 같은 상위 폴더를 현재 디렉토리에 복사
    git clone <repo url> . -  상위 폴더 없이 저장소의 내용물만 현재 디렉토리에 복사
    ```

- 변경 사항 체크   
    ```
    git status
    ```

- 원격 저장소 추가
    ```
    git remote add origin <repo url>
    ```

- 원격 저장소 제거하기 (관련된 브랜치도 포함)
    ```
    git remote rm origin
    ```

- 변경된 모든 파일 스테이징 및 커밋
    ```
    git add *
    git commit -m "message"
    ```

- 원격으로 보내기(푸시)
    ```
    git push origin master
    ```

- 커밋 이력 확인
    ```
    git log                     // 모든 커밋 log
    git log -num                // 최근 num개 커밋 log
    git log --pretty=online     // 각 커밋을 한 줄로 표시
    git log reflog              // reset 혹은 rebase로 없어진 과거의 커밋 이력 확인
    ```

---
### **브랜치**

- 브랜치 목록
    ```
    git branch // local
    git branch -r //remote
    git branch -a // all of branch
    ```

- 브랜치 생성
    ```
    git branch new master   // master -> new 브랜치 생성
    git push origin new     // new 브랜치 원격으로 보내기
    ```

- 브랜치 삭제
    ```
    git branch -D <삭제할 브랜치 명>    // local
    git push orgin :<원격 브랜치>       // remote ??
    ```

- 빈 브랜치 생성
    ```
    git checkout --orphan <새로운 브랜치 명>
    git commit -a               // commit해야 새로운 브랜치 생성
    git checkout -b new-branch  // 브랜치 생성과 동시에 체크아웃
    ```

- 리모트 브랜치 가져오기
    ```
    git checkout -t origin/<가져올 브랜치 명>
    ```

- 현재 브랜치 이름 변경
    ```
    git branch -m <new name>
    ```

---

### **기타**

`[]` : 생략 가능   

- 작업 트리 변경 사항 되돌리기
    ```
    git checkout HEAD <file> [<file>]
    ```

- 마지막 커밋 수정
    ```
    git commit -m "message" --amend
    ```

- 이전 커밋을 수정하고 커밋 메세지를 재사용
    ```
    git commit -C HEAD --amend
    ```

- 파일 삭제
    ```
    git rm --cached --ignore-unmatch <삭제할 파일명>
    ```

- 히스토리 삭제 (id, password 같은 비공개 정보 파일을 올렸을 때 삭제하기 위한 목적)
    ```
    git clone <repo url>    # 저장소 복사
    cd <folder name>        # 해당 폴더 이동
    git filter-branch --index-filter 'git rm --cached --ignore-unmatch <삭제할 파일명>' --prune-empty -- --all  # 모든 히스토리에 해당 파일 삭제
    git push origin master  # 서버로 전송
    ```

- 리모트 주소 추가하여 로컬에 싱크
    ```
    git remote add upstream <리모트 주소>
    git pull upsteram <브랜치 명>
    ```

- 최적화
    ```
    git gc
    git gc --agressive
    ```

---

### **마치며**

git을 아직 제대로 써보진 않았지만 브랜치를 만들고 이들을 다시 합치는 부분이 상당히 헷갈린다.   
계속해서 사용해보면 적응하겠지 나도...