# mkvtool 中文用户手册

## 概述

`mkvtool` 是一款功能强大的命令行工具，专为处理 MKV（Matroska 视频）文件设计。它支持创建、提取、制作和查询 MKV 文件，同时提供字幕和字体的管理功能。本手册旨在帮助用户快速掌握 `mkvtool` 的使用方法，包括全局参数、子命令及其具体应用。

---

## 全局参数

全局参数适用于所有子命令，以下是常用选项：

- `--enable-ass-pgs-coexist`：允许 ASS 和 PGS 字幕共存。
- `--enable-pgs-output`：启用 PGS 字幕输出。
- `--font-cache-dir <路径>`：指定字体缓存目录，默认为 `C:\Users\用户名\.mkvtool\caches`。
- `--framerate <帧率>`：设置 PGS 或空白视频的帧率，可选值包括 `23.976`、`24`、`25`、`30` 等，默认 `23.976`。
- `--log <文件路径>`：指定日志文件路径。
- `--no-font-check`：禁用字体检查。
- `--resolution <分辨率>`：设置视频分辨率，支持 `720p`、`1080p` 或自定义（如 `720*480`），默认 `1920*1080`。
- `-h, --help`：显示帮助信息。

---

## 子命令说明

`mkvtool` 支持以下子命令：

1. **​`cache`​**：创建字体缓存。
2. **​`completion`​**：生成 shell 自动补全脚本。
3. **​`create`​**：从文件夹创建 MKV 文件。
4. **​`dump`​**：提取 MKV 文件中的字幕和字体。
5. **​`info`​**：查看字体文件信息。
6. **​`list`​**：列出 ASS 文件使用的字体。
7. **​`make`​**：重新组合 MKV 文件。
8. **​`query`​**：查询文件夹中的 MKV 项目。
9. **​`subset`​**：对字体进行子集化处理。
10. **​`version`​**：显示版本信息。

### 1. cache - 创建字体缓存

**用法**：

```
mkvtool cache <字体目录> [参数]
```

**参数**：

- `-c, --clean-old-cache`：清除旧缓存。
- `-h, --help`：显示帮助。

**示例**：

```
mkvtool cache /path/to/fonts --clean-old-cache
```

**注意事项**：

- 缓存可提升后续操作的效率，建议定期更新。

---

### 2. completion - 生成自动补全脚本

**用法**：

```
mkvtool completion <shell类型>
```

**支持的 shell**：

- `bash`、`fish`、`powershell`、`zsh`

**参数**：

- `--no-descriptions`：禁用补全描述。
- `-h, --help`：显示帮助。

**示例**：

```
mkvtool completion bash > /etc/bash_completion.d/mkvtool
```

**注意事项**：

- bash 用户需安装 `bash-completion` 包。

---

### 3. create - 创建 MKV 文件

**用法**：

```
mkvtool create <输入目录> [参数]
```

**参数**：

- `-n, --disable-overwrite`：禁用文件覆盖。
- `-c, --clean`：清理原始视频中的字幕和字体。
- `-o, --output-sub-dir <目录>`：指定输出子目录，默认 `o`。
- `-s, --subtitle-sub-dir <目录>`：指定字幕子目录，默认 `s`。
- `-l, --subtitle-language <语言>`：指定字幕语言，默认 `chi`。
- `-t, --subtitle-title <标题>`：指定字幕标题。
- `-h, --help`：显示帮助信息。

**目录结构**：

```
输入目录/
├── v/           # 视频目录
│   ├── ep1.mkv
│   └── ep2.mp4
├── s/           # 字幕目录
│   ├── #ep1_chi_简体中文.ass    # ep1 的默认中文简体字幕
│   ├── ep1_eng_English.srt     # ep1 的英文字幕
│   └── ep2_chi_简体中文.ass    # ep2 的中文简体字幕
└── f/           # 字体目录
    ├── font1.ttf
    └── font2.otf
```

**字幕命名格式**：

- **格式**：`#<视频名>_<语言>_<标题>.<后缀>`
- **组成部分**：
  - `#`：可选，表示默认字幕轨道。
  - `<视频名>`：与视频文件名（不含扩展名）匹配。
  - `<语言>`：语言代码，例如 `chi`（中文）、`eng`（英文）。
  - `<标题>`：字幕的描述性标题。
  - `<后缀>`：字幕文件格式，例如 `ass`、`srt`。
- **示例**：
  - `#ep1_chi_简体中文.ass`：`ep1.mkv` 的默认中文简体字幕。
  - `ep2_eng_English.srt`：`ep2.mp4` 的英文字幕。

**示例**：

```
mkvtool create /path/to/input -l eng -t "English Subtitles"
```

**注意事项**：

- 字幕文件名中的 `<视频名>` 必须与视频文件名一致。
- ASS 字幕会自动进行子集化处理，字体从 `f/` 目录中提取。
- 使用 `-c` 参数可清理原始视频中的字幕和字体。

---

### 4. dump - 提取 MKV 内容

**用法**：

```
mkvtool dump <MKV文件|目录> [输出目录] [参数]
```

**参数**：

- `-n, --no-subset`：禁用字体子集化。
- `-h, --help`：显示帮助。

**示例**：

```
mkvtool dump video.mkv /path/to/output
```

---

### 5. info - 查看字体信息

**用法**：

```
mkvtool info <字体文件> [参数]
```

**参数**：

- `-h, --help`：显示帮助。

**示例**：

```
mkvtool info font.ttf
```

---

### 6. list - 列出字体

**用法**：

```
mkvtool list <ASS文件|目录> [输出目录] [参数]
```

**参数**：

- `-f, --font-dir <目录>`：指定字体目录。
- `-h, --help`：显示帮助。

**示例**：

```
mkvtool list subtitles.ass -f /path/to/fonts
```

---

### 7. make - 制作 MKV 文件

**用法**：

```
mkvtool make <视频目录> [数据目录] [输出目录] [参数]
```

**参数**：

- `-n, --disable-overwrite`：禁用文件覆盖。
- `-l, --subtitle-language <语言>`：指定字幕语言，默认 `chi`。
- `-h, --help`：显示帮助。

**示例**：

```
mkvtool make /path/to/videos /path/to/data
```

---

### 8. query - 查询 MKV 项目

**用法**：

```
mkvtool query <MKV文件|目录> [输出文件] [参数]
```

**参数**：

- `-h, --help`：显示帮助。

**示例**：

```
mkvtool query /path/to/mkv_folder result.txt
```

---

### 9. subset - 字体子集化

**用法**：

```
mkvtool subset <ASS文件|目录> [参数]
```

**参数**：

- `-f, --font-dir <目录>`：指定字体目录。
- `-e, --video-encoder <编码器>`：指定测试视频编码器，默认 `libx264`。
- `-h, --help`：显示帮助。

**示例**：

```
mkvtool subset subtitles.ass -f /path/to/fonts
```

---

### 10. version - 显示版本

**用法**：

```
mkvtool version [参数]
```

**参数**：

- `-h, --help`：显示帮助。

**示例**：

```
mkvtool version
```

---

## 使用建议

- **缓存管理**：定期运行 `cache` 子命令以保持字体缓存最新。
- **语言设置**：为字幕指定正确的语言代码（如 `chi` 为中文，`eng` 为英文）。
- **分辨率调整**：根据需求调整 `--resolution` 和 `--framerate` 参数。
- **帮助选项**：遇到问题时使用 `-h` 查看详细说明。

---

## 结语

本手册涵盖了 `mkvtool` 的所有核心功能和使用方法。通过清晰的结构、详细的参数说明和丰富的示例，用户可以轻松上手并高效完成 MKV 文件的处理任务。如需进一步帮助，请随时查阅 `-h` 参数提供的内置文档。
