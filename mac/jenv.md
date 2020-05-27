# jenv: java 버전 관리 패키지

Node.js를 사용한 분들은 nvm이나 n 등을 떠올리면 될 것 같다.

</br>

### jenv 설치

```zsh
# Homebrew 업데이트
$ brew update && brew upgrade cask

# jenv 설치
$ brew install jenv
```

</br>

### Java 최신버전 설치 (다른 여러 버전 설치 해도 됨)

```zsh
# java 정보 확인
$ brew cask info java

# 자바 설치(위에서 확인한 버전으로 설치됨. 최신 버전)
$ brew cask install java

# 이건 뭐하는 거지? 버전 관련된 뭐인거 같은데 나중에 찾아봐야겠다(20.05.27)
$ brew tap homebrew/cask-versions
```

</br>

설치 후 `~/.zshrc` 에 아래 코드를 추가하여 jenv 초기화

```zsh
# editor로 .zshrc 파일 열기
$ vi ~/.zshrc

# Init jenv
if which jenv > /dev/null; then eval "$(jenv init -)"; fi

# 저장
:wq

# 설정 반영
$ source ~/.zshrc
```

</br>

### jenv가 관리 중인 java 버전 목록 확인

```zsh
$ jenv versions
  system
  14.0
  14.0.1
* openjdk64-14.0.1 (set by /Users/bluuminn/.jenv/version)
```

</br>

### jenv로 관리할 자바 버전 추가

```zsh
# JDK 1.8 추가
$ jenv add /Library/Java/JavaVirtualMachines/adoptopenjdk-8.jdk/Contents/Home/
openjdk64-1.8.0.252 added
1.8.0.252 added
1.8 added
```

</br>

### jenv가 관리 중인 java 버전 목록 재확인

```zsh
$ jenv versions
  system
  1.8
  1.8.0.252
  14.0
  14.0.1
  openjdk64-1.8.0.252
* openjdk64-14.0.1 (set by /Users/bluuminn/.jenv/version)
```

</br>

### java8을 전역으로 설정

```zsh
$ jenv global openjdk64-1.8.0.252
```

</br>

### 설정이 잘 되었는지 확인

```zsh
$ jenv versions
  system
  1.8
  1.8.0.252
  14.0
  14.0.1
* openjdk64-1.8.0.252 (set by /Users/bluuminn/.jenv/version)
  openjdk64-14.0.1
```

</br>

### 디렉토리 별로 다른 버전 설정하기

```zsh
# 해당 디렉토리로 이동 후
$ jenv local [jdk version]
```





참고 블로그

https://jojoldu.tistory.com/329

https://madplay.github.io/post/manage-java-version-using-jenv



### openjdk8 설치

참고 블로그: https://findstar.pe.kr/2019/01/20/install-openjdk-by-homebrew/