# Git & GitHub

**필수 내용**
>김주환, 전소명, 정주영

1. **git과 github의 차이점** 
   - Git: 버전관리 소프트웨어
   - GitHub: Git으로 관리하는 폴더를 웹 상에 올려주는 플랫폼
2. **init,  add, commit -m 명령어들에 대한 설명**
   -  git을 설치하고, 초기설정하기
  
    `$ git config --global user.name "<NAME>"`

    `$ git config --global user.email "<EMAIL>"`
    
    - git repository 생성

    `$ mkdir git-test `

    `$ cd git-test`

    `$ git init`

    - 파일 생성하고, staging 하기
  
    `$ touch test.txt ` 

    `$ git status`     

    - commit해서 하나의 버전으로 만들기 (staged 상태 → committed 상태)
  
    `$ git commit -m "my first commit"`

    `$ git status`

    - 변경된 파일 commit하기 (modified 상태 → staged 상태 → committed 상태)

    `$ echo "My test memo" > test.txt`

    `$ cat test.txt`

    `My test memo`

    `$ git add .`

    `$ git commit -m "My memo file"`

    배운 내용 정리한 [Notion link][nn]입니다.
    
    [nn]: https://www.notion.so/Git-GitHub-56fe7d449448479bbbf7d851f59b1cd8

3. **remote, clone, push, pull 명령어들에 대한 설명**
    - git repository와 git-test 폴더 연결

    `$ git remote add origin https://github.com joowhan/OPAL_test.git`

    - push 하기 
    
    `$ git push -u origin master`

    - clone을 할 경우, `$git clone <repository 주소>` 하면 된다. 
    - pull: 바꾼 부분, 필요한 부분만 pull한다. clone은 전부 복사하는 것이고, pull은 기존 프로젝트에 변화된 내용을 받고 싶을 때 사용한다. 

4. **아래 사진을 첨부하기**  
   
    ![olaf](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSggWRVAXWutTOjtlFO2e7-8y0y5F3orAnTZg&usqp=CAU)

5. **branch, checkout 명령어 설명**
   - 평행세계를 만드는 것이다.
   - Git은 최대한 branch를 만들고, mater branch로 병합하라고 권장한다.
   - branch는 포인터이다. commit들을 pointing하고 있다.
   - Git 은 기본 브랜치로 master 브랜치를 갖고 있는데 이 master 브랜치는 언제나 마지막 커밋을 포인팅하고 있다.
   - git checkout master: branch 전환
   
1. merge 2가지 설명 (fast-forward/Merge conflict)
    
    | merge | fast-forward | Merge conflict |
    |:---:|---:|---:|
    | master branch가 수정되었는가?|X|O|
    | | master branch가 다른 branch가 commit하고 있는 것을 포인팅 하고 있는 경우|master와 다른 branch에도 수정사항이 있어 병합 시 충돌이 일어나는 경우|
