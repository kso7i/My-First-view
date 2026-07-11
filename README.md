<p align="center">
  <img src="assets/My-First-view-logo.png" width="180" alt="My-First-view Logo">
</p>

<h1 align="center">My-First-view 10.10</h1>

<p align="center">
  A Windows image viewer with Explorer-style sorting, multi-view layouts, RAW/NEF support, fast preview, tray integration, and multilingual UI.<br>
  一款面向 Windows 的多格式图片浏览器，支持资源管理器式排序、多窗口预览、NEF 快速浏览、系统托盘和多语言界面。
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-0078D4" alt="Windows">
  <img src="https://img.shields.io/badge/Python-3.10%2B-3776AB" alt="Python">
  <img src="https://img.shields.io/badge/GUI-PyQt5-41CD52" alt="PyQt5">
  <img src="https://img.shields.io/badge/Version-10.10-blue" alt="Version">
</p>

---

## Preview / 软件预览



---

## Introduction / 项目介绍

**My-First-view** 是一个使用 Python、PyQt5 和 Pillow 编写的 Windows 图片浏览器。

它不仅能打开常见图片格式，还提供了接近 Windows 文件资源管理器的排序与分组逻辑，并加入多窗口浏览、缩放、旋转、格式转换、背景、水印、系统托盘、开机启动、默认看图软件设置，以及 Nikon NEF 快速预览等功能。

The project is designed primarily for Windows 10 and Windows 11. Some functions, such as Explorer synchronization, startup registration, default-app association, and Recycle Bin operations, depend on Windows APIs.

---

## Features / 主要功能

| Category / 类别 | Features / 功能 |
|---|---|
| Image formats / 图片格式 | JPG、JPEG、PNG、BMP、GIF、WEBP、TIFF、AVIF、NEF |
| Fast startup / 快速启动 | 当前图片优先显示，文件夹扫描与邻近图片读取在后台进行 |
| Explorer sorting / 资源管理器排序 | 支持 Name、Date、Type、Size 排序与分组，支持 Ascending / Descending |
| Multi-view / 多窗口预览 | 支持 `1V1`、`2V2`、`1V2`、`2V1` 布局 |
| Linked viewing / 联动浏览 | 多窗口可选择 Linked 联动或 Separate 独立切换 |
| Zoom / 缩放 | 适应窗口、100% 显示、按钮缩放、滑块缩放、滚轮缩放 |
| Rotation / 旋转 | 左右 90° 旋转及任意角度旋转 |
| Resource browser / 资源浏览 | 当前文件夹缩略图浏览，按需加载可见区域 |
| File navigation / 文件导航 | 拖拽打开、Ctrl+V 粘贴路径、地址栏跳转、历史地址、文件名跳转 |
| Editing / 编辑 | 水印、背景设置、清除背景、旋转保存 |
| Conversion / 格式转换 | 当前图片格式转换及另存为 |
| Themes / 主题 | Explorer 浅色主题及其他主题 |
| Languages / 多语言 | 简体中文、繁體中文、日本語、English |
| Windows integration / 系统集成 | 系统托盘、开机启动、窗口置顶、默认看图软件、单窗口/多窗口模式 |
| NEF support / NEF 支持 | 内嵌 JPEG 快速预览、相邻图片预取、内存缓存、完整 RAW 解码 |
| Focus display / 对焦点显示 | 尝试从 EXIF 或 ExifTool 数据中读取 NEF 对焦区域 |
| Safety / 稳定性 | 超大图片预览限幅、后台加载、异常日志和未保存修改确认 |

---

## NEF / RAW Support / NEF 与 RAW 支持

My-First-view 10.10 对 Nikon NEF 文件做了专门优化：

1. 优先读取 NEF 中的相机内嵌 JPEG。
2. 缓存最近浏览的 NEF 预览。
3. 后台预取当前图片前后的 NEF 文件。
4. 浏览时使用快速预览，编辑或保存时再执行完整 RAW 解码。
5. 尝试读取 `SubjectArea`、`SubjectLocation` 等 EXIF 对焦坐标。
6. 可选调用 `exiftool.exe`，读取 Nikon MakerNotes 中更完整的对焦信息。

> 对焦框是否能显示，取决于相机型号和 NEF 文件中是否保存了可转换为画面坐标的数据。  
> 部分文件只保存对焦模式或对焦点名称，无法绘制精确位置。

将 `exiftool.exe` 放在程序或 EXE 同目录，可以提高部分 Nikon 文件的对焦信息识别能力。

---

## Requirements / 运行环境

### System / 系统

- Windows 10 或 Windows 11
- Python 3.10 或更高版本
- 推荐 Python 3.13

### Python packages / Python 依赖

```bash
pip install PyQt5 Pillow rawpy pillow-avif-plugin
```

用途：

| Package | Purpose / 用途 |
|---|---|
| `PyQt5` | 图形界面 |
| `Pillow` | 常规图片读取、处理和保存 |
| `rawpy` | NEF / RAW 解码与内嵌预览提取 |
| `pillow-avif-plugin` | AVIF 格式支持 |

### Optional dependency / 可选依赖

- `ExifTool`：增强 NEF 对焦点与 Nikon MakerNotes 信息读取。

---

## Installation / 源码运行

### 1. Clone repository / 克隆仓库

```bash
git clone https://github.com/YOUR_USERNAME/My-First-view.git
cd My-First-view
```

将 `YOUR_USERNAME` 替换为你的 GitHub 用户名。

### 2. Create virtual environment / 创建虚拟环境

```bat
python -m venv .venv
.venv\Scripts\activate
```

### 3. Install dependencies / 安装依赖

```bat
python -m pip install --upgrade pip
pip install PyQt5 Pillow rawpy pillow-avif-plugin
```

### 4. Run / 运行

```bat
python My-First-view10.10_EnglishMenu_Fixed.py
```

---

## Build EXE / 编译为 Windows EXE

### Install PyInstaller / 安装 PyInstaller

```bat
python -m pip install --upgrade pyinstaller
```

### Icon file / 图标文件

PyInstaller 的 Windows 图标必须使用 `.ico` 扩展名。

当前图标名若为：

```text
My-First-view.ioc
```

请先改名：

```bat
ren "My-First-view.ioc" "My-First-view.ico"
```

### Build command / 编译命令

```bat
python -m PyInstaller ^
  --noconfirm ^
  --clean ^
  --onefile ^
  --windowed ^
  --name "My-First-view10.10" ^
  --icon "My-First-view.ico" ^
  --collect-all rawpy ^
  --collect-all pillow_avif ^
  "My-First-view10.10_EnglishMenu_Fixed.py"
```

单行版本：

```bat
python -m PyInstaller --noconfirm --clean --onefile --windowed --name "My-First-view10.10" --icon "My-First-view.ico" --collect-all rawpy --collect-all pillow_avif "My-First-view10.10_EnglishMenu_Fixed.py"
```

编译完成后，程序位于：

```text
dist\My-First-view10.10.exe
```

---

## Usage / 使用方法

### Open images / 打开图片

可以使用以下方式打开图片：

- 将图片或文件夹拖入主窗口。
- 点击 `File / 文件` 菜单打开图片或文件夹。
- 按 `Ctrl + V` 粘贴图片路径或文件夹路径。
- 在顶部地址栏输入路径。
- 在 Windows 文件资源管理器中双击已关联的图片。
- 将图片文件拖到 EXE 上。

### Sort and group / 排序与分组

顶部编辑栏支持：

- Sort by：Name / Date / Type / Size
- Sort direction：Ascending / Descending
- Group by：None / Name / Date / Type / Size
- Group direction：Ascending / Descending

排序逻辑尽量与 Windows 文件资源管理器保持一致。

### Multi-view / 多窗口浏览

可选择：

- `1V1`
- `2V2`
- `1V2`
- `2V1`

并切换：

- `Linked`：各窗口联动切换
- `Separate`：各窗口独立浏览

---

## Shortcuts / 快捷键

| Shortcut / 快捷键 | Action / 功能 |
|---|---|
| `Ctrl + V` | 粘贴图片或文件夹路径并跳转 |
| `←` | 上一张图片，可长按 |
| `→` | 下一张图片，可长按 |
| `Delete` | 删除当前图片，Windows 下优先移入回收站 |
| `A` | 左旋转 90° |
| `D` | 右旋转 90° |
| `+` | 放大 |
| `-` | 缩小 |
| `0` | 适应窗口或恢复默认大小 |
| `Ctrl + T` | 显示或隐藏顶部编辑栏 |
| `Esc` | 退出程序 |

---

## System Tray / 系统托盘

系统托盘右键菜单支持：

- 显示或隐藏主窗口
- 打开图片
- 打开文件夹
- 上一张 / 下一张
- 适应窗口
- 100% 显示
- 显示或隐藏编辑栏
- 窗口置顶
- 开机启动
- 退出程序

---

## Supported Formats / 支持格式

| Format | Support |
|---|---|
| JPG / JPEG | Built-in / 内置 |
| PNG | Built-in / 内置 |
| BMP | Built-in / 内置 |
| GIF | First-frame preview / 首帧预览 |
| WEBP | Built-in / 内置 |
| TIFF / TIF | Built-in / 内置 |
| AVIF | Requires `pillow-avif-plugin` |
| NEF | Requires `rawpy` |

---

## Repository Structure / 建议仓库结构

```text
My-First-view/
├─ My-First-view10.10_EnglishMenu_Fixed.py
├─ My-First-view.ico
├─ README.md
├─ requirements.txt
├─ assets/
│  └─ My-First-view-logo.png
├─ docs/
│  └─ images/
│     └─ main-window.png
└─ LICENSE
```

`requirements.txt` 可以写成：

```text
PyQt5
Pillow
rawpy
pillow-avif-plugin
```

---

## Release Notes / 10.10 更新内容

- 修复英文界面部分菜单文字显示不完整的问题。
- 帮助窗口正文完整支持多语言。
- 修复资源浏览加载弹窗白底白字问题。
- 移除帮助窗口和加载窗口右上角的 `?`。
- 加载占位图数量与实际图片数量对应。
- 新增 NEF 快速预览与相邻图片缓存。
- 新增 NEF 对焦点显示选项。
- 支持可选 ExifTool 对焦信息增强。
- 优化资源浏览可见区域缩略图加载。
- 增加 Explorer 风格默认主题。
- 增加系统托盘、开机启动和窗口置顶。
- 支持隐藏顶部编辑栏。
- 优化单张图片启动速度和后台文件夹扫描。

---

## Known Limitations / 已知限制

- 项目主要针对 Windows，其他操作系统未完整适配。
- Windows 默认应用关联受系统 `UserChoice` 保护，部分设备仍需在系统设置中手动确认。
- 部分 NEF 文件没有足够大的内嵌 JPEG，会退回完整 RAW 解码。
- NEF 对焦点显示依赖文件中的可用坐标，不保证所有相机和文件都能显示。
- GIF 当前主要用于静态首帧预览。
- AVIF 需要额外安装 `pillow-avif-plugin`。

---

## Bug Report / 问题反馈

提交 Issue 时建议附上：

1. Windows 版本。
2. Python 版本。
3. 软件版本。
4. 操作步骤。
5. 错误截图。
6. 控制台报错或调试日志。
7. 出问题的图片格式和大致尺寸。

涉及 NEF 问题时，请说明：

- 相机型号
- NEF 文件尺寸
- 是否开启快速 NEF 预览
- 是否安装 `rawpy`
- 是否配置 `exiftool.exe`

---

## Contributing / 参与开发

欢迎通过以下方式参与：

- 提交 Bug
- 提出功能建议
- 改进多语言翻译
- 优化 Windows Explorer 排序兼容性
- 测试不同 Nikon 相机的 NEF 文件
- 提交 Pull Request

提交代码前建议先执行：

```bat
python -m py_compile My-First-view10.10_EnglishMenu_Fixed.py
```

---

## License / 许可证

当前项目尚未在本 README 中指定开源许可证。

公开发布前建议在仓库根目录添加 `LICENSE` 文件。未添加许可证时，默认不代表他人拥有复制、修改或分发代码的授权。

---

## Acknowledgements / 致谢

- [PyQt5](https://www.riverbankcomputing.com/software/pyqt/)
- [Pillow](https://python-pillow.org/)
- [rawpy](https://github.com/letmaik/rawpy)
- [ExifTool](https://exiftool.org/)
- [PyInstaller](https://pyinstaller.org/)

---

<p align="center">
  My-First-view 10.10<br>
  Windows Image Viewer / Windows 多格式图片浏览器
</p>
