## SECURITY.md
```
SECURITY.md 파일은 오픈 소스 프로젝트에서 보안 문제를 보고하고, 해결하는 방법에 대한 정보를 제공하는 데 사용됩니다.
이 파일은 프로젝트의 사용자나 개발자가 프로젝트와 관련된 보안 문제를 발견했을 때, 어떻게 그 문제를 안전하게 보고할 수 있는지에 대한 지침을 제공합니다.
```

### 정의:
> SECURITY.md는 깃허브 레포지토리에 포함될 수 있는 파일로, 프로젝트의 보안 정책과 절차에 대한 정보를 담고 있습니다.

### 특장점:
> * 투명성: 프로젝트의 보안 절차와 정책에 대한 명확한 정보 제공.
> * 지침 제공: 보안 문제 발생 시 어떻게 대응해야 하는지에 대한 지침을 제공하여 일관된 대응이 가능하게 합니다.
> * 신뢰성 증진: 사용자와 기타 이해당사자에게 프로젝트의 보안에 대한 신뢰를 제공합니다.


### 사용 이유:
```
사용자, 기여자, 이해당사자들에게 프로젝트의 보안 접근 방식을 명확하게 설명하기 위해서.
보안 취약점이 발견될 경우, 안전하고 효과적으로 이를 보고할 수 있는 표준 절차를 제공하기 위해서.
```
### 사용법:
> 레포지토리에 SECURITY.md 파일 생성: 레포지토리의 루트 디렉토리 또는 .github 디렉토리에 이 파일을 생성합니다.
>
> 보안 정책 및 절차 작성:
>   - 보안 취약점을 어떻게 보고해야 하는지에 대한 지침을 명시합니다.
>   - 보고된 취약점에 대한 대응 프로세스를 설명합니다.
>   - 지원되는 버전에 대한 정보를 포함시킬 수 있습니다.
>

> security.md 예시
> # 보안 정책
> ## 지원되는 버전들
> ## 이 프로젝트에서 배포하는 버전 중 보안 취약점 검사를 수행한 버전은 다음과 같습니다.
> | 버전 | 지원 여부           |
> | ---- | ------------------ |
> | 1.2.x  | :white_check_mark: |
> | 1.1.x  | :x:                |
> | 1.0.x  | :white_check_mark: |
> | < 1.0  | :x:                |
> 
> ## 취약점 보고하기
> 
> 취약점을 보고하려면 security@example.com으로 이메일을 보내주세요.
> 
> 저희는 보고된 취약점을 검토하고, 지원되는 버전에 영향을 미치는지 결정할 것입니다. 만약 영향을 미친다면, 저희는 심각도와 영향에 따라 이를 우선 순위에 두게 될 것입니다. 저희는 보고 접수를 확인한 후 48시간 이내에 답변 드리겠습니다.
> 
> 만약 취약점을 검증하게 된다면, 저희는 최대한 빠르게 패치를 배포할 것이며, 보고자가 원한다면 그에게 크레딧을 드릴 것입니다.


### 문서 공개:
```
작성된 SECURITY.md 파일을 레포지토리에 커밋 및 푸시하여 공개합니다.
이렇게 하면, 깃허브 사용자들은 레포지토리의 "Security" > "Security overview" > "view security policy"  프로젝트의 보안 정책을 볼 수 있게 됩니다.
```


![image](https://github.com/gon1942/how2github/assets/31919227/82e0d227-b450-44bb-8cfb-b114079b4ffa)
