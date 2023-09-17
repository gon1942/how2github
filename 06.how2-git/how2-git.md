<table>
<tr>
    <td align="center" style="word-wrap: break-word; width: 150.0; height: 150.0">
        <a href=https://github.com/gon1942>
            <img src=https://avatars.githubusercontent.com/u/31919227?v=4 width="100;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=Ryan-K/>
            <br />
            <sub style="font-size:14px"><b>Ryan-K</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 150.0; height: 150.0">
        <a href=https://github.com/1942kg>
            <img src=https://avatars.githubusercontent.com/u/24218451?v=4 width="100;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=1942kg/>
            <br />
            <sub style="font-size:14px"><b>1942kg</b></sub>
        </a>
    </td>
    <td align="center" style="word-wrap: break-word; width: 150.0; height: 150.0">
        <a href=https://github.com/suyun1017>
            <img src=https://avatars.githubusercontent.com/u/93955272?v=4 width="100;"  style="border-radius:50%;align-items:center;justify-content:center;overflow:hidden;padding-top:10px" alt=suyun1017/>
            <br />
            <sub style="font-size:14px"><b>suyun1017</b></sub>
        </a>
    </td>
</tr>
</table>

# git_command

git 명령어 모음

저장소 생성
```bash
git init
```

원격 저장소로부터 복제
```bash
git clone remoteurl
```

변경 사항 체크
```bash
git status
```

특정 파일 스테이징
```bash
- git add 파일명
- git add * 
```

커밋
```bash
- git commit -m “내용” 
- git push origin master 
```

원격저장소 추가
```bash
git remote add origin 원격서버주소
```

커밋 정렬(rebase)
```bash
git rebase -i HEAD~3 (최신 3개의 커밋을 하나로 정렬
```

커밋 메세지 수정
```bash
- git commit --amend ( editor로 수정 ) 
- git commit --amend -m 커밋내용 ( 바로 수정 )
- git push
```

브랜치 목록
```bash
- git branch  (로컬)
- git branch -r (리모트)  
- git branch -a (로컬  리모트)
```
브랜치 생성
```bash
- git branch new master (master > new branch)
```
브랜치 삭제
```bash
- git branch -D DeleteBranchName (local)
- git push origin :DeleteBranchName (remote)

- git push origin --delete DeleteBranchName
```

