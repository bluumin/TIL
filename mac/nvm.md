# NVM(Node Version Manager) Quick Start

- 사용환경: macOS

</br>

### 1. NVM 설치

```
$ sudo curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.1/install.sh | bash
```

</br>

### 2. 확인

```
$ nvm ls

-zsh: nvm: command not found
```

</br>

### 3. 당황하지 않고

```
$ vi ~/.zshrc
```

vi 에디터로 ./zshrc 열어서

```
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" # This loads nvm
```

위 코드가 있는지 확인

</br>

### 4. 재시작

```
source ~/.zshrc
```

</br>

### 5. 확인

```
$ nvm ls
->       system
node -> stable (-> N/A) (default)
iojs -> N/A (default)
```

</br>

</br>

## Node 설치

### 1. 설치

```
$ nvm install 6.10.1
```

안정화된 최신 버전인 6.10.1 설치

</br>

### 2. 확인

```
$ nvm ls
->      v6.10.1
         system
default -> 6.10.1 (-> v6.10.1)
node -> stable (-> v6.10.1) (default)
stable -> 6.10 (-> v6.10.1) (default)
iojs -> N/A (default)
lts/* -> lts/boron (-> v6.10.1)
lts/argon -> v4.8.1 (-> N/A)
lts/boron -> v6.10.1
$ node -v
v6.10.1
```

</br>

</br>

## 다른 버전의 노드 설치 및 버전 변경

### 1. 설치

```
$ nvm install 7.7.4
```

가장 최신 버전인 7.7.4 설치

</br>

### 2. 확인

```
$ nvm ls
        v6.10.1
->       v7.7.4
         system
default -> 6.10.1 (-> v6.10.1)
node -> stable (-> v7.7.4) (default)
stable -> 7.7 (-> v7.7.4) (default)
iojs -> N/A (default)
lts/* -> lts/boron (-> v6.10.1)
lts/argon -> v4.8.1 (-> N/A)
lts/boron -> v6.10.1
$node -v
v7.7.4
```

</br>

### 3. node 버전 변경 및 확인

```
$ nvm use 6.10.1
```

다시 6.10.1 버전으로 변경

```
$ node -v
v6.10.1
```

</br>

## 그밖의 자세한 정보는

[NVM](https://github.com/creationix/nvm) 에서 확인할 수 있습니다.