## Dependabot 정의

> Dependabot은 GitHub에서 제공하는 보안 기능 중 하나로, 프로젝트의 종속성(dependencies)을 자동으로 업데이트 해주는 도구입니다.
> 
> Dependabot은 프로젝트의 dependencies를 모니터링하여, 새로운 버전이 릴리즈되면 해당 업데이트를 자동으로 제안해줍니다.
> 
> 이를 통해 사용자는 최신의 종속성을 유지하며, 보안 취약점이나 버그를 해결할 수 있습니다.

![image](https://github.com/gon1942/how2github/assets/31919227/0c77398f-0c83-4b23-9e98-ac17349c2506)


### 특장점
```
보안 업데이트: Dependabot은 보안 취약점을 가진 종속성을 자동으로 식별하고 업데이트합니다.
자동 풀 리퀘스트 생성: 새로운 종속성 버전이 발견되면, 해당 업데이트를 반영한 풀 리퀘스트를 자동으로 생성합니다.
커스텀 설정: 사용자는 Dependabot의 설정을 통해 어떤 종속성을 얼마나 자주 업데이트할지 등을 설정할 수 있습니다.
시간 절약: 종속성을 수동으로 관리하는 것에 비해 많은 시간을 절약할 수 있습니다.
라이선스 확인: Dependabot은 종속성의 라이선스를 확인하여, 프로젝트의 라이선스 정책과 호환되는지 체크합니다.
```

### 사용 방법
> Dependabot을 사용하려면, GitHub 레포지토리에서 몇 가지 설정을 해야 합니다.

### Dependabot 설정 파일 생성
> GitHub 레포지토리의 루트 디렉토리에 .github/dependabot.yml 파일을 생성합니다.
> 
> 해당 파일에 원하는 설정을 작성합니다. 예를 들어, 다음과 같이 작성할 수 있습니다:
```
yaml
Copy code
version: 2
updates:
  - package-ecosystem: "npm"
    directory: "/"
    schedule:
      interval: "daily"
```
위 설정은 JavaScript 프로젝트의 종속성을 매일 검사하도록 Dependabot에 지시합니다.

> 설정 옵션
> * package-ecosystem: 사용하는 패키지 매니저를 지정합니다 (예: npm, maven, pip 등).
> * directory: 프로젝트 디렉토리를 지정합니다.
> * schedule: 얼마나 자주 종속성을 검사할지 지정합니다. 가능한 값은 daily, weekly, monthly 등이 있습니다.
> * open-pull-requests-limit: 열린 풀 리퀘스트의 최대 개수를 지정합니다.
