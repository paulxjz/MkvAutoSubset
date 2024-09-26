 mkvtool 创建
-----------

 创建 mkv 文件

###  概要

从指定的源文件夹创建 mkv 文件，包括视频、字幕和字体。

    mkvtool create <input-dir> [flags]


###  选项

      -n, --disable-overwrite          禁用文件覆盖.
      -c, --clean                      清理原始文件字幕和字体.
      -m, --enable-mks-output          启用 mks 输出.
      -f, --font-sub-dir string        字体子目录. (default "f")
      -h, --help                       帮助创建
      -o, --output-sub-dir string      输出子目录. (default "o")
      -l, --subtitle-language string   指定字幕语言. (default "chi")
      -s, --subtitle-sub-dir string    字幕子目录. (default "s")
      -t, --subtitle-title string      指定字幕标题.
      -v, --video-sub-dir string       视频子目录. (default "v")


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

