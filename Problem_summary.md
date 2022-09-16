# coc.nvim 
## registnotification error 
更新coc -> :PlugUpdate

#nvim剪切板
下载xclip
sudo apt install xclip
init.vim 中添加
```vim
set clipboard+=unnamedplus
```

#备份ubuntu
执行压缩命令
```bash
sudo su
tar cvpzf backup.tgz --exclude=/proc --exclude=/lost+found --exclude=/backup.tgz --exclude=/mnt --exclude=/sys --exclude=/media /
```
