---
title: Remote-SSH-VSCode
date: 2020-02-01T12:01:33+02:00
draft: false
categories: [Dev]
tags: [tool]
---

+ Install Remote-SSH [extension](https://code.visualstudio.com/docs/remote/ssh)

+ Config for remote server
Using GUI or config file (`$HOME/.ssh/config`)
![](/images/remote-ssh-vscode.png)


+ Config for remote server through proxy (an intermediate server)
Using [`ProxyCommand`](https://code.visualstudio.com/blogs/2019/10/03/remote-ssh-tips-and-tricks)
```
# Jump box with public IP address
Host jump-box
    HostName 52.179.157.97
    User sana
    IdentityFile ~/.ssh/jumpbox

# Target machine with private IP address
Host target-box
    HostName <IP address of target>
    User sana
    IdentityFile ~/.ssh/target
    ProxyCommand ssh -q -W %h:%p jump-box

```

