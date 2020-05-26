# NetEase-CMD
一个基于命令行的网易云音乐播放器 for Linux

[![example](https://github.com/CxZMoE/NetEase-CMD/raw/master/image/example.gif)](https://github.com/CxZMoE/NetEase-CMD)  

# 安装

## 手动安装
```shell script
# 可以将这个脚本复制到 xxx.sh 中执行
# 如果没有装node请先安装
# Ubuntu: sudo apt install npm
# Arch: sudo pacman -S npm

# 如果没有装golang请先安装
# Ubuntu: sudo apt install golang
# Arch: sudo pacman -S go
SRC_DIR=$GOPATH/src/github.com/CxZMoE/NetEase-CMD/
INSTALL_DIR=/usr/local/NetEase-CMD
echo "Creating program directory."
sudo mkdir -p $INSTALL_DIR

# 获取项目
echo "Getting Project: NetEase-CMD"
go get -u github.com/CxZMoE/NetEase-CMD

# 复制动态链接库
echo "Installing libraries."
cd $SRC_DIR
sudo cp libbass.so /lib
sudo cp lib/libbassflac.so /lib

# 安装Node包
echo "Installing node packages."
sudo cp -r $SRC_DIR/NeteaseApi $INSTALL_DIR/NeteaseApi
cd $INSTALL_DIR/NeteaseApi
npm install


## 创建程序目录
### cd $SRC_DIR/
### go build -o NetEase-CMD
echo "Installing main program."
cd $GOPATH/bin
sudo ln $INSTALL_DIR/NetEase-CMD -s /usr/bin/NetEase-CMD

# 安装完毕
echo "Installation of NetEase-CMD finished"

```

# 使用方法

## 功能特性
1. 支持MP3格式、FLAC无损格式音频播放
1. 支持我喜欢的音乐、歌单的播放
1. 支持每日推荐、私人FM、心动模式
1. 支持加入喜欢
1. 支持每日签到 +3积分
1. 歌词显示（命令行内
1. 基本的播放操作
1. 支持多功能全局快捷键（打游戏的时候终于不用切出来了

注:全局快捷键功能需要程序以root身份运行 `$ sudo NetEase-CMD`  
## 键盘快捷键		
| 按键   | 功能          |
| ----- | --------------- | 
| CTRL+ALT+左箭头| 上一首 |
| CTRL+ALT+右箭头| 下一首 | 
| CTRL+ALT+PgDn| 快进 15s |
| CTRL+ALT+PgUp|快退 15s |
| CTRL+ALT+P| 播放/暂停 |
| CTRL+ALT+S| 停止播放 |
| CTRL+ALT+]| 增加音量 10% |
| CTRL+ALT+[| 减少音量 10% |
| CTRL+ALT+F| 前往我喜欢的音乐 |
| CTRL+ALT+G| 前往私人FM |
| CTRL+ALT+D| 前往推荐 |
| CTRL+ALT+M| 改变播放模式 |
| CTRL+ALT+K| 添加到喜欢 |
| CTRL+ALT+L| 取消喜欢 |

## 命令行帮助菜单
输入m可以查看帮助

```shell script
===Command Usages===
0) [author] 显示作者信息
1) [login] <邮箱> <密码>: 邮箱登陆
2) [logout]: 登出
3) [exit/q]: 退出程序
4) [qd]: 每日签到
5) [fm]: 前往私人FM模式
6) [fav]: 前往我喜欢的音乐
7) [day]: 前往每日推荐
8) [sheet]: 显示当前歌单列表
9) [sheet] <序号>: 前往对应序号歌单
10) [list/ls]: 显示播放列表
11) [goto/go] <序号>: 转跳到指定序号歌曲
12) [time/t] <sec>: 跳到歌曲的第sec秒
13) [last/l]: 上一首
14) [next/n]: 下一首
15) [play/p]: 播放歌曲
16) [pause]: 暂停歌曲
17) [stop]: 停止歌曲
18] [x]: 打开/关闭 歌词
19) [pg]: 显示进度条 #显示的时候输入字符会被刷掉.
20) [key]: 显示快捷键列表
21) [exit/q]: 退出
```

### 感谢以下项目的贡献
* Binaryify / [NeteaseCloudMusicApi](https://github.com/Binaryify/NeteaseCloudMusicApi)  
* buger / [goterm](https://github.com/buger/goterm)
