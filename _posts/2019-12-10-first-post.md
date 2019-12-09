---
title: "hello world!"
excerpt: "깃허브 사용법"
categories: git
tag: git, github
---



# 1. 깃 시작 할 시에 필수 항목..

git config --global user.name "username"
git config --global user.email "useremail"

위 두 설정은 사용할 username 과 email을 넣게된다.

방법은 간단하게 깃허브 가입시 아이디와 이메일을 넣으면 된다.


# 2. 깃을 이용해서 깃허브에 등록..

git init

git remote remotename https://git저장소.git

git commit -m "커밋할 내용"

git push remotename master




# 3. 브런치 변경

git checkout -b branchname

자동으로 브런치 생성 및 변경해준다.
나중에 프로젝트별 또는 따로 관리해야할 파일이 있을때 사용..




ps.
fisrt Post...

마지막 시간으로 글자 수정해봄..
카테고리 및 태그 넣어봄