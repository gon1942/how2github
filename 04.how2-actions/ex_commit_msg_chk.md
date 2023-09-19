
## Commit Msg Check
> 커밋 메시지 체크 워크플로우는 소프트웨어 개발 프로세스에서 사용되는 자동화 도구 또는 시스템입니다. 이 워크플로우는 다음과 같은 주요 목적으로 사용됩니다.

### 목적:
> 커밋 메시지 체크 워크플로우의 주요 목적은 올바른 커밋 메시지를 작성하고 일관성 있는 커밋 메시지 스타일을 유지하는 것입니다. 이를 통해 코드의 품질과 가독성을 향상시키며, 협업과 관리를 더욱 효율적으로 만듭니다.

### 주요 기능과 특징:

> 1. 커밋 메시지 패턴 확인: 워크플로우는 정해진 커밋 메시지 패턴 또는 규칙을 확인합니다. 이 패턴은 커밋 메시지의 형식과 구조를 지정하며, 주로 다음과 같은 내용을 체크합니다.
>     * 커밋 타입 (예: feat, fix, chore, docs 등)  
>     * 변경 사항의 요약
>     * 선택적으로 본문과 연관된 이슈 또는 문제 번호
> 2. 커밋 메시지 일관성 유지: 워크플로우는 팀 내에서 커밋 메시지 스타일이 일관되게 유지되도록 돕습니다. 이는 개발자들이 일관된 방식으로 커밋 메시지를 작성하고 프로젝트 표준을 준수할 수 있도록 합니다.
> 3. 품질 제어: 올바른 커밋 메시지 작성을 강제함으로써, 코드 변경 사항의 목적과 의도를 명확하게 설명하고, 코드 품질을 향상시킵니다. 이는 코드 리뷰와 버그 추적을 더욱 효과적으로 수행하는 데 도움이 됩니다.
> 4. 알림 및 피드백 제공: 워크플로우는 올바르지 않은 커밋 메시지를 감지하면 해당 커밋에 대한 피드백을 제공하거나, 작성자에게 알림을 보내어 수정을 요청할 수 있습니다.
> 5. 자동화 및 통합: CI/CD 파이프라인과 통합하여, 코드가 빌드 및 배포되기 전에 커밋 메시지 규칙을 체크하고, 만족하지 않는 경우 자동으로 빌드를 실패하도록 설정할 수 있습니다.
> 6. 보안 강화: 커밋 메시지 체크를 통해 보안 문제나 민감한 정보가 커밋 메시지에 노출되는 것을 방지하여 보안을 강화할 수 있습니다.

## Sample Commit Msg Chk
```
name: 'Commit Message Check'
on:
  pull_request:
    types:
      - opened
      - edited
      - reopened
      - synchronize
  pull_request_target:
    types:
      - opened
      - edited
      - reopened
      - synchronize
  push:
    branches:
      - main
      - 'releases/*'

jobs:
  check-commit-message:
    name: Check Commit Message
    runs-on: ubuntu-latest
    steps:
      - name: Check Commit Type
        uses: gsactions/commit-message-checker@v1
        with:
          #pattern: '\[[^]]+\] .+$'
          pattern: '(Feat|feat|Fix|fix|Design|design|Style|style|Refactor|refactor|Comment|comment|Docs|docs|Test|test|Chore|chore|Rename|rename|Remove|remove) .+$'
          flags: 'gm'
          error: 'need Your first line has to contain a commit type like "[BUGFIX]".'
          
  run-if-fail:
    if: ${{ always() && (needs.check-commit-message.result=='failure') }}
    needs: [check-commit-message]
    runs-on: ubuntu-latest
    env: 
      PR_NUMBER: ${{ github.event.number }}
    steps:
      - uses: actions/github-script@v3
        with:
          github-token: ${{secrets.GITHUB_TOKEN}}
          script: |
            github.issues.createComment({
              issue_number: ${{ env.PR_NUMBER }},
              owner: context.repo.owner,
              repo: context.repo.repo,
              body: '요청해 주신 PR이 [하모나이즈 프로젝트의 커밋 컨벤션](https://github.com/hamonikr/hamonize/blob/master/.gitmessage.txt)을 위반합니다. \n
              커밋 메시지와 PR title에 다음 Commit Type 중 하나를 포함해 주세요. \n
              Feat Fix Design Style Refactor Comment Docs Test Chore Rename Remove'
            })
``` 

