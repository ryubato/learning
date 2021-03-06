# Windows 10 개발환경구성

## WSL Ubuntu

### 다운로드 서버 변경

속도가 느린 기본 해외 서버를 카카오 서버로 변경

```bash
sudo vi /etc/apt/sources.list
:%s/archive.ubuntu.com/ftp.daumkakao.com  # 모두 바꾸기
:%s/security.ubuntu.com/ftp.daumkakao.com
```

### 터미널 색상 테마 적용

```bash
git clone https://github.com/seebi/dircolors-solarized ~/temp
cp /temp/dircolors.ansi-dark ~/.dircolors
rm -rf /temp
```

### zsh & oh my zsh 적용

#### 0. 터미널 속성에서 폰트를 D2 ligature로 변경

#### 1. zsh 설치

```bash
sudo apt-get install zsh
```

#### 2. zsh 설정 변경 - 테마 agnoster로 변경

```bash
sudo vi ~/.zshrc

ZSH_THEME = "agnoster"
```

#### 3. zsh 설정 변경 - bash 터미널 색상 테마 적용

```bash
sudo vi ~/.zshrc

eval `dircolors ~/.dircolors`  # 추가
```

#### 4. zsh 설정 변경 - prompt context 수정

```bash
sudo vi ~/.zshrc

# $USER@%m : user name & pc name
prompt_context() {
  if [[ "$USER" != "$DEFAULT_USER" || -n "$SSH_CLIENT" ]]; then
    prompt_segment black default "%(!.%{%F{yellow}%}.)$USER"
  fi
}
```

#### 5. zsh 설정 변경 - New Line 적용

```bash
vi ~/.oh-my-zsh/themes/agnoster.zsh-theme

# prompt_newline 추가
build_prompt() {
  RETVAL=$?
  prompt_status
  prompt_virtualenv
  prompt_context
  prompt_dir
  prompt_git
  prompt_bzr
  prompt_hg
  prompt_newline //이부분을 추가 꼭 순서 지켜서
  prompt_end
}

# prompt_newline function 추가
prompt_newline() {
  if [[ -n $CURRENT_BG ]]; then
    echo -n "%{%k%F{$CURRENT_BG}%}$SEGMENT_SEPARATOR
%{%k%F{blue}%}$SEGMENT_SEPARATOR"
  else
    echo -n "%{%k%}"
  fi

  echo -n "%{%f%}"
  CURRENT_BG=''
}
```

#### 6. oh my zsh 설치

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

#### 7. wsl ubuntu 기본 shell을 bash에서 zsh로 변경

```bash
which zsh # zsh 경로 확인 ex) /usr/bin/zsh
chsh -s /usr/bin/zsh
```

### Intellij 기본 Terminal wsl ubuntu로 변경

Settings > Tools > Terminal > Shell path : C:\Windows\System32\wsl.exe

```cmd
C:\Windows\System32\wslconfig /list

Windows Subsystem for Linux Distributions:
Ubuntu-18.04
Legacy (Default)

C:\Windows\System32\wslconfig /setdefault Ubuntu-18.04

C:\Windows\System32\wsl.exe
```

### 참고사이트

https://medium.com/harrythegreat/oh-my-zsh-iterm2%EB%A1%9C-%ED%84%B0%EB%AF%B8%EB%84%90%EC%9D%84-%EB%8D%94-%EA%B0%95%EB%A0%A5%ED%95%98%EA%B2%8C-a105f2c01bec

https://medium.com/@boystyou82/%EC%9C%88%EB%8F%84%EC%9A%B010-frontend-%EA%B0%9C%EB%B0%9C%ED%99%98%EA%B2%BD-%EC%84%B8%ED%8C%85-2-d82b47136e63

https://nesoy.github.io/articles/2017-03/ZSH

https://snowdeer.github.io/linux/2018/09/26/how-to-config-zsh/
