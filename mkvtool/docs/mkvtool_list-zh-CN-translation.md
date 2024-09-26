 mkv工具列表
--------

 显示字体列表

###  概要

显示指定 ass 文件或文件夹中使用的字体列表。

    mkvtool list <ass-file|ass-dir> [output-dir] [flags]


###  选项

      -f, --font-dir string   指定 ass 字体文件夹.
      -h, --help              帮助列表


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

*   [mkvtool](mkvtool.md) - MKV 工具 - 管理 mkv 文件的多功能工具

###### 由 spf13/cobra 于 2024 年 6 月 16 日自动生成
