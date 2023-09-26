## SBOM
```
SBOM은 Software Bill of Materials의 약자로, 소프트웨어 제품이 어떤 구성요소로 이루어져 있는지 상세하게 명시한 명세서입니다.
SBOM은 소프트웨어의 구성요소, 그 구성요소의 버전, 출처, 라이선스 등에 대한 정보를 포함합니다.
```

### SBOM의 특장점:
> * 투명성: SBOM은 소프트웨어의 구성요소와 그 구성요소의 관계에 대한 명확한 이해를 제공하여, 소프트웨어의 투명성을 증가시킵니다.
>
> * 보안: SBOM을 통해 소프트웨어에 포함된 취약한 구성요소를 식별하고, 이를 수정하여 보안 위험을 관리할 수 있습니다.
>
> * 라이선스 관리: SBOM은 각 구성요소의 라이선스 정보를 제공하여, 라이선스 위반의 위험을 줄이고 법적 준수를 보장합니다.
>
> * 유지보수와 업데이트: SBOM을 통해 구성요소의 버전 정보를 얻을 수 있어, 필요에 따라 업데이트 및 유지보수를 수행할 수 있습니다.


### SBOM의 필요성:
> * 공급망 보안: 현대의 소프트웨어는 수많은 오픈소스와 서드파티 구성요소를 사용합니다. 이러한 구성요소 중 하나에 보안 취약점이 발견되면 전체 시스템이 위험에 노출될 수 있습니다. 
SBOM은 이러한 구성요소의 보안 상태를 평가하고 관리할 수 있게 합니다.
>
> * 법적 준수: 여러 라이선스 요구사항을 충족시키기 위해, 소프트웨어 개발자와 사용자 모두가 소프트웨어의 구성요소와 그 라이선스를 이해해야 합니다.
>
> * 신뢰성과 품질관리: 소프트웨어의 구성요소와 그 구성요소의 품질을 이해하면, 개발자는 더 높은 품질의 소프트웨어 제품을 제공할 수 있습니다.
>
> * 사이버 보안과 레지린시: 소프트웨어 구성요소의 취약점을 식별하고 대응함으로써, 기업은 사이버 위협으로부터 보호받을 수 있으며, 사이버 공격에 더 강력하게 대응할 수 있습니다.


### 예시: GitHub Actions를 사용한 SBOM 생성 및 업로드
> 1. GitHub Actions Workflow 설정:\
> - 워크플로우를 구성하는 .yml 파일을 생성합니다.\
> - 이 파일은 .github/workflows 디렉토리에 위치해야 합니다.
> 
> 2. SBOM 생성 단계:
> - 워크플로우의 한 단계에서, SBOM 생성 도구를 사용하여 SBOM을 생성합니다.\
> - 예를 들어, Microsoft의 sbom-tool을 사용할 수 있습니다.
> 3. SBOM 업로드 단계:
> - 생성된 SBOM을 GitHub Artifacts 또는 다른 저장소에 업로드합니다.

```
name: Generate and Upload SBOM

on:
  push:
    branches: [ master ]

jobs:
  generate-and-upload-sbom:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2
    
    - name: Generate SBOM
      run: |
        curl -Lo ./sbom-tool https://github.com/microsoft/sbom-tool/releases/latest/download/sbom-tool-linux-x64
        chmod +x ./sbom-tool
        ./sbom-tool generate -b . -bc . -pn <YourProjectName> -pv 1.0.0 -ps YourName

    - name: Upload SBOM
      uses: actions/upload-artifact@v2
      with:
        name: sbom
        path: ./_manifest/spdx_2.2/
```
> 이 예제에서는 <YourProjectName> 을 프로젝트의 이름으로 교체하고,\
> <YourName>을 소프트웨어 소유자의 이름으로 교체합니다.\
> .github/workflows/하위에 워크플로우 작성합니다.\
> Sbom.yml 워크플로우가 실행이 되면 Github Artifacts 와 레포지토리에 업로드된 SBOM을 확인하실 수 있습니다.
>

![image](https://github.com/gon1942/how2github/assets/31919227/c7cba1fc-51b5-4d40-8d5f-40155d32a23c)
