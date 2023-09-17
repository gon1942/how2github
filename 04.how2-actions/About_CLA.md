# Contributor License Agreement  CLA(기여자 라이선스 계약) 

- 위키백과 사전에서는 "기여자 라이선스 동의(Contributor License Agreement, CLA)는 지식 재산권이 회사/프로젝트(일반적으로 오픈 소스 사용권을 준수하는 소프트웨어)에 기여되는 조항을 정의한다."라고 명시.
- 오픈 소스 프로젝트를 유지 관리하는 경우 프로젝트 기여자에 대한 묵시적 계약을 제공하는 반면, 기여자 라이선스 계약(CLA)은 이러한 조건을 명시하고 이러한 계약의 기록을 제공합니다.
- 모든 오픈소스 프로젝트에 CLA를 추가할 필요는 없다. 프로젝트의 속성(상업,비상업)에 따라 추가를 하면 됨.
```
# DCO
 - CLA의 대안으로 DCO(Developer Certificate of Origin) 방식이 있습니다.
* DCO 방식은
  - git에서 -S(--signoff) 플래그로 자신의 기여에 서명하는 방식.
  - 해당 커밋에만 적용됨.

```


## CLA 목적 
```
- Wikipedia
CLA의 목적은 프로젝트 결과물의 보호자가 선택한 라이선스에 따라 배포할 수 있도록 모든 기여에 대해 필요한 소유권 또는 권한 부여를 갖도록 하는 것입니다.
```



### CLA_BOT ( 승인된 기여자에 대해 pull request을 확인하는 봇 )
```
- cla-bot은 기여자 라이선스 계약(CLA) 자동화를 위한 GitHub 애플리케이션입니다. 기여자가 계약에 서명했는지 확인하고 PR이 있는 경우 PR에 레이블을 추가하거나 서명하지 않은 경우 서명을 요청합니다.
- CLA 리포지토리별로 설정할 수 있으며,  풀 요청을 통과하기 전에 모든 기여자가 CLA에 동의해야 합니다.
```



## CLA 구성
1. .github/workflows/cla.yml 파일 생성
```
name: "CLA Assistant"
on:
  issue_comment:
    types: [created]
  pull_request_target:
    types: [opened,closed,synchronize]

jobs:
  CLAssistant:
    runs-on: ubuntu-latest
    steps:
      - name: "CLA Assistant"
        if: (github.event.comment.body == 'recheck' || github.event.comment.body == 'I AGREE this CLA') || github.event_name == 'pull_request_target'
        # Beta Release
        uses: cla-assistant/github-action@v2.1.3-beta
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          # the below token should have repo scope and must be manually added by you in the repository's secret
          PERSONAL_ACCESS_TOKEN : ${{ secrets.PERSONAL_ACCESS_TOKEN }}
        with:
          path-to-signatures: 'cla/signatures/version1/cla.json'
          path-to-document: 'https://github.com/gon1942/test/blob/master/cla/cla.md' # e.g. a CLA or a DCO document
          # branch should not be protected
          branch: 'master'
          allowlist: bot*

         #below are the optional inputs - If the optional inputs are not given, then default values will be taken
          ##remote-organization-name: enter the remote organization name where the signatures should be stored (Default is storing the signatures in the same repository)
          ##remote-repository-name:  enter the  remote repository name where the signatures should be stored (Default is storing the signatures in the same repository)
          #create-file-commit-message: 'For example: Creating file for storing CLA Signatures'
          #signed-commit-message: 'For example: $contributorName has signed the CLA in #$pullRequestNo'
          custom-notsigned-prcomment: "\n\n프로젝트에 기여해 주셔서 감사합니다! 요청해 주신 PR을 반영하기 이전에, [Contributor License Agreements](https://ko.wikipedia.org/wiki/%EA%B8%B0%EC%97%AC%EC%9E%90_%EB%9D%BC%EC%9D%B4%EC%84%A0%EC%8A%A4_%EB%8F%99%EC%9D%98)에 동의해 주셔야 합니다. [해당 문서](https://github.com/gon1942/test/blob/master/cla/cla.md)를 확인하신 후, 댓글로 아래 문구(I AGREE this CLA)를 남겨주시면 CLA 사인이 완료됩니다.\n\nThank you for your pull request and welcome to our community! We require contributors to sign our [Contributor License Agreement](https://en.wikipedia.org/wiki/Contributor_License_Agreement). After checking [this document](https://github.com/gon1942/test/blob/master/cla/cla.md), please leave the following statement(I AGREE this CLA) in the comments to complete the CLA signature."
          custom-pr-sign-comment: 'I AGREE this CLA.'
          #custom-allsigned-prcomment: 'pull request comment when all contributors has signed, defaults to **CLA Assistant Lite bot** All Contributors have signed the CLA.'
          #lock-pullrequest-aftermerge: false - if you don't want this bot to automatically lock the pull request after merging (default - true)
          #use-dco-flag: true - If you are using DCO instead of CLA


```
### 옵션 설명.
```
1. 'I AGREE this CLA' 는 기여자가 댓글로 달 문구. 해당 문구는 변경 가능하다.
2. GITHUB_TOKEN 은 해당 액션이 자동으로 생성, 사용하므로 직접 등록해 두지 않아도 된다.
3. PERSONAL_ACCESS_TOKEN 은 직접 해당 레포지토리의 settings/Secrets 에 PERSONAL_ACCESS_TOKEN 을 등록해 두어야 한다.
4. path-to-signatures 는 CLA에 사인을 완료한 사용자의 정보를 저장하는 json 파일의 위치를 의미합니다.
5. path-to-document 는 CLA 사인을 미완료한 기여자에게 달리는 댓글에서 안내할 CLA 문서의 링크를 의미합니다.
6. branch 는 위의 path-to-signatures 파일을 가질 branch 명입니다.
7. allowlist는 CLA 사인을 하지 않아도 PR을 자동 허용할 사용자 리스트입니다. bot의 pr은 CLA 체크를 하지 않도록 설정합니다.
8. custom-notsigned-prcomment 는 CLA 사인을 완료하지 않은 기여자가 PR을 요청했을때 댓글로 달릴 문구입니다. 해당 문구에서 CLA문서 링크와 사인 방법을 안내해야 합니다.
9. custom-pr-sign-comment 는 기여자가 CLA 사인을 완료했다는 의미로 PR의 댓글로 달 문구입니다. 해당 문구가 댓글로 달리면 github action이 이를 반영합니다.
```

