 mkv工具
------

MKV 工具 - 用于管理 mkv 文件的多功能工具

###  概要

MKV Tool 是一个全面的实用程序，用于创建、转储、制作、查询和管理 mkv 文件及其相关的字幕和字体。

`mkvtool <子命令> [标志]`

###  选项

          --enable-ass-pgs-coexist   启用pgs和ass共存模式.
          --enable-pgs-output        启用 pgs 输出模式.
          --font-cache-dir string    指定字体缓存目录路径。 (default "C:\\Users\\hlj49/.mkvtool/caches")
          --framerate string         设置 pgs 或空白视频帧速率 (e.g., 23.976, 24, 25, 30, 29.97, 50, 59.94, 60, or custom fps like 15/1). (default "23.976")
      -h, --help                     mkvtool 的帮助
          --log string               指定日志文件路径.
          --no-font-check            禁用字体检查模式。
          --no-font-check-strict     禁用严格字体检查模式。
          --no-font-rename           禁用字体重命名模式。
          --resolution string        设置 pgs 或空白视频分辨率 (e.g., 720p, 1080p, 2k, or custom resolution like 720*480). (default "1920*1080")


###  另请参阅

*   [mkvtool cache](mkvtool_cache.md) - 创建字体缓存
*   [mkvtool completion](mkvtool_completion.md) - 为指定的 shell 生成自动补全脚本
*   [mkvtool create](mkvtool_create.md) - 创建 mkv 文件
*   [mkvtool dump](mkvtool_dump.md) - 转储 mkv 文件
*   [mkvtool info](mkvtool_info.md) - 显示字体信息
*   [mkvtool list](mkvtool_list.md) - 显示字体列表
*   [mkvtool make](mkvtool_make.md) - 制作 mkv 文件
*   [mkvtool query](mkvtool_query.md) - 查询项目的文件夹
*   [mkvtool subset](mkvtool_subset.md) - 执行 ass 字体子集
*   [mkvtool version](mkvtool_version.md) - 显示应用程序版本

###### 由 spf13/cobra 于 2024 年 6 月 16 日自动生成

