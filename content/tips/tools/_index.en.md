+++
title = "Tools"
date = 2019-03-17T15:31:16-04:00
weight = 1
chapter = true
pre = " > "
+++

### Tips for tools
***

+ [Easy to use terminal - Oh My ZSH + iTerm2](#tips-tool-iterm2)
+ [Easy to use terminal - alias](#tips-tool-iterm2)



<a name="tips-tool-iterm2"></a>
### Easy to use terminal - Oh My ZSH + iTerm2
___

If you are not familiar with terminal and git,
I strongly recommend oh my zsh and iterm2!

{{% notice info %}}
[Jazz Up Your “ZSH” Terminal In Seven Steps — A Visual Guide](https://medium.freecodecamp.org/jazz-up-your-zsh-terminal-in-seven-steps-a-visual-guide-e81a8fd59a38)
{{% /notice %}}

{{% notice warning %}}
I use docker for dev environment.
After I installed iterm2, I got errors when I tried to use nvm.
You need to add command in your bash_profile.
{{% /notice %}}
go to `~/.bash_profile`
add these!
```
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```



<a name="tips-tool-alias"></a>
### Easy to use terminal - alias
___

If you use iterm2,

```
vi ~/.zshrc
```

or

```
opne ~/.zshrc
```

and you can see these line which you set up for plugins

```
  if [[ "$USER" != "$DEFAULT_USER" || -n "$SSH_CLIENT" ]]; then
    prompt_segment black default "%(!.%{%F{yellow}%}.)$USER"
  fi
}

```

above if statement,
you can add **alias statement**

```
alias go_areumpro='cd /Users/areum/Documents/AreumProjects'
alias go_areum_blog='cd /Users/areum/Documents/AreumProjects/areum_blog'
alias open_setting='vim ~/.zshrc'
alias restart_setting='source ~/.zshrc'
```

How to use

```
alias ***your alias*** = '***what you want to do***'
```

I made `go_areumpro`, `go_areum_blog` for moving into folder,<br />
`open_setting` for open setting file since I forget file name all the time <br />
Usually, we need to restart terminal when we changed our setup file. I made `restart_setting`. So I do not need to restart my terminal window!

_If you just use terminal_

```
open ~/.bash_profile
```
and added **alias**

