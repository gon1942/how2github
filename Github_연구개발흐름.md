## 1. 깃허브 기반의 공개SW 연구개발 플로우
    - 1. Issue 생성 -> Commit & Push
    - 2. Issue 기반의 브랜치 생성 -> Dev/ Commit & Push
    - 3. Pull Request 요청
    - 4. Code Review 완료 
    - 5. 메인 Branch 병합 및 릴리즈 

2. Issue 관리
> * Issue 발행
> * Issue란?
> * Issue Template
> Issue Template 등록
> Issue Template 사용법
> Issue Template 파일
> Issue 작업
> 등록된 issue 살펴 보기
> Issue 연동
> Issue 기반 Branch 생성


3. Pull Request[Code Review]
> Code Review
    
    Approve: 코드에 대한 의문점이 없다면 승인 .
    Comment: 간단한 피드백 제출
    Request changes: 해당 코드에 문제가 있다고 판단되며 코드를 반드시 수정 요구
    

4. CI & Test Coverage 
    ``GitHub Marketplace Public Repository를 이용하면 대부분 무료로 이용 가능``

> CI 도구 (Travis) 사용법
> 
    Merge pull request를 통해서 해당 작업(issue)을 반영했다면 Travis가 Build 할 때 작성된
    Test Code 기반으로 Coverage 정보를 위처럼 자동으로 코멘드를 추가해줍니다.
    누군가가 테스트 코드를 작성하지 않았다면 Change from base 항목에서 - 표시가 됩니다.
    이렇게 해당 작업마다 커버리지를 표시하는 것이 전체 커버리지를 높이고 그 값을 유지하는 좋은 방법이다.
> 테스트 커버지리 표시


5. Wiki


6. 깃헙 칸반보드 및 ZenHub 사용법 `이슈들이 발급되면 그것을 한눈에 보는 것은 기존 UI에서는 어렵습니다. 이런 문제를 칸반보드 형식으로 해결해주는 것이 ZenHub`


7. Milestone `전체적인 작업에 진행 척도를 가시적으로 확인하기 좋다 `
8. Labels `Epic은 Milestone과 비슷하게 이해하시면 됩니다. 큰 작업(Issue)이 있다면 그 작업(Issue)을 여러 Issue로 등록하고 한 묶음으로 관리하는 것`
9. Github Action
> Github Action 만들기
> 
   java ==> gradle.yml
    
> Action Workflows

10. Badge
11. READEME.md
12. LICENSE.md
13. CONTRIBUTING.md
14. CODE_OF_CONDUCT.md
15. .gitmessage.txt
16. .all-contributorsrc
17. Issue-template
