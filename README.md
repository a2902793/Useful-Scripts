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

  【功能】 可以把repo抓下來後自動 `cd` 進去
</td>
</tr>
</table>

<br>

## ipv4
1. 在 `/usr/local/bin` 建立了一個名為 `ipv4` 的檔案（沒有附檔名）

    ```shell
    sudo nano /usr/local/bin/ipv4
    ```
2. 然後把指令貼近去、儲存
3. 提供權限

    ```shell
    sudo chmod +x /usr/local/bin/ipv4
    ```
<br>
<table>
<tr>
<td>
  
  用 `ifconfig` 確認 ip 前面是 `inet` 還是 `inet addr`
  
  **inet (Ex: Ubuntu, macOS, Raspberry Pi...)**
  ```shell
  ifconfig `route | grep ^default | sed "s/.* //"` |
  grep -m 1 -w 'inet' | awk '{print $2}'
  ```
  
  **inet addr**
  ```shell
  ifconfig `route | grep ^default | sed "s/.* //"` |
  grep 'inet addr' | cut -d: -f2 | awk '{print $1}'
  ```
</td>
<td>
<img src="/images/ipv4.png"</img>
</td>
</tr>
<tr>
<td colspan="2">

  【功能】 與其用 `ifconfig` 查 ip 然後再從一大堆資訊裡面挑出來，這個命令就單純只會印出你的 ip
</td>
</tr>
</table>
