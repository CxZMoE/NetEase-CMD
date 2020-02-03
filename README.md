# NetEase-CMD
一个基于命令行的网易云音乐播放器 for Linux

[![example](https://github.com/CxZMoE/NetEase-CMD/raw/master/image/example.gif)](https://github.com/CxZMoE/NetEase-CMD)

## 安装
#### 依赖
`libbass`
`node`

#### 预编译

#### 编译运行
```shell script
# 如果没有装node请先安装
# Ubuntu: sudo apt install npm
# Arch: sudo pacman -S npm


git clone https://github.com/CxZMoE/Netease-CMD.git
cd Netease-CMD/
go build app.go
sudo cp libbass.so /usr/lib
./app   #运行
```

## 功能特性
1. 支持MP3格式、FLAC无损格式音频播放
1. 支持我喜欢的音乐、歌单的播放
1. 支持每日推荐、私人FM、心动模式
1. 支持加入喜欢
1. 支持每日签到 +3积分
1. 歌词显示（命令行内
1. 基本的播放操作
1. 支持多功能全局快捷键（打游戏的时候终于不用切出来了

注:全局快捷键功能需要程序以root身份运行 `$ sudo ./xzp`

## 键盘快捷键		
| 按键   | 功能          |
| ----- | --------------- | 
| CTRL+ALT+左箭头| 上一首|
| CTRL+ALT+右箭头     | 下一首 | 
| CTRL+ALT+PgDn| 快进 15s|
| CTRL+ALT+PgUp|快退 15s|
| CTRL+ALT+P| 播放/暂停|
| CTRL+ALT+S| 停止播放|
| CTRL+ALT+]| 增加音量 10%|
| CTRL+ALT+[| 减少音量 10%|
| CTRL+ALT+F| 前往我喜欢的音乐|
| CTRL+ALT+G| 前往私人FM|
| CTRL+ALT+D| 前往推荐|
| CTRL+ALT+M| 改变播放模式|
| CTRL+ALT+L| 添加到喜欢|

## 命令行帮助菜单
输入m可以查看帮助

```shell script
===Command Usages===
0) [author] 显示作者信息
1) [login] <邮箱> <密码>: 邮箱登陆
2) [logout]: 登出
3) [qd]: 每日签到
4) [fm]: 前往私人FM模式
5) [fav]: 前往我喜欢的音乐
6) [day]: 前往每日推荐
7) [sheet]: 显示当前歌单列表
8) [sheet] <序号>: 前往对应序号歌单
9) [list/ls]: 显示播放列表
10) [goto/go] <序号>: 转跳到指定序号歌曲
11) [time/t] <sec>: 跳到歌曲的第sec秒
12) [last/l]: 上一首
13) [next/n]: 下一首
14) [play/p]: 播放歌曲
15) [pause]: 暂停歌曲
16) [stop]: 停止歌曲
17) [pg]: 显示进度条 #显示的时候输入字符会被刷掉.
18) [key] 显示快捷键列表
```

### 感谢以下项目的贡献
* Binaryify / NeteaseCloudMusicApi 
* buger / goterm 
* eiannone / keyboard 