## Badge 
```
GitHub 배지(Badges)는 리포지토리의 README 파일이나 다른 마크다운 문서에 종종 삽입되는 작은 이미지 라벨입니다. 
이러한 배지는 특정 정보를 빠르게 전달하거나 리포지토리의 상태를 시각적으로 표시하는 데 도움이 됩니다. 
예를 들어, 배지를 통해 빌드 상태, 테스트 커버리지, 라이선스, 패키지 버전 등 다양한 정보를 표시할 수 있습니다.
```

### 일반적으로 사용되는 GitHub 배지 종류:
> * Build Status: CI/CD 툴(예: Travis CI, GitHub Actions 등)의 빌드 상태를 표시합니다.
> * Code Coverage: 코드 커버리지 툴(예: Codecov, Coveralls 등)의 결과를 표시합니다.
> * License: 리포지토리의 라이선스를 표시합니다.
> * Version: 패키지의 현재 버전을 표시합니다.
> * Downloads: 패키지의 다운로드 횟수를 표시합니다.
> * Stars, Forks: 리포지토리가 얼마나 많이 스타와 포크를 받았는지 표시합니다.
> * Open Issues, PRs: 열려 있는 이슈나 풀 리퀘스트의 수를 표시합니다.
> * Dependencies: 의존성 상태를 표시합니다.

### 배지 추가 방법:
> * Markdown 문법을 사용하여 README.md 파일에 배지를 추가할 수 있습니다. 예를 들어, Travis CI의 빌드 상태 배지를 추가하는 경우 다음과 같은 코드를 사용할 수 있습니다.
```
[![Build Status](https://travis-ci.org/your-username/your-repo.svg?branch=master)](https://travis-ci.org/your-username/your-repo)

```

### 자동화:
> * 여러 배지를 자동으로 추가하고 관리할 수 있는 여러 GitHub Actions이 있습니다.
> * 이러한 Actions은 라이선스, 버전, 빌드 상태 등을 자동으로 감지하고 배지를 README 파일에 추가해 줍니다.
> * YAML 예제에서는 gon1942/badge-it이라는 GitHub Action을 사용하여 이러한 작업을 자동화하고 있습니다.

```
name: 'Github Action Badgit '  # 워크플로우 이름
on: [push]  # push 이벤트 발생 시 실행

jobs:  # 작업 목록
  test:  # 작업 이름
    runs-on: ubuntu-latest  # 사용할 러너 (Ubuntu 최신 버전)
    steps:  # 실행할 단계 목록
      - uses: actions/checkout@v2  # 코드를 체크아웃

      # 배지 추가 단계
      - name: add badges  
        uses: gon1942/badge-it@master  # badge-it 액션 사용
        with:  # 액션에 필요한 파라미터
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}  # GitHub 토큰
          badges: 'gh_license,gh_version, gh_stars, gh_fork, gh_open_issue, gh_open_pr, gh_dependencies, gh_repo_size, gh_code_size, travis_com, travis_org'  # 추가할 배지 목록
          badge-style: 'flat-square'  # 배지 스타일
          badges_line: '### badgesLine'  # 배지가 추가될 라인
```
