

# Profile 配置保存

```json
function zgw {  cd 'H:\ZgwWorkSpace\zhonggangwang\ZhongGangWang' }
function sql{  cd 'H:\ASWorkSpace\pos-pay' }
function asws { cd 'H:\ASWorkSpace' }
function pyws { cd 'H:\pyProject' }
function ideaws { cd 'H:\IdeaProject' }
function wxws{ cd 'H:wxProject' }
function note {  cd 'H:\Note'  }
function wlb {  cd 'H:\ZgwWorkSpace\Wlb_Android\LogisticsOfLiuZonghui'  }
function apidoc {  cd 'H:\ApiDoc'  }
function profile {  start 'C:\Users\lyf\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1'  }
function as {  start 'C:\Program Files\Android\Android Studio\bin\studio64.exe'  }
function edge {  start 'C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe' --profile-directory=Default  }
function chrome {  start 'C:\Program Files\Google\Chrome\Application\chrome.exe' }
function idea {  start 'E:\IntelliJ IDEA 2020.3.3\bin\idea64.exe' }
function wx{  start 'E:\SuperWeChatPC-1.1.3\bin\WeChat1.exe' }
function fileres{  start 'C:\Users\lyf\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch\User Pinned\TaskBar\File Explorer.lnk' }
function Typora {  start 'E:\Typora\Typora.exe' }

$PSDefaultParameterValues['*:Encoding'] = 'utf8'
set-alias vim "E:\Vim\vim82\vim.exe" # 此处为vim的安装路径
 
Function Edit-Profile
{
    vim $profile
}
 
Function Edit-Vimrc
{
    vim $HOME\_vimrc
}
```

