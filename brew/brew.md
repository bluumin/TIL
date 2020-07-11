# homebrew



## Homebrew 설치하기

아래 내용을 터미널에 붙여넣기. homebrew 자동 설치 됨.

```zsh
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```



## 리스트로 한번에 설치하기

```zsh
# 리스트 만들기
$ brew cask list > app_list.txt

# 설치 (갖고 있는 list가 있어야 할 것 같다.)
$ brew cask install $(cat app_list.txt)
```