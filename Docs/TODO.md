﻿# TODO
- ~~完善播放列表的功能，以支持“上一个”和“下一个”的切换，并能自动把同目录下相似文件名的文件加入播放列表中~~已完成，待测试
- ~~自动加载外挂字幕，并支持切换~~目前已经支持自动加载外挂字幕（如果视频文件本身没有字幕轨道的话），但暂时还无法实现选择字幕轨道的功能
- ~~自动加载外挂音轨，并支持切换~~我考虑了一下，感觉这个功能很鸡肋，所以暂时不打算添加了，想加载外挂音轨可以从右键菜单手动加载
- ~~添加SProgressBar，使其作为全屏时的进度指示器~~已完成，待测试
- ~~添加显示当地时间的OSD~~已完成，待测试
- ~~使媒体信息窗口和捐助窗口能根据主窗口尺寸缩放，而不是固定尺寸，同时注意如果缩放后尺寸太小就给一个合适的尺寸而不缩放~~已完成，待测试
- ~~使捐助二维码的图片分辨率更大一些~~已完成，待测试
- 添加BugReport程序
- 添加自动更新程序
- ~~添加托盘图标，并关联菜单~~已完成，待测试
- ~~添加章节跳转的功能~~已完成，待测试
- ~~绘制一套适合浅色皮肤使用的UI图标和LOGO素材，并在切换浅色和深色皮肤时自动切换相关素材~~已完成，但目前浅色和深色皮肤切换后需要重启播放器以实现部分UI元素的刷新
- 添加可以选择字幕轨道的功能
- 优化视频预览逻辑，防止播放卡顿
- 添加进度条右键提示显示章节名称（如果有的话）的功能
- 添加显示音乐专辑封面图片（FFmpeg：AVStream->attached_pic，是一个AVPacket，也要解码转RGB；Qt：QMediaMetaData->CoverArtImage，是一个QImage，先用MediaType判断是否是音频文件）的功能，播放器窗口大小要适应专辑封面图片的大小。如果音频文件没有专辑图片，则在其所在文件夹中查找是否有放置在外部的专辑封面图片，有就加载，如果音频文件内部和外部都没有专辑图片，则显示默认音频封面。[FFmpeg获取专辑图片的StackOverFlow参考](https://stackoverflow.com/questions/13592709/retrieve-album-art-using-ffmpeg)，[Qt获取专辑图片的知乎参考](https://www.zhihu.com/question/36859497/answer/69449195)
- 播放列表和播放历史挪到视频画面的左/右边，像一般的播放器那样可以收缩隐藏，同时也可以动态调整放在左边还是放在右边，ini文件可以记录播放列表是显示还是隐藏，底部控制区域右边添加一个控制播放列表隐藏/显示的按钮
- 添加其他语言翻译
- 支持高DPI
- 快进/快退调整为4秒（以前是10秒）
- 使用QLibrary加载dll，不再借助lib文件和头文件
- 添加渲染PGS和SUB字幕的功能
- 程序第一次打开时提示确认许可协议，不同意不能运行
- 解决双击切换全屏/窗口时会导致视频暂停/继续播放的问题
- 跟随QtAV的Player项目同步更新用得到的代码
- 改进打开URL的窗口，不再使用Qt自带的输入框，而是使用自己设计的窗口，在原来输入框的布局下方加入一个历史记录的列表区，同时在用户输入网址后判断网址是否包含http/ftp等前缀，若缺少则自动添加
- 默认启动器已使用Delphi实现，原来用Qt实现的启动器废弃
- 新版SPlayer的二进制文件均放置在与其版本号对应的文件夹中，不再像以前那样直接覆盖原始文件
- 所有业务逻辑不再单独放置在一个动态链接库中，而是直接编译成一个完整的可执行程序。为了减小exe文件的大小，所有资源文件不再编译进exe中，而是全部放置在外部
- 如果打开的是音频文件，那么就把其所在文件夹下所有的音频文件都加入到播放列表中，而不判断文件名是否相似；打开的是视频文件就要判断文件名是否相似后再添加
- 播放列表添加一个选项，支持单曲循环，列表循环，随机播放，单曲一次，列表一次模式，音视频都支持