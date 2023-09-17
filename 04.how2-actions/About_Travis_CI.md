# CI(Continuous Integration)은
- 소프트웨어어를 개발하면서 무엇인가를 수정할 때, 이를 전체 시스템에 반영 후 테스트 및 빌드를 수행하여 이상이 없는지 지속적으로 검사하는 것을 말합니다.
- Travis는 github에서 webhook을 받아 ci를 자동화해주는 서비스이다.
- github에서 repository에 webhook을 걸어주고 .travis.yml 파일에 환경과 빌드스크립트를 지정해놓으면
   자동으로 가상환경을 만들어 프로젝트를 빌드하고 테스트한다.
   
![Deepin스크린샷_선택 영역_20220113101226](https://user-images.githubusercontent.com/31919227/149248100-593f23bf-3acb-4f4e-964d-7aae2e45b52a.png)

