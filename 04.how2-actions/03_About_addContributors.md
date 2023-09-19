## Contributors
> GitHub 리포지토리에 대한 기여자의 프로필 및 관리 정보를 정의하는 데 사용되는 파일입니다.
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

### Add Contributor in README.md 
```
name: Add contributors
on:
  schedule:
    - cron:  '* * * * *' #분 시 일 월 요일
  push:
   branches:
     - master

jobs:
  add-contributors:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - uses: BobAnkh/add-contributors@master
      with:
        CONTRIBUTOR: '### Contributors'
        COLUMN_PER_ROW: '8'
        ACCESS_TOKEN: ${{secrets.GITHUB_TOKEN}}
        IMG_WIDTH: '100'
        FONT_SIZE: '14'
        PATH: '/README.md'
        COMMIT_MESSAGE: 'docs(README): update contributors'
        AVATAR_SHAPE: 'round'
```
