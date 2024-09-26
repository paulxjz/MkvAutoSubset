 mkvtool 完成 zsh
---------------

为 zsh 生成自动完成脚本

###  概要

为 zsh shell 生成自动完成脚本。

如果您的环境中尚未启用 shell 完成，则需要启用它。您可以执行一次以下操作：

    echo "autoload -U compinit; compinit" >> ~/.zshrc


要在当前 shell 会话中加载补全：

    source <(mkvtool completion zsh)


要为每个新会话加载补全，请执行一次：

####  Linux的：

    mkvtool completion zsh > "$\{fpath[1]\}/\_mkvtool"


####  macOS 版本：

    mkvtool completion zsh \> $(brew --prefix)/share/zsh/site-functions/_mkvtool


您需要启动一个新的 shell 才能使此设置生效。

    mkvtool completion zsh [flags]


###  选项

      -h, --help              zsh 帮助
          --no-descriptions   禁用完成描述


### 从父命令继承的选项

          --enable-ass-pgs-coexist   启用 pgs 和 ass 共存模式.
          --enable-pgs-output        启用 pgs 输出模式.
          --font-cache-dir string    指定字体缓存目录路径. (default "C:\\Users\\hlj49/.mkvtool/caches")
          --framerate string         设置 pgs 或空白视频帧速率 (e.g., 23.976, 24, 25, 30, 29.97, 50, 59.94, 60, or custom fps like 15/1). (default "23.976")
          --log string               指定日志文件路径.
          --no-font-check            禁用字体检查模式.
          --no-font-check-strict     禁用严格字体检查模式.
          --no-font-rename           禁用字体重命名模式.
          --resolution string        设置 pgs 或空白视频分辨率 (e.g., 720p, 1080p, 2k, or custom resolution like 720*480). (default "1920*1080")


###  另请参阅

*   [mkvtool completion](mkvtool_completion.md) - 为指定的 shell 生成自动补全脚本

###### 由 spf13/cobra 于 2024 年 6 月 16 日自动生成

