# homebrew



## Homebrew 설치하기

아래 내용을 터미널에 붙여넣기. homebrew 자동 설치 됨.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```



## brew로 프로그램 설치하기



### Java 설치

1. Homebrew Cask

Home-brew 최신 업데이트

```brew update && brew upgrade cask```

2. Install Java Latest

brew로 Java 최신 버전 설치

```brew cask info java```

![image-20200513181733023](/Users/bluuminn/Library/Application Support/typora-user-images/image-20200513181733023.png)

> 2020.05.13 기준 최신 버전 14.0.1

```brew cask install java```

​	최신 버전의 java가 설치됨

![image-20200513182008259](/Users/bluuminn/Library/Application Support/typora-user-images/image-20200513182008259.png)



3. Install jenv

jenv: java 버전 관리 패키지

> Node.js를 사용한 분들은 nvm이나 n 등을 떠올리면 될 것 같다.

brew install jenv

설치 후에 ~/.bash_profile에 아래 코드를 추가하여 jenv 초기화



참고: https://jojoldu.tistory.com/329



### openjdk8 설치

참고 블로그: https://findstar.pe.kr/2019/01/20/install-openjdk-by-homebrew/