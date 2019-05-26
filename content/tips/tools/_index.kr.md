+++
title = "Tools"
date = 2019-03-17T15:31:16-04:00
weight = 1
chapter = true
pre = " > "
+++

### Tips for tools
***
일을 하면서 툴, 단축키 등 사용 하나하나가 개발 생산성에 큰 영향을 준다는 것을 깨닫고 또 깨닫습니다. 그래서 제가 아는 팁들을 간단하게 정리하거나 링크 하려고 합니다.

+ [터미널 쉽게 사용하기 - Oh My ZSH + iTerm2](#tips-tool-iterm2)
+ [터미널 쉽게 사용하기 - alias로 나만의 단축키 만들기](#tips-tool-iterm2)



<a name="tips-tool-iterm2"></a>
### 터미널 쉽게 사용하기 - Oh My ZSH + iTerm2
___

처음 git을 사용할 때 저는 제가 어느 브런치에 있는지 상태는 어떤지 매번 확인하면서도 불안함에 쉽게 어느 커멘트도 날릴 수 없었습니다. 회사에 구세주 한 분 [(구세주 보러 가기)](https://blog.sonim1.com/)이 계시는데 그 분이 링크까지 보내주면서 이걸 써 보라고...

그리고 현재는 인턴에게 git에대해 제가 설명까지 해줄 수 있는 기적같은 일이 일어났다는!!

개념과 방법이 잘 소개 되어있는 링크 하나면 될 것 같습니다.
어느 정도냐하면 제 브라질 친구(한국어 1도 모름)가 그냥 보고 따라하더라고요!

{{% notice info %}}
[Oh My ZSH+ iTerm2로 터미널을 더 강력하게](https://medium.com/harrythegreat/oh-my-zsh-iterm2%EB%A1%9C-%ED%84%B0%EB%AF%B8%EB%84%90%EC%9D%84-%EB%8D%94-%EA%B0%95%EB%A0%A5%ED%95%98%EA%B2%8C-a105f2c01bec)
{{% /notice %}}

{{% notice warning %}}
저는 Docker를 이용해서 개발환경을 쓰고 있는데요.
iTerm2를 깔았더니 nvm을 쓸 때 자꾸 오류가 나더라구요 ㅠㅠ<br />
아래처럼 설정해 주면 됩니다.
{{% /notice %}}
`~/.bash_profile` 에서
```
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```



<a name="tips-tool-alias"></a>
### 터미널 쉽게 사용하기 - alias로 나만의 단축키 만들기
___

만약 iterm2를 쓴다면,

```
vi ~/.zshrc 또는 opne ~/.zshrc
```
명령어를 통해 설정파일로 들어 갈 수 있습니다.

그리고

```
  if [[ "$USER" != "$DEFAULT_USER" || -n "$SSH_CLIENT" ]]; then
    prompt_segment black default "%(!.%{%F{yellow}%}.)$USER"
  fi
}

```

위에 if 설정(iterm 플러그인 사용을 위해 파일 제일 끝에 입력했던 부분입니다.) 윗부분에 아래 내용처럼 단축키를 만들어줍니다.

```
alias go_areumpro='cd /Users/areum/Documents/AreumProjects'
alias go_areum_blog='cd /Users/areum/Documents/AreumProjects/areum_blog'
alias open_setting='vim ~/.zshrc'
alias restart_setting='source ~/.zshrc'
```

- `alias`: 단축키를 만들기 위한 명령어 입니다.

보통 모양은 아래와 같습니다.

```
alias 쓰고싶은 명령어 이름 = '수행하고 싶은 내용'
```

저는 `go_areumpro`, `go_areum_blog`를 이용해서 쉽게 제가 접근하고 싶은 폴더로 이동 할 수 있게 만들었습니다.<br />
`open_setting`를 통해 설정파일을 열도록 하였습니다.(제가 자꾸 파일명을 까먹어서...) <br />
보통 설정파일을 변경하게 되면 터미널을 껏다 다시 켜줘야 하는데요.
`restart_setting` 를 통해서 다시 재부팅 할 필요 없이 만들어주었습니다.

_만약 mac에 있는 터미널을 쓰신다면_

```
open ~/.bash_profile
```
해당 파일에서 **alias** 명령어를 써주시면 됩니다.



