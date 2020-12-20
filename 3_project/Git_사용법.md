# Git 사용법

## 맨 처음 하셔야 할 일(`Git clone` 받고 한 번만 하면 됩니다.)

1. git clone 주소
2. git remote add 주소
3. git remote update
4. git fetch
5. git fetch origin
6. git checkout develop
7. git checkout -b feature/브랜치명 dev

<br/>

## `feature/브랜치명`에 `push` 하기

1. git pull origin develop

   > develop에 push된 다른 사람들의 수정사항을 반영하기위해 해준다.
   >
   > 만약, pull하지 않고 git add . 해서 모든 파일이 올라갈 경우 **ERROR** 날 수도 있다.

2. git add 수정한 파일 이름

   > `ex` ~/folder1/folder2/file.py 인 경우
   >
   > - git bash를 연 위치가 `~` 일 때
   >
   >   **git add folder1/folder2/file.py**
   >
   > - git bash를 연 위치가 `folder2` 일 때
   >
   >   **git add file.py**

3. git commit -m "jira-number 커밋"

   > `ex` S02P22C107의 Board에서 31번의 Story를 만들었다면,
   >
   > **git commit -m "S02P22C107-31 커밋 내용 작성하기"**
   >
   > 이렇게 작성하면 된다.

4.  git push origin feature/브랜치명

   > `feature/브랜치명`에 수정사항을 올린다.

<br/>

## `feature/브랜치명`의 내용을 `Develop`에 `Merge` 요청 보내기

1. git checkout develop

2. **git pull origin develop**

3. Gitlab에 접속합니다.

4. Merge Requests를 클릭합니다.

   > ![image-20200403111450175](assets/image-20200403111450175.png)

5. 상단에 있는 초록색 버튼(New merge request)를 클릭한다.

   > ![image-20200403111542741](assets/image-20200403111542741.png)

6. Source branch에는 merge를 요청하고자하는 **feacher/브랜치명**을 선택한다.

   > ![image-20200403111813321](assets/image-20200403111813321.png)

7. Target branch에는 **develop를 선택**한다.

   > ![image-20200403111905392](assets/image-20200403111905392.png)

8. 그 다음 초록색 버튼(Compare branches and continue) 버튼을 누른다.

   > ![image-20200403111959522](assets/image-20200403111959522.png)

9. 다음 페이지로 넘어가면, branch들이 맞게 들어갔는지 확인 후

   > ![image-20200403113251293](assets/image-20200403113251293.png)

10. 제출하면 된다.

    > ![image-20200403113321551](assets/image-20200403113321551.png)

<br/>

## 새로운 feature/브랜치명 따기

> 작업하는 내용이 달라진다면, 헷갈리지 않게 feature를 새로 만들어 진행하는 것이 좋다.

1. git checkout -b feature/브랜치명 develop

<br/>

개발은 각자의 `feature/브랜치명`에서 해주시고 git push 하기 전 꼭 **pull **하십시오.

feature의 내용을 merge하고 싶으시다면 위와 같이 진행한 후 **머지 요청한다는 말씀 부탁드립니다.**