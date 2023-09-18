## 1. 깃허브 기반의 공개SW 연구개발 플로우
    - 0. Projcect Board & MileStones 
    - 1. Issue 생성 -> Commit & Push
    - 2. Issue 기반의 브랜치 생성 -> Dev/ Commit & Push
    - 3. Pull Request 요청
    - 4. Code Review 완료 
    - 5. 메인 Branch 병합 및 릴리즈 
    
    > * Template를 활용한 일관된 형식의 이슈, 커밋, 풀리퀘스트

## 2. Issue 관리
```
프로젝트 진행 중 발생할 수 있는 문제,기능 개선 등의 부분을 기록하고 추적하는 일종의 “할 일 목록”

> Github의 Issues는 개발에서 발견되는 버그, 기능, 개선 사항 등등을 추적하고 관리
> Issue = 기능 개발, 버그, 개선 사항 등등 모든 작업들을 의미
> 이슈를 생성시 제목, 내용, 라벨, 담당자, 마일스톤, 프로젝트 등의정보를 포함.
# 이러한 이슈들을 Github Project, Github Milestone을 이용하면  →   프로젝트 작업의 진행 상황을 파악하기 쉬움.
```

> * Issue Template
> * Issue 기반 Branch 생성
> * Project Board, Milestones


## 3. Pull Request
```
프로젝트의 원본 저장소에 변경 사항을 제안하고, 그 변경 사항을 리뷰 및 토론하는 프로세스
PR 요청시 Github Actions 트리거를 발생시켜 코드 품질 관리 및 빌드/테스트 작업을 실행
- 리뷰어는 코드 품질 도구의 실행 결과를 참조하여 메인 브랜치에 Merge or Close.
- 코드 품질 관리 도구 종류 : CodeQL, SonarQube, Travis-CI, Jenkins, Github Actions Workflows etc.
```
> * PR Template
> * Github Action CI/CD

## 4. Code Review
    
    Approve: 코드에 대한 의문점이 없다면 승인 .
    Comment: 간단한 피드백 제출
    Request changes: 해당 코드에 문제가 있다고 판단되며 코드를 반드시 수정 요구
    
## 5. Release
```
- 수동 or 자동(Github Action) 배포 가능한 소프트웨어를 제공하여 사용자가 다운로드하고 사용
```

## 6. Wiki
```
공개 소프트웨어 연굴 개발 프로젝트에 관련된 사항을 문서화하는것은 프로젝트의 투명성, 지식공유, 협업의 원활함을 위해 필요

> 사용자용 
- 릴리즈 노트, 시스템 요구 사항, 설치 가이드, 사용자 매뉴얼, 이전버전과 호환성을 유지하는 방법, 기능 리스트

> 개발자용 
- 소스 코드로 작업하는 법, 빌드 방법, 아키텍처의 구성, 
개발 프로세스 개요, 디버깅 방법, 테스트 자동화 방법, 
패치를 제출하는 방법. API 활용 방법

> 프로젝트 활성화를 위한 기타 문서 
- 라이선스, 제품 로드 맵, 개발 전략, 문서화 참여 방법, 도입 사례, 각종 백서
```


## 깃허브 연구개발을 위한 요소들.
```
* Badge ( 프로젝트 레포지토리의 활성화를 위한 시각화 )
* READEME.md
* LICENSE.md
* CONTRIBUTING.md
* CODE_OF_CONDUCT.md
* 기여자 라이선스 협약(CLA)
* Discussions 
```
