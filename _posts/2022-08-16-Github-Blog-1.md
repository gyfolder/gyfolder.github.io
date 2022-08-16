---
title: Logs of Github Page - 1
author: giyong park
date: 2022-08-16 08:45:00 +0900
categories: [DevLog, Github]
tags: [Series]
---

# Github 블로그 제작 기록

## 개요

![image](/images/20220816/picture-of-blog.jpg)

나만의 웹사이트를 만드는 프로젝트.

큰 기능들에 맞추어 내 블로그 제작 방법을 기록할 것이다.


## 내가 작업한 내용


1. github 계정 만들기 (이미 있다면 로그인하기)
2. '계정 이름.github.io'라는 이름으로 repository 만들기
3. default branch를 main으로 하기
4. 로컬 특정 위치에 clone하기(나는 Github Desktop으로 했다)

여기서부터 [📒Github Blog 만들기-1 (velog.io)](https://velog.io/@hashnsalt/%EC%82%AC%EC%A0%84-%ED%95%99%EC%8A%B5-220731) 사이트를 참고함.

5. ruby3.1.2-1 x86 다운로드 & 설치
6. start command prompt with Ruby에서 cd로 로컬 repository 폴더 경로로 이동했다.
7. ruby에 jekyll 설치. ```> gem install jekyll bundler```
8. (ruby 3.0ver 이상) ruby에 webrick 설치 ```> gem install webrick```
9. jekyll 생성 ```> jekyll new ./``` -> 에러가 뜰 것이다.
10. 로컬 repository 경로 내 파일을 전부 삭제한다. (.git 폴더 제외.)
11. 다시 jekyll 생성 ```> jekyll new ./``` -> 성공
> jekyll 생성 명령어는 jekyll 기본 테마로 한 새로운 페이지를 만들어 줍니다.
12. bundle 설치 ```> bundle install``` 
13. jekyll 서버 작동 ```> bundle exec jekyll serve``` -> 에러가 뜰 수도 있다.
14. webrick 라이브러리 관련 에러고 webrick 설치하면 완료. ```> bundle add webrick```
15. 다시 jekyll 서버 작동 ```> bundle exec jekyll serve``` 
16. jekyll 접속 - 127.0.0.1:4000(또는 localhost:4000) 주소로 들어가면 아까 생성한 웹사이트를 볼 수 있다.

여기서부터 [📒Github Blog 만들기-2 (velog.io)](https://velog.io/@hashnsalt/Github-Blog-%EB%A7%8C%EB%93%A4%EA%B8%B0-2) 사이트를 참고함.

17. 적용하고픈 테마 다운받기. 나는 [jekyll-theme-chripy](https://github.com/cotes2020/jekyll-theme-chirpy) 들어가서 zip로 다운받았다.
18. zip 파일을 풀고 로컬 repository 폴더에 붙여넣었다.
19. 그 후, 로컬 repository에서 삭제해야할 파일들이 있다.
* Gemfile.lock
* docs 폴더
* .travis.tml
* _posts.docs (나는 _posts 폴더가 있었는데 그냥 두었다.)
* .github 폴더에서 workflows 폴더(와 그 하위 디렉터리)만 남기고 나머지 삭제.
* .github/workflows 폴더에서 commitlint.yml과 page-deploy.yml.hook 외에 다 지우기
* page-deploy.yml.hook의 이름을 page-deploy.yml로 변경하기
20. start command prompt with Ruby를 관리자 권한으로 실행한 후 cd로 로컬 repository 폴더 경로로 이동했다.
21. bundle 설치 ```> bundle install``` 
22. _config.yml 파일 수정하기 
* url : 'http://gyfolder.github.io' (내 계정 이름이 gyfolder이므로.)
23. .github/workflows/page-deploy.yml 파일 수정하기 
* branches: - master -> - main으로 변경한다. 
* ruby-version: 2.7 -> 3.1으로 변경한다.(난 3.1버전을 설치했으므로))
24. 로컬 repository 에서 커밋.(git bach 이용하거나 Github Desktop 이용.)
25. gh-pages 브랜치가 새로 생성되고 빌드가 성공하면 github 사이트에서 '계정 이름.github.io' repository로 들어간 후 Settings - Pages - Branch를 gh-pages로 바꿔준다.
26. 주소창에 계정 이름.github.io를 검색하면 아까 로컬로 빌드했었던 모습이 뜰 것이다.
<!--
![image](/images/20220816/picture-of-blog.jpg){: width="1580" height="250" }
-->