

<h1 align="center">How2github</h1>


<p align="center">
  <a href="#dart-about">About</a> &#xa0; | &#xa0; 
  <a href="#white_check_mark-github-인터페이스-이해하기">Github 인터페이스 이해하기</a> &#xa0; | &#xa0;
  <a href="#white_check_mark-github-워크플로우에-필요한-핵심-파일들">GitHub 워크플로우에 필요한 핵심 파일들</a> &#xa0; | &#xa0;
  <a href="#white_check_mark-how2github-폴더-구조">How2Github 폴더 구조</a> &#xa0; | &#xa0;
</p>

<br>

## :dart: About ##

how2github 저장소에 오신 것을 환영합니다!\
이 저장소는 GitHub 기반 워크플로우를 사용하는데있어서 필요한 정보를 제공하는 것을 목적으로 합니다.\
GitHub을 처음 사용하는 분이든 특정 기능에 대한 간단한 복습이 필요하신 분이든, 여기서 필요한 정보를 찾을 수 있습니다.\

1. GitHub 인터페이스에 대한 이해.
2. GitHub 워크플로우에 필요한 핵심 파일들.
3. 이슈, 커밋, PR, 릴리즈, 컨트리뷰터를 위한 환경 구성에 대한 이해 및 사용법.

이 외 필요한 부분이 있으신 경우 [Issue](https://github.com/gon1942/how2github/issues/new?assignees=gon1942&labels=enhancement&projects=&template=%EA%B8%B0%EB%8A%A5-%EC%9A%94%EC%B2%AD.md&title=%5BFEATURE%5D) 또는 [Discussion](https://github.com/gon1942/how2github/discussions/new?category=request)으로 요청해 주세요.


## :white_check_mark: Github 인터페이스 이해하기  ##
> GitHub의 핵심적인 부분입니다. 저장소는 프로젝트의 코드, 문서, 그리고 관련 리소스를 저장하는 곳입니다.
```
Code: 저장소의 코드와 파일들을 볼 수 있습니다.
Issues: 프로젝트와 관련된 문제점이나 제안사항을 토론할 수 있는 곳입니다.
Pull Requests: 코드 변경을 제안하고, 리뷰 및 병합을 관리하는 섹션입니다.
Actions: CI/CD와 같은 자동화된 워크플로우를 설정하고 관리하는 부분입니다.
Projects: 칸반 보드 스타일로 프로젝트 관리를 도와줍니다.
Wiki: 프로젝트와 관련된 문서를 작성하고 공유하는 공간입니다.
Settings: 저장소 설정, 권한 관리, 웹훅 설정 등을 할 수 있는 곳입니다.
```


## :white_check_mark: GitHub 워크플로우에 필요한 핵심 파일들 ##

1. README.md -> [리드미 사용법 바로가기!](https://github.com/gon1942/how2github/blob/main/00.Basic_Github/01.About_READEME.md)
- 목적: 프로젝트의 기본 설명, 사용 방법, 기여 방법 등을 소개합니다.
- 위치: 저장소의 루트 디렉토리에 위치합니다.
- 팁: Markdown 언어를 사용하여 작성하며, 이미지, 링크, 코드 등을 포함할 수 있습니다.
2. .gitignore -> [사용법 바로가기.](https://github.com/gon1942/how2github/blob/main/00.Basic_Github/06.About_.gitignore.md)
- 목적: Git에서 추적하지 않을 파일 또는 디렉토리를 지정합니다.
- 위치: 저장소의 루트 디렉토리에 위치합니다.
- 팁: 특정 프로그래밍 언어나 환경에 대한 템플릿을 gitignore.io에서 찾아 사용할 수 있습니다.
3. LICENSE -> [라이선스 바로가기](https://github.com/gon1942/how2github/blob/main/00.Basic_Github/02.About_LICENSE.md)
- 목적: 프로젝트에 대한 라이선스를 지정합니다.
- 위치: 저장소의 루트 디렉토리에 위치합니다.
- 팁: 다양한 라이선스 중에서 프로젝트에 적합한 것을 선택합니다. GitHub는 라이선스를 자동으로 인식하고 표시합니다.
4. CONTRIBUTING.md -> [바로가기](https://github.com/gon1942/how2github/blob/main/00.Basic_Github/04.About_CONTRIBUTING.md)
- 목적: 프로젝트에 기여하는 방법에 대한 가이드를 제공합니다.
- 위치: 저장소의 루트 디렉토리에 위치합니다.
- 팁: 기여 프로세스, 코드 스타일, 테스트 방법 등을 명시합니다.
5. .github
- 목적: GitHub Actions 워크플로우, 이슈 및 PR 템플릿 등 GitHub 관련 설정을 저장합니다.
- 위치: .github 디렉토리 안에 위치합니다.
- 팁: 이 디렉토리 안에 workflows/, ISSUE_TEMPLATE/, PULL_REQUEST_TEMPLATE/ 등의 서브 디렉토리를 포함할 수 있습니다.
6. CODE_OF_CONDUCT.md -> [바로가기](https://github.com/gon1942/how2github/blob/main/00.Basic_Github/03.About_CODE_OF_CONDUCT.md)
- 목적: 프로젝트 참여자들에게 기대하는 행동과 원칙을 명시합니다.
- 위치: 저장소의 루트 디렉토리에 위치합니다.
- 팁: GitHub는 코드 행동 강령 템플릿을 제공하므로, 이를 활용하여 작성할 수 있습니다.
&#xa0;

<a href="#top">Back to top</a>

## 깃허브 프로젝트 관리에 필요한 요소들:
1. 이슈 관리 -> [이슈 관리 가이드 클릭!](https://github.com/gon1942/how2github/blob/main/07_%EC%9D%B4%EC%8A%88%EA%B4%80%EB%A6%AC/About_Issue.md)
2. 깃허브 엑션 CI/CD ->  [깃허브 엑션을 이용한 이해 및 사용법 클릭!](https://github.com/gon1942/how2github/tree/main/04.how2-actions)
3. 깃허브 보안관리 -> [깃허브에서 제공하는 보안관리 이해 및 사용법 클릭!](https://github.com/gon1942/how2github/tree/main/05_how2_security)
4. 릴리즈 관리 - [릴리즈 관리 이해 및 사용법 클릭!](https://github.com/gon1942/how2github/tree/main/03.how2-release)



## :white_check_mark: How2Github 폴더 구조 ##

:heavy_check_mark: 00.Basic_Github : 리드미, 라이선스, Code_of_conduct, Contributing, Wiki. - [클릭!](https://github.com/gon1942/how2github/tree/main/00.Basic_Github)\
:heavy_check_mark: 01_how2_SBOM : 깃허브 엑션을 활용한 SBOM - [클릭!](https://github.com/gon1942/how2github/blob/main/01_how2_SBOM/About_Sbom.md)\
:heavy_check_mark: 02_how2_Discussions : 커뮤니케이션을 위한 Discussions - [클릭!](https://github.com/gon1942/how2github/blob/main/02_how2_Discussions/About_Discussions.md)\
:heavy_check_mark: 03.how2-release : 릴리즈 사용법 - [클릭!](https://github.com/gon1942/how2github/tree/main/03.how2-release)\
:heavy_check_mark: 04.how2-actions : CLA, TravisCI, AddContributor, Badge, commitMsg-Chk, Hooks 사용법. -  [클릭!](https://github.com/gon1942/how2github/tree/main/04.how2-actions)\
:heavy_check_mark: 05.how2-template : 
[이슈 템플릿 파일](https://github.com/gon1942/how2github/blob/main/05.how2-template/issue_template.md), 
[커밋 템플릿 파일](https://github.com/gon1942/how2github/blob/main/05.how2-template/commit_template.md), 
[풀리퀘스트 템플릿 파일](https://github.com/gon1942/how2github/blob/main/05.how2-template/pr_template.md) \
:heavy_check_mark: 05_how2_security : Dependabot, Security 사용법 - [클릭!](https://github.com/gon1942/how2github/tree/main/05_how2_security)\
:heavy_check_mark: 06.how2-github : 깃 명령어, 권한 관리 - [클릭!](https://github.com/gon1942/how2github/tree/main/06.how2-github) \
:heavy_check_mark: 07_이슈관리 : 이슈관리 - [클릭!](https://github.com/gon1942/how2github/blob/main/07_%EC%9D%B4%EC%8A%88%EA%B4%80%EB%A6%AC/About_Issue.md)




&#xa0;

<a href="#top">Back to top</a>
