## Contributors
> GitHub 리포지토리에 대한 기여자의 프로필 및 관리 정보를 정의하는 데 사용되는 파일입니다.\
> 이 파일을 사용하여 리포지토리 기여자의 정보를 구성하고 관리할 수 있습니다. 


### 필요성 및 사용 이유:
> * 기여자 프로필 개선: contributor.yml 파일을 사용하면 기여자의 프로필을 개선할 수 있습니다. 이를 통해 기여자들의 이름, 이메일 주소, 직무, 아바타 이미지 등을 정의하고 표시할 수 있습니다.
> * 기여자 관리: 리포지토리에 여러 기여자가 있는 경우, contributor.yml 파일을 사용하여 모든 기여자의 정보를 중앙 집중화하고 업데이트할 수 있습니다.
> * 리포지토리 소개 개선: 기여자 정보를 추가하면 리포지토리 소개 페이지에서 더 많은 정보를 제공할 수 있으며, 이를 통해 프로젝트의 투명성을 높일 수 있습니다.


### 장점:
> * 투명성과 신뢰성 향상: 기여자 정보를 명시적으로 제공함으로써 프로젝트의 투명성을 높이고, 기여자에 대한 신뢰를 증가시킵니다.
> * 프로젝트 인지도 향상: 기여자 프로필 및 정보를 제공하면 프로젝트가 눈에 띄고 인지도를 향상시킬 수 있습니다.
> * 기여자 관리 용이성: 다수의 기여자와 작업할 때, contributor.yml 파일을 사용하여 기여자 정보를 관리하고 업데이트하기가 용이합니다.
> * GitHub의 contributor.yml 파일을 사용하면 프로젝트 관리와 커뮤니케이션을 개선하고, 기여자들을 인정하고 존중하는데 도움이 됩니다.

### How.. Contributor.yml 
> * cat .github/workflows/contributor.yml
> * 일정시간 간격으로 워크플로우를 실행하거나 메인브랜치에 푸시 이벤트가 발생할경우 README.md 파일에 컨트리뷰터의 프로필을 표시.
```
name: Add contributors # 이 워크플로우의 이름입니다.

on:
  schedule:
    - cron:  '* * * * *' # 일정한 시간 간격으로 워크플로우 실행 (분 시 일 월 요일)
  push:
   branches:
     - master # 'master' 브랜치에 푸시 이벤트가 발생하면 워크플로우 실행

jobs:
  add-contributors:
    runs-on: ubuntu-latest # GitHub Actions에서 사용할 런타임 환경 (Ubuntu Latest)
    steps:
    - uses: actions/checkout@v2 # 리포지토리 체크아웃 액션 사용 (현재 워크플로우의 스크립트를 실행하기 위해 리포지토리를 체크아웃)
    - uses: BobAnkh/add-contributors@master # BobAnkh/add-contributors 리포지토리의 액션을 사용합니다.
      with:
        CONTRIBUTOR: '### Contributors' # README.md 파일에 추가될 컨트리뷰터 섹션의 제목
        COLUMN_PER_ROW: '8' # 컨트리뷰터 아바타 이미지를 몇 개의 열로 나타낼 것인지 설정
        ACCESS_TOKEN: ${{secrets.GITHUB_TOKEN}} # GitHub 토큰을 사용하여 액션을 실행할 수 있는 권한을 부여합니다.
        IMG_WIDTH: '100' # 아바타 이미지의 너비 설정
        FONT_SIZE: '14' # 텍스트의 글꼴 크기 설정
        PATH: '/README.md' # README.md 파일의 경로를 설정
        COMMIT_MESSAGE: 'docs(README): update contributors' # 커밋 메시지 설정
        AVATAR_SHAPE: 'round' # 아바타 이미지 모양 설정 (round 또는 square)
```
