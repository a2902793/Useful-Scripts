Command Line (Bash/Zsh)
------
把你想要的功能貼在你的 `~/.bashrc`、`~/.zshrc` 或 `~/.bash_profile` 最下面
記得 `source` 讓你剛貼近去的指令生效
<br>
<br>
### lazyclone
可以把repo抓下來後自動 `cd` 進去.
```bash
function lazyclone {
    reponame=${1##*/}
    reponame=${reponame%.git}
    git clone "$1" "$reponame";
    cd "$reponame";
}
```

### ip?
與其每次看ip時要輸入`ifconfig`然後慢慢找，不如直接印出ip省去其他資訊
```bash
ifconfig `route | grep ^default | sed "s/.* //"`  | grep 'inet addr' | cut -d: -f2 | awk '{print $1}'
```

<table>
<tr>
<td>
  
  ```bash
  function lazyclone {
      reponame=${1##*/}
      reponame=${reponame%.git}
      git clone "$1" "$reponame";
      cd "$reponame";
  }
  ```
</td>
<td>
  
  ```nemerle
  def x : int = 3;
  def y : string = "foo";
  def obj : Object = getObject();
  ```
</td>
</tr>
<tr>
<td colspan="2">
  可以把repo抓下來後自動 `cd` 進去
</td>
</tr>
</table>

bgdfjd
