- [SBOM](#sbom)
  * [SBOM의 필수 구성요소](#sbom%EC%9D%98-%ED%95%84%EC%88%98-%EA%B5%AC%EC%84%B1%EC%9A%94%EC%86%8C)
  * [SBOM의 특장점](#sbom%EC%9D%98-%ED%8A%B9%EC%9E%A5%EC%A0%90)
  * [SBOM의 필요성](#sbom%EC%9D%98-%ED%95%84%EC%9A%94%EC%84%B1)
- [제품에 SBOM 관리를 적용하는 방법](#%EC%A0%9C%ED%92%88%EC%97%90-sbom-%EA%B4%80%EB%A6%AC%EB%A5%BC-%EC%A0%81%EC%9A%A9%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95)
- [국내외 SPDX 관련 표준](#%EA%B5%AD%EB%82%B4%EC%99%B8-spdx-%EA%B4%80%EB%A0%A8-%ED%91%9C%EC%A4%80)
- [SBOM (Software Bill of Materials) 관리](#sbom-software-bill-of-materials-%EA%B4%80%EB%A6%AC)
  * [SPDX 생성 도구](#spdx-%EC%83%9D%EC%84%B1-%EB%8F%84%EA%B5%AC)
  * [CycloneDX 생성 도구](#cyclonedx-%EC%83%9D%EC%84%B1-%EB%8F%84%EA%B5%AC)
  * [GitHub Actions를 사용한 SBOM 생성 및 업로드](#github-actions%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-sbom-%EC%83%9D%EC%84%B1-%EB%B0%8F-%EC%97%85%EB%A1%9C%EB%93%9C)
  * [Trivy 스캐너를 사용한 SBOM 생성 및 업로드](#trivy-%EC%8A%A4%EC%BA%90%EB%84%88%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-sbom-%EC%83%9D%EC%84%B1-%EB%B0%8F-%EC%97%85%EB%A1%9C%EB%93%9C)

   
## SBOM

미국의 국가 사이버 보안 강화 지침(2021년 5월)이 배포된 이후, 미국 정부의 요청으로 미국의 90여개 소프트웨어 기업과 오픈소스 커뮤니티가 자문에 참여하여 의견을 제시하였습니다. CISA와 NTIA에서는 이를 정리하여 [SBOM과 관련한 가이드라인 및 FAQ](https://www.ntia.gov/SBOM)를 공개하였습니다.

SBOM은 Software Bill of Materials의 약자로, 소프트웨어 제품이 어떤 구성요소로 이루어져 있는지 상세하게 명시한 명세서입니다.
SBOM은 소프트웨어의 구성요소, 그 구성요소의 버전, 출처, 라이선스 등에 대한 정보를 포함합니다.


### SBOM의 필수 구성요소

- Supplier name
- Component name
- Version of the component
- Cryptograph hash of the component
- Any other unique identifier
- Dependency relationship
- Author of the SBOM data


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


## 제품에 SBOM 관리를 적용하는 방법

### 1) 식별 및 추적

- 외부 컴포넌트를 식별하고, 해당 컴포넌트의 라이선스와 보안 취약점을 추적합니다.

### 2) SBOM 생성

- 선택한 표준(SDPX 또는 CycloneDX)에 따라 SBOM을 생성합니다.

### 3) 검증 및 업데이트

- SBOM의 정확성을 검증하고, 외부 컴포넌트가 업데이트될 때마다 SBOM도 업데이트합니다.

### 4) 제품 통합

- SBOM 정보를 제품의 문서나 설정 파일에 포함시켜 배포합니다.

### 5) 모니터링

- 지속적으로 외부 컴포넌트의 라이선스 및 보안 취약점을 모니터링하고, 필요한 경우 SBOM을 업데이트합니다.


## 국내외 SPDX 관련 표준

### [TTAK.KO-11.0309 공개 소프트웨어 공급망 관리를 위한 소프트웨어 목록 구성(SBOM) 속성 규격](https://committee.tta.or.kr/data/standard_view.jsp?secondDepthCode=PG602&firstDepthCode=TC6&pk_num=TTAK.KO-11.0309&commit_code=PG602)

### SPDX (Software Package Data Exchange)

- SPDX는 소프트웨어 패키지의 라이선스, 저작권, 보안 취약점 등의 메타데이터를 표준화하는 포맷입니다.

### CycloneDX

- CycloneDX는 소프트웨어 공급망의 컴포넌트 정보를 XML 또는 JSON 형식으로 제공하는 표준입니다.


## SBOM (Software Bill of Materials) 관리

### SPDX 생성 도구

- [SPDX Tools](https://github.com/spdx/tools-java)
- [FOSSology](https://github.com/spdx/tools-python)

### CycloneDX 생성 도구

- [CycloneDX Maven Plugin](https://github.com/CycloneDX/cyclonedx-web-tool)
- [CycloneDX Node Module](https://cyclonedx.org/tool-center/)

### GitHub Actions를 사용한 SBOM 생성 및 업로드
> 1. GitHub Actions Workflow 설정:\
> - 워크플로우를 구성하는 .yml 파일을 생성합니다.\
> - 이 파일은 .github/workflows 디렉토리에 위치해야 합니다.
> 
> 2. SBOM 생성 단계:
> - 워크플로우의 한 단계에서, SBOM 생성 도구를 사용하여 SBOM을 생성합니다.\
> - 예를 들어, Microsoft의 sbom-tool을 사용할 수 있습니다.
> 3. SBOM 업로드 단계:
> - 생성된 SBOM을 GitHub Artifacts 또는 다른 저장소에 업로드합니다.

#### 샘플 파일을 이용하는 법
[sbom.yml](./sbom.yml) 파일의 내용은 아래와 같이 작성되어 있습니다.

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

1) 이 샘플 파일의 내용 중 `<YourProjectName>` 을 프로젝트의 이름으로 변경하고,\
`<YourName>`을 소프트웨어 소유자의 이름으로 변경합니다.\
2) 변경한 sbom.yml 파일을 .github/workflows/하위에 복사합니다.\
3) sbom.yml 워크플로우가 실행이 되면 Github Artifacts 와 레포지토리에 업로드된 SBOM을 확인하실 수 있습니다.

![image](https://github.com/gon1942/how2github/assets/31919227/c7cba1fc-51b5-4d40-8d5f-40155d32a23c)


### Trivy 스캐너를 사용한 SBOM 생성 및 업로드

- Trivy는 알려진 취약성 및 라이선스 정보를 스캔하여 제공하는 오픈 소스 보안 스캐너입니다.

#### 설치 및 준비

```bash
curl -sfL https://raw.githubusercontent.com/aquasecurity/trivy/main/contrib/install.sh | sh -s -- -b /usr/local/bin
```

#### 스캔 및 SBOM 파일 생성
```bash
Copy code
git clone https://github.com/<your_username>/<your_project>.git
cd <your_project>
trivy fs --format json . > sbom.json
```

#### 결과 확인
스캔이 완료되면 sbom.json 파일이 프로젝트 디렉터리에 생성됩니다.



