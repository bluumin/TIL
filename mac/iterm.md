# iTerm





## brew 로 iTerm 설치

```bash
brew cask install iterm2
```





## iTerm 설치 후 zsh 등 터미널 설정

zsh update & zsh-completions 설치

brew install zsh zsh-completions



oh-my-zsh 설치

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```





**플러그인**

oh-my-zsh의 가장 강력한 점은 플러그인입니다. [기본 플러그인](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins)외에 명령어 하이라이팅 플러그인 [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)과 자동완성 플러그인 [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)을 설치합니다.

```
# zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# zsh-autosuggestions
git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
```



플러그인을 설치하면 반드시 `~/.zshrc`파일에 설정을 해야합니다. 파일을 열고 `plugins`항목에 플러그인을 추가합니다.

```
plugins=(
  git
  zsh-syntax-highlighting
  zsh-autosuggestions
)
```

설정 파일을 수정했으면 터미널을 재시작하거나 `source ~/.zshrc` 명령어를 실행하여 설정을 다시 불러와야 합니다. 이제 명령어를 입력할 때 존재하지 않는 명령어는 빨간색으로 뜨고 한번 입력했던 명령어를 회색으로 표현해주는 걸 확인할 수 있습니다.



**테마**

oh-my-zsh의 기본 테마인 `robbyrussell`도 깔끔하지만, 이 외에 [다양한 테마](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes)가 존재합니다. 테마를 바꾸는 방법은 `~/.zshrc`파일의 `ZSH_THEME="robbyrussell"` 부분을 원하는 테마로 수정하면 됩니다.

여기서는 이쁘고 단순하고 빠른 [pure](https://github.com/sindresorhus/pure) prompt를 사용합니다.

```
brew install nodejs # nodejs가 설치되어 있다면 skip
npm install --global pure-prompt
```

설치를 완료했으면 `~/.zshrc`파일에 다음항목을 추가합니다.

```
autoload -U promptinit; promptinit
prompt pure
```

이제 zsh 기본 설정이 끝났습니다!





**oh-my-zsh 팁**

zsh과 oh-my-zsh의 조합으로 강력한 쉘을 사용할 수 있게 되었습니다. 여기서 모든 기능을 설명할 순 없지만 자주 사용하는 몇 가지 팁을 소개합니다.

1. 명령어가 기억나지 않으면 `tab`을 누르세요
2. cd ../.. 대신 `...`, `....`, `.....`, …
3. 단축명령어 - `git status` => `gst`, `git pull` => `gl` 등등 [다양한 단축명령어](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugin:git)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        



팁이 맘에 든다면 [다른 플러그인](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins)도 구경하세요. 어마어마한 양의 플러그인이 준비되어 있습니다.

[oh-my-zsh 홈페이지](https://github.com/robbyrussell/oh-my-zsh) / [pure github](https://github.com/sindresorhus/pure)

## 커맨드라인 애플리케이션

이제 터미널이 이뻐졌으니 각종 도구를 설정해봅니다.

### vim

vim은 기본으로 설치된 터미널용 에디터로 GUI 환경의 에디터를 사용할 수 있는 macOS 환경에서는 일부 ~~고오오급~~ 개발자를 제외하고는 잘 쓰이지 않습니다. 하지만 터미널 작업을 하다 보면 간단하게 수정할 파일이 있고 git 커밋메시지를 작성할 때 종종 사용하게 됩니다.

기본으로 설정된 화면은 밋밋하기 그지 없기 때문에 강력한 기능의 플러그인을 설치해줍니다.

**설치**

내장된 vim대신 neovim을 설치합니다. neovim은 vim과 차이가 없어 보이는데 24bit True Color를 지원하고 오래된 vim 소스를 처음부터 다시 짜서 소스코드가 줄었다고 합니다. 저 같은 라이트 유저는 차이를 느끼진 못하지만 좋다고 해서 사용하고 있습니다. 그리고 테마에서 사용할 개발용 폰트를 설치합니다.

```
brew install neovim
brew tap homebrew/cask-fonts
brew cask install font-hack-nerd-font
```

기본 설치가 완료되었으면 터미널 기본 에디터로 vi대신 neovim을 사용하도록 `~/.zshrc`에 다음 항목을 추가합니다.

```
alias vim="nvim"
alias vi="nvim"
alias vimdiff="nvim -d"
export EDITOR=/usr/local/bin/nvim
```

`source ~/.zshrc`를 입력하여 설정을 다시 불러옵니다.





**플러그인**

vim은 강력한 플러그인들이 많이 있는데 설치가 어렵고 어떤 게 좋은지 라이트 유저는 알 수가 없습니다. SpaceVim이라는 프로젝트는 가장 많은 사람들이 사용하는 플러그인을 자동으로 설치해줍니다. 약간 무거운 느낌이 있긴 하지만 설치가 간단하고 화면을 보는 순간 고오오급 개발자의 포스를 만들어주니 바로 설치해봅니다.

```
curl -sLf https://spacevim.org/install.sh | bash
```

설치가 완료되면 `vi`를 실행합니다. 최초 실행 시 mode 설정을 물어보고 (`1`을 누릅니다) 자동으로 플러그인을 설치합니다. 플러그인이 많아서 시간이 꽤 걸립니다.





__테마변경__

vi ~/.SpaceVim.d/init.toml

![image-20200514144720772](/Users/bluuminn/Library/Application Support/typora-user-images/image-20200514144720772.png)



같은 파일 맨 아래에 추가

![image-20200514145305694](/Users/bluuminn/Library/Application Support/typora-user-images/image-20200514145305694.png)



**폰트**

앗, 플러그인을 설치하고 vi를 실행하면 폰트가 깨져서 ?가 보이는 걸 알 수 있습니다.

![img](https://subicura.com/assets/article_images/2017-11-22-mac-os-development-environment-setup/nvim-question.png)

iTerm2에 개발 관련 폰트를 모은 NerdFont를 추가로 설정합니다.

![img](https://subicura.com/assets/article_images/2017-11-22-mac-os-development-environment-setup/iterm-font.png)

iTerm을 실행하고 설정(`⌘` + `,`)창에서 `Profiles` 항목을 선택하고 `Text`탭을 선택합니다. Font항목에서 `Use a different font for non-ASCII text`를 체크하고 다른 탭을 살짝 눌렀다 다시 돌아오면 Non-ASCII Font를 설정할 수 있습니다. 거기서 Knack Regular Nerd Font Complete를 선택하면 폰트가 이쁘게 나옵니다.





### fzf

fzf는 강력하고 엄청나게 빠른 fuzzy finder 도구입니다. 증분 검색을 통하여 원하는 파일이나 히스토리를 쉽고 빠르게 찾을 수 있게 해줍니다. 정확하게 원하는 값을 입력하지 않고 일부만 입력해도 실시간으로 검색 결과를 보여줍니다.

![img](https://subicura.com/assets/article_images/2017-11-22-mac-os-development-environment-setup/fzf-sample.png)

**설치**

```
brew install fzf

# To install useful key bindings and fuzzy completion:
$(brew --prefix)/opt/fzf/install
```

brew 설치 후 install 명령어를 입력하면 몇 가지를 물어보는데 전부 `y`를 누르면 됩니다. 설치가 완료되었으면 `source ~/.zshrc`를 입력하여 설정을 다시 불러옵니다.



brew install fzf

![image-20200514145916399](/Users/bluuminn/Library/Application Support/typora-user-images/image-20200514145916399.png)



설치 다 되면

중간에 To install useful keybindings and fuzzy completion: 아래 경로 복사해서 명령어로 실행 (아래 사진 참고)

![image-20200514150039151](/Users/bluuminn/Library/Application Support/typora-user-images/image-20200514150039151.png)



그리고 전부 y눌러서 설치.

설치가 완료되었으면 `~/.zshrc`에 plugin을 추가해줍니다.

```
plugins=(
  ...
  ...
  fzf
)
```

설치 완료 후 `source ~/.zshrc`(설정 다시 불러오기)



**명령어**

정말 다양하게 사용할 수 있지만 여기선 가장 기본적인 기능만 살펴봅니다.

| 단축키      | 기능                       |
| :---------- | :------------------------- |
| `⌃` + `T`   | 하위 디렉토리 파일 검색    |
| `⌃` + `R`   | 히스토리 검색              |
| `esc` + `C` | 하위 디렉토리 검색 후 이동 |





### fasd

fasd는 사용빈도가 높은 파일 또는 디렉토리 검색을 편하게 해서 생산성을 향상시켜주는 도구입니다. 열어본 파일이나 이동한 디렉토리를 기억하고 우선순위를 정해서 빠르게 검색할 수 있게 도와줍니다.

**설치**

```
brew install fasd
```

설치가 완료되었으면 `~/.zshrc`에 plugin을 추가해줍니다.

```
plugins=(
  ...
  ...
  fasd
)
```

전부 완료되었으면 `source ~/.zshrc`를 입력하여 설정을 다시 불러옵니다.

**명령어**

명령어를 사용하기 위해서는 일단 디렉토리를 좀 이동하고 파일도 열어보고 해야 합니다. 어느 정도 히스토리가 쌓이면 명령어를 입력해봅니다.

| 단축키 | 기능                  |
| :----- | :-------------------- |
| `z`    | 디렉토리 이동         |
| `s`    | 파일 or 디렉토리 검색 |

디렉토리를 이동할 때 `z github`, `tab`과 같이 일부 검색어를 입력하고 tab을 눌러서 이동합니다.





#### 도커 설치

- `brew cask install `



#### neofetch

- `brew install neofetch`







### [oh-my-zsh] Insecure completion-dependent directories detected 에러 해결

Mac이나 리눅스에서 대체로 이런 문제는 퍼미션 때문이다.

 

이 경우 원인은 /usr/local/share/zsh 및 그 하위디렉토리의 소유자(user)가 원래 쓰던 계정으로 되어 있기 때문이다. 새로 만든 계정이 administer라 하더라도 그렇다.

 

해결방법은 두 가지가 있는데, 하나는 디렉토리 소유권을 변경하는 것이고 다른 하나는 에러 메시지에 나온 것처럼 .zshrc에 ZSH_DISABLE_COMPFIX="true"를 입력하는 것이다.

 

이런 경우 .zshrc에 설정을 추가하는 것이 바람직하다. 주의할 점은 oh-my-zsh보다 앞에 설정해야 한다는 것.



![image-20200514170049081](/Users/bluuminn/Library/Application Support/typora-user-images/image-20200514170049081.png)



껐다가 켜거나 source ~/.zshrc 하면 됨

