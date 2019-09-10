Command Line (Bash/Zsh)
------
把你想要的功能貼在你的 `~/.bashrc`、`~/.zshrc` 或 `~/.bash_profile` 最下面
記得 `source` 讓你剛貼近去的指令生效
<br>
<br>
## lazyclone
<table>
<tr>
<td>
  
  ```shell
  function lazyclone {
      reponame=${1##*/}
      reponame=${reponame%.git}
      git clone "$1" "$reponame";
      cd "$reponame";
  }
  ```
</td>
<td>
<img src="/images/lazyclone.png"</img>
</td>
</tr>
<tr>
<td colspan="2">

  可以把repo抓下來後自動 `cd` 進去
</td>
</tr>
</table>

<br>

## ip
Note : I haven't had successes in alias and function so I went with a custom command placed in /usr/local/bin
<table>
<tr>
<td>
  
  **For Linux**
  ```bash
  ifconfig `route | grep ^default | sed "s/.* //"`  \
  | grep 'inet addr' | cut -d: -f2 | awk '{print $1}'
  ```
  
  **For macOS**
  ```bash
  ifconfig `route | grep ^default | sed "s/.* //"`  \
  | grep -w 'inet' | awk '{print $2}'
  ```
</td>
<td>
<img src="/images/ip.png"</img>
</td>
</tr>
<tr>
<td colspan="2">

  Instead of finding your ip using `ifconfig` while searching through a bunch of extra infos, this simply outputs your ip
</td>
</tr>
</table>
