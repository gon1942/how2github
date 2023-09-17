### hooks settings ###

1. 스크립트를 사용하여 설정
```
hooks/setup_hooks.sh 
```


2. git clone 시 --template 옵션 사용
```
git hooks directory 생성 후 클론시 사용
git clone --template=<git_hooks_templates_directory> https://github.com/gon1942/opensource.git
```

3. husky 사용
```
1,2번은 개발자가 설정은 한다고해도 실질적으로 사용을 안할수잇어 강제적으로 hook을 사용하도록 해야한다.
즉, Git Hooks 을 적용하지 않을 가능성이 크다.

프로젝트가 불특정다수에게 공개한 프로젝트라면 작업자가 Git Hooks 를 적용했는지 관리 감독하기가 더욱 어려워진다.

Git Hooks 을 반드시 적용하게끔 강제할 수는 없을까? 만약 프로젝트가 모듈 의존성을 관리하기 위해 npm 을 사용하고 있다면 husky 은 좋은 선택이 될 수 있다.


1. husky 설치
$ npm install --save-dev husky
-- npx husky-init && npm install > package.json script 에 'husky install' 등록됨.

2. commit 정책을 정의한다. .huskyrc 파일에 정의하고자 하는 훅과 실행할 명령어를 지정

.huskyrc

{
    "hooks": {
        "pre-commit": "echo 'Hello Gabia, woof!'"
    }
}

-- :npx husky add .husky/pre-commit 'echo "Hello Husky"'

```

