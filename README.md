
<h1 align="center">My-First-view </h1>

<p align="center">
  A Windows image viewer with Explorer-style sorting, multi-view layouts, RAW/NEF support, fast preview, tray integration, and multilingual UI.<br>
  一款面向 Windows 的多格式图片浏览器，支持资源管理器式排序、多窗口预览、NEF 快速浏览、系统托盘和多语言界面。<br>
  Windows 向けの多形式画像ビューアー。Explorer 風の並べ替え、マルチビュー、RAW/NEF、高速プレビュー、システムトレイ、多言語 UI に対応。
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-0078D4" alt="Windows">
  <img src="https://img.shields.io/badge/Distribution-Binary%20Release-555555" alt="Binary Release">
  <img src="https://img.shields.io/badge/Version-10.10-blue" alt="Version">
  <img src="https://img.shields.io/badge/Source%20Code-Not%20Published-lightgrey" alt="Source Code Not Published">
</p>

<p align="center">
  <a href="#简体中文">简体中文</a> ·
  <a href="#english">English</a> ·
  <a href="#日本語">日本語</a>
</p>

---

## Preview / 软件预览 / プレビュー

<img width="1663" height="860" alt="2026-07-11_14-49-16" src="https://github.com/user-attachments/assets/2474aa54-9d20-491e-b185-6e1a0669465f" />
<img width="1663" height="860" alt="2026-07-11_15-04-01" src="https://github.com/user-attachments/assets/55b2b1c8-6838-4d2c-bd53-03fecd27cc6f" />
<img width="1663" height="860" alt="2026-07-11_15-04-23" src="https://github.com/user-attachments/assets/30b5e369-f7fc-47b1-859a-1b9b39e33c82" />



---

# 简体中文

## 作品介绍

**My-First-view** 是一款面向 Windows 10 和 Windows 11 的多格式图片浏览器。

本仓库用于：

- 发布软件成品
- 提供版本更新说明
- 展示软件截图
- 收集 Bug 反馈和功能建议
- 提供 Windows EXE 下载

本项目**不公开源代码**。仓库中的 Release 文件仅用于软件安装、体验和版本发布。

## 下载与安装

前往本仓库右侧的 **Releases** 页面，下载最新版本：

```text
My-First-view10.10.exe
```

下载完成后可直接运行，无需安装 Python。

如 Windows SmartScreen 提示“Windows 已保护你的电脑”，可点击：

```text
更多信息 → 仍要运行
```

建议将程序放在固定目录中，例如：

```text
C:\Program Files\My-First-view\
```

或：

```text
D:\Software\My-First-view\
```

不要长期放在下载目录中运行，以免开机启动、默认看图软件关联或配置文件路径发生变化。

## 主要功能

| 类别 | 功能 |
|---|---|
| 图片格式 | JPG、JPEG、PNG、BMP、GIF、WEBP、TIFF、AVIF、NEF |
| 快速启动 | 当前图片优先显示，文件夹扫描与邻近图片读取在后台进行 |
| 资源管理器排序 | 支持 Name、Date、Type、Size 排序与分组，支持 Ascending / Descending |
| 多窗口预览 | 支持 `1V1`、`2V2`、`1V2`、`2V1` 布局 |
| 联动浏览 | 多窗口可选择 Linked 联动或 Separate 独立切换 |
| 缩放 | 适应窗口、100% 显示、按钮缩放、滑块缩放、滚轮缩放 |
| 旋转 | 左右 90° 旋转及任意角度旋转 |
| 资源浏览 | 当前文件夹缩略图浏览，按需加载可见区域 |
| 文件导航 | 拖拽打开、Ctrl+V 粘贴路径、地址栏跳转、历史地址、文件名跳转 |
| 编辑 | 水印、背景设置、清除背景、旋转保存 |
| 格式转换 | 当前图片格式转换及另存为 |
| 主题 | Explorer 浅色主题及其他主题 |
| 多语言 | 简体中文、繁體中文、日本語、English |
| 系统集成 | 系统托盘、开机启动、窗口置顶、默认看图软件、单窗口/多窗口模式 |
| NEF 支持 | 内嵌 JPEG 快速预览、相邻图片预取、内存缓存、完整 RAW 解码 |
| 对焦点显示 | 尝试读取 NEF 文件中的对焦区域信息 |
| 稳定性 | 超大图片预览限幅、后台加载、异常日志和未保存修改确认 |

## NEF 与 RAW 支持

My-First-view 10.10 对 Nikon NEF 文件进行了专门优化：

1. 优先读取 NEF 中的相机内嵌 JPEG。
2. 缓存最近浏览的 NEF 预览。
3. 后台预取当前图片前后的 NEF 文件。
4. 浏览时使用快速预览，编辑或保存时再执行完整 RAW 解码。
5. 尝试读取 `SubjectArea`、`SubjectLocation` 等对焦坐标。
6. 可选调用 `exiftool.exe`，读取 Nikon MakerNotes 中更完整的对焦信息。

> 对焦框能否显示，取决于相机型号和 NEF 文件中是否保存了可转换为画面坐标的数据。  
> 部分文件只保存对焦模式或对焦点名称，无法绘制精确位置。

将 `exiftool.exe` 放在程序 EXE 同目录，可以提高部分 Nikon 文件的对焦信息识别能力。

## 使用方法

### 打开图片

可以使用以下方式：

- 将图片或文件夹拖入主窗口。
- 点击 `文件 / File` 菜单打开图片或文件夹。
- 按 `Ctrl + V` 粘贴图片路径或文件夹路径。
- 在顶部地址栏输入图片或文件夹路径。
- 将图片文件拖到 EXE 上。
- 设置为默认看图软件后，在资源管理器中双击图片。

### 排序与分组

顶部编辑栏支持：

- Sort by：Name / Date / Type / Size
- Sort direction：Ascending / Descending
- Group by：None / Name / Date / Type / Size
- Group direction：Ascending / Descending

排序逻辑尽量与 Windows 文件资源管理器保持一致。

### 多窗口浏览

可选择：

- `1V1`
- `2V2`
- `1V2`
- `2V1`

并切换：

- `Linked`：各窗口联动切换
- `Separate`：各窗口独立浏览

## 快捷键

| 快捷键 | 功能 |
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

## 系统托盘

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

## 支持格式

| 格式 | 支持情况 |
|---|---|
| JPG / JPEG | 支持 |
| PNG | 支持 |
| BMP | 支持 |
| GIF | 首帧预览 |
| WEBP | 支持 |
| TIFF / TIF | 支持 |
| AVIF | 支持 |
| NEF | 支持 |

## 10.10 更新内容

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

## 已知限制

- 软件主要针对 Windows 10 和 Windows 11。
- Windows 默认应用关联受系统 `UserChoice` 保护，部分设备仍需在系统设置中手动确认。
- 部分 NEF 文件没有足够大的内嵌 JPEG，会退回完整 RAW 解码。
- NEF 对焦点显示依赖文件中的可用坐标，不保证所有相机和文件都能显示。
- GIF 当前主要用于静态首帧预览。
- 极大的 RAW 文件首次完整解码时仍可能需要等待。

## 问题反馈

请通过 GitHub **Issues** 提交问题，并尽量附上：

1. Windows 版本
2. 软件版本
3. 操作步骤
4. 错误截图
5. 调试日志
6. 出问题的图片格式和大致尺寸

涉及 NEF 问题时，请补充：

- 相机型号
- NEF 文件尺寸
- 是否开启快速 NEF 预览
- 是否配置 `exiftool.exe`

## 关于源代码与使用权限

本仓库仅用于发布 My-First-view 软件作品及其更新。

- 源代码未公开。
- 未经作者明确许可，不得反编译、修改后重新发布、重新打包或冒用软件名称。
- 不得将本软件用于违法用途。
- 软件 Logo、名称、界面设计和发布文件归作者所有。
- 个人用户可以下载并正常使用 Release 中提供的软件版本。

---

# English

## About This Project

**My-First-view** is a multi-format image viewer for Windows 10 and Windows 11.

This repository is used to:

- Publish finished software releases
- Provide release notes
- Display screenshots
- Collect bug reports and feature requests
- Distribute Windows executable files

The source code is **not publicly available**. Files provided through GitHub Releases are intended only for installing, evaluating, and using the application.

## Download and Installation

Open the repository's **Releases** page and download the latest version:

```text
My-First-view10.10.exe
```

The executable can be launched directly. Python is not required.

If Windows SmartScreen displays a warning, select:

```text
More info → Run anyway
```

It is recommended to place the application in a fixed directory, for example:

```text
C:\Program Files\My-First-view\
```

or:

```text
D:\Software\My-First-view\
```

Avoid running it permanently from the Downloads folder, because moving the executable later may affect startup registration, default-viewer association, or configuration paths.

## Features

| Category | Features |
|---|---|
| Image formats | JPG, JPEG, PNG, BMP, GIF, WEBP, TIFF, AVIF, NEF |
| Fast startup | Shows the current image first while folder scanning and neighbor loading continue in the background |
| Explorer-style sorting | Sort and group by Name, Date, Type, and Size; Ascending / Descending supported |
| Multi-view layouts | `1V1`, `2V2`, `1V2`, and `2V1` |
| Linked viewing | Linked mode for synchronized windows or Separate mode for independent browsing |
| Zoom | Fit to window, 100%, button zoom, slider zoom, and mouse-wheel zoom |
| Rotation | 90° left/right rotation and arbitrary-angle rotation |
| Resource browser | Thumbnail browser for the current folder with on-demand visible-item loading |
| File navigation | Drag and drop, Ctrl+V path paste, address bar, history, and filename jump |
| Editing | Watermark, background image, clear background, and rotation save |
| Conversion | Convert the current image or save it in another format |
| Themes | Explorer-style light theme and additional themes |
| Languages | Simplified Chinese, Traditional Chinese, Japanese, and English |
| Windows integration | System tray, startup launch, always-on-top, default viewer, single-window and multi-window modes |
| NEF support | Embedded JPEG preview, neighbor prefetching, memory cache, and full RAW decoding |
| Focus display | Attempts to read NEF focus-area information |
| Stability | Large-image preview limits, background loading, crash logs, and unsaved-change confirmation |

## NEF / RAW Support

My-First-view 10.10 includes dedicated Nikon NEF optimizations:

1. Reads the camera-embedded JPEG first.
2. Caches recently viewed NEF previews.
3. Prefetches NEF files before and after the current image.
4. Uses fast preview for browsing and full RAW decoding for editing or saving.
5. Attempts to read focus coordinates such as `SubjectArea` and `SubjectLocation`.
6. Can optionally call `exiftool.exe` for more complete Nikon MakerNotes focus information.

> Whether a focus box can be drawn depends on the camera model and whether the NEF file contains coordinates that can be mapped to the image.  
> Some files store only focus mode or focus-point names and cannot provide exact display coordinates.

Place `exiftool.exe` beside the application EXE to improve focus-data recognition for some Nikon files.

## Usage

### Open Images

- Drag an image or folder into the main window.
- Use `File` to open an image or folder.
- Press `Ctrl + V` to paste an image or folder path.
- Enter a path in the top address bar.
- Drag an image file onto the EXE.
- Set the program as the default viewer and double-click images in Windows File Explorer.

### Sort and Group

The top toolbar supports:

- Sort by: Name / Date / Type / Size
- Sort direction: Ascending / Descending
- Group by: None / Name / Date / Type / Size
- Group direction: Ascending / Descending

The application attempts to follow Windows File Explorer sorting behavior.

### Multi-view Browsing

Available layouts:

- `1V1`
- `2V2`
- `1V2`
- `2V1`

Modes:

- `Linked`: windows navigate together
- `Separate`: windows browse independently

## Shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl + V` | Paste an image or folder path and jump to it |
| `←` | Previous image; hold to repeat |
| `→` | Next image; hold to repeat |
| `Delete` | Delete the current image; moves it to the Recycle Bin when possible |
| `A` | Rotate left by 90° |
| `D` | Rotate right by 90° |
| `+` | Zoom in |
| `-` | Zoom out |
| `0` | Fit to window or restore the default size |
| `Ctrl + T` | Show or hide the top toolbar |
| `Esc` | Exit |

## System Tray

The tray context menu includes:

- Show or hide the main window
- Open image
- Open folder
- Previous / next image
- Fit to window
- 100% view
- Show or hide toolbar
- Always on top
- Launch at startup
- Exit

## Supported Formats

| Format | Support |
|---|---|
| JPG / JPEG | Supported |
| PNG | Supported |
| BMP | Supported |
| GIF | First-frame preview |
| WEBP | Supported |
| TIFF / TIF | Supported |
| AVIF | Supported |
| NEF | Supported |

## Release Notes — 10.10

- Fixed truncated English toolbar labels.
- Added full multilingual help content.
- Fixed unreadable white text in the resource-loading dialog.
- Removed the `?` button from help and loading dialogs.
- Matched loading placeholders to the actual number of images.
- Added fast NEF previews and neighbor-image caching.
- Added optional NEF focus-point display.
- Added optional ExifTool focus-information enhancement.
- Optimized visible-area thumbnail loading.
- Added the Explorer-style default theme.
- Added system tray, startup launch, and always-on-top support.
- Added toolbar show/hide support.
- Improved single-image startup speed and background folder scanning.

## Known Limitations

- The application primarily targets Windows 10 and Windows 11.
- Windows default-app association is protected by `UserChoice`, so some systems may require manual confirmation.
- Some NEF files do not contain a sufficiently large embedded JPEG and must fall back to full RAW decoding.
- NEF focus display depends on usable coordinate data and is not guaranteed for every camera or file.
- GIF is mainly handled as a static first-frame preview.
- Very large RAW files may still take time during the first full decode.

## Bug Reports

Please use GitHub **Issues** and include:

1. Windows version
2. Application version
3. Reproduction steps
4. Screenshots
5. Debug log
6. Image format and approximate dimensions

For NEF-related issues, also include:

- Camera model
- NEF file size
- Whether fast NEF preview is enabled
- Whether `exiftool.exe` is configured

## Source Code and Usage Terms

This repository is used only to publish My-First-view software releases and updates.

- The source code is not published.
- Reverse engineering, modified redistribution, repackaging, or impersonation of the software name is not permitted without explicit authorization.
- The software must not be used for unlawful purposes.
- The application name, logo, interface design, and release files remain the property of the author.
- Individual users may download and use the versions provided through GitHub Releases.

---

# 日本語

## 作品概要

**My-First-view** は、Windows 10 / 11 向けの多形式画像ビューアーです。

このリポジトリは、次の目的で使用します。

- 完成版ソフトウェアの公開
- バージョン更新情報の提供
- スクリーンショットの掲載
- 不具合報告と機能要望の受付
- Windows EXE の配布

ソースコードは**公開していません**。GitHub Releases で提供するファイルは、ソフトウェアのインストール、試用、利用を目的としています。

## ダウンロードとインストール

リポジトリの **Releases** ページから最新版をダウンロードしてください。

```text
My-First-view10.10.exe
```

EXE はそのまま実行でき、Python のインストールは不要です。

Windows SmartScreen の警告が表示された場合：

```text
詳細情報 → 実行
```

固定フォルダーへ配置することを推奨します。

```text
C:\Program Files\My-First-view\
```

または：

```text
D:\Software\My-First-view\
```

ダウンロードフォルダーから長期間実行すると、後で EXE を移動した際に自動起動、既定ビューアー関連付け、設定ファイルのパスへ影響する可能性があります。

## 主な機能

| カテゴリ | 機能 |
|---|---|
| 画像形式 | JPG、JPEG、PNG、BMP、GIF、WEBP、TIFF、AVIF、NEF |
| 高速起動 | 現在の画像を先に表示し、フォルダー走査と前後画像の読み込みをバックグラウンドで実行 |
| エクスプローラー風の並べ替え | Name、Date、Type、Size による並べ替え・グループ化、昇順 / 降順 |
| マルチビュー | `1V1`、`2V2`、`1V2`、`2V1` |
| 連動表示 | Linked で同期、Separate で独立表示 |
| ズーム | ウィンドウに合わせる、100%、ボタン、スライダー、マウスホイール |
| 回転 | 左右 90° 回転、任意角度回転 |
| リソースブラウザー | 現在のフォルダーのサムネイルを表示し、可視範囲のみ必要に応じて読み込み |
| ファイル移動 | ドラッグ＆ドロップ、Ctrl+V、アドレスバー、履歴、ファイル名ジャンプ |
| 編集 | 透かし、背景設定、背景解除、回転保存 |
| 形式変換 | 現在の画像の変換、別形式で保存 |
| テーマ | Explorer 風のライトテーマなど |
| 多言語 | 簡体字中国語、繁体字中国語、日本語、英語 |
| Windows 連携 | システムトレイ、自動起動、常に手前、既定ビューアー、単一 / 複数ウィンドウ |
| NEF 対応 | 埋め込み JPEG、高速プレビュー、前後画像の先読み、メモリキャッシュ、完全 RAW デコード |
| フォーカス表示 | NEF 内のフォーカス領域情報を取得 |
| 安定性 | 巨大画像のプレビュー制限、バックグラウンド読み込み、例外ログ、未保存確認 |

## NEF / RAW 対応

My-First-view 10.10 では Nikon NEF 向けに次の最適化を行っています。

1. NEF 内のカメラ埋め込み JPEG を優先して読み込みます。
2. 最近表示した NEF プレビューをキャッシュします。
3. 現在の画像の前後にある NEF をバックグラウンドで先読みします。
4. 閲覧時は高速プレビューを使用し、編集・保存時に完全 RAW デコードを行います。
5. `SubjectArea`、`SubjectLocation` などのフォーカス座標を取得します。
6. 必要に応じて `exiftool.exe` を利用し、Nikon MakerNotes の詳細なフォーカス情報を取得します。

> フォーカス枠を表示できるかどうかは、カメラ機種と NEF 内に画面座標へ変換可能な情報が保存されているかによって決まります。  
> フォーカスモードやポイント名だけが保存されているファイルでは、正確な位置を描画できません。

`exiftool.exe` をアプリケーション EXE と同じフォルダーに置くと、一部の Nikon ファイルでフォーカス情報の取得率が向上します。

## 使い方

### 画像を開く

- 画像またはフォルダーをメインウィンドウへドラッグします。
- `File` メニューから画像またはフォルダーを開きます。
- `Ctrl + V` で画像またはフォルダーのパスを貼り付けます。
- 上部アドレスバーへパスを入力します。
- 画像ファイルを EXE へドラッグします。
- 既定ビューアーに設定後、Windows エクスプローラーで画像をダブルクリックします。

### 並べ替えとグループ化

上部ツールバーでは次を選択できます。

- Sort by：Name / Date / Type / Size
- Sort direction：Ascending / Descending
- Group by：None / Name / Date / Type / Size
- Group direction：Ascending / Descending

並べ替え動作は、可能な限り Windows エクスプローラーに合わせています。

### マルチビュー

利用可能なレイアウト：

- `1V1`
- `2V2`
- `1V2`
- `2V1`

表示モード：

- `Linked`：各ウィンドウを同期
- `Separate`：各ウィンドウを独立操作

## ショートカット

| ショートカット | 動作 |
|---|---|
| `Ctrl + V` | 画像またはフォルダーのパスを貼り付けて移動 |
| `←` | 前の画像。長押し対応 |
| `→` | 次の画像。長押し対応 |
| `Delete` | 現在の画像を削除。可能な場合はごみ箱へ移動 |
| `A` | 左へ 90° 回転 |
| `D` | 右へ 90° 回転 |
| `+` | 拡大 |
| `-` | 縮小 |
| `0` | ウィンドウに合わせる / 既定サイズへ戻す |
| `Ctrl + T` | 上部ツールバーの表示 / 非表示 |
| `Esc` | 終了 |

## システムトレイ

トレイの右クリックメニュー：

- メインウィンドウの表示 / 非表示
- 画像を開く
- フォルダーを開く
- 前の画像 / 次の画像
- ウィンドウに合わせる
- 100% 表示
- ツールバーの表示 / 非表示
- 常に手前
- Windows 起動時に実行
- 終了

## 対応形式

| 形式 | 対応 |
|---|---|
| JPG / JPEG | 対応 |
| PNG | 対応 |
| BMP | 対応 |
| GIF | 先頭フレームのプレビュー |
| WEBP | 対応 |
| TIFF / TIF | 対応 |
| AVIF | 対応 |
| NEF | 対応 |

## 10.10 リリースノート

- 英語 UI の一部ツールバー文字切れを修正。
- ヘルプ本文を完全な多言語対応に変更。
- リソース読み込みダイアログの白地に白文字となる問題を修正。
- ヘルプと読み込みダイアログの `?` ボタンを削除。
- 読み込みプレースホルダー数を実際の画像数に合わせるよう変更。
- NEF 高速プレビューと前後画像キャッシュを追加。
- NEF フォーカスポイント表示を追加。
- 任意の ExifTool フォーカス情報強化を追加。
- 可視範囲サムネイル読み込みを最適化。
- Explorer 風の既定テーマを追加。
- システムトレイ、自動起動、常に手前を追加。
- ツールバーの表示 / 非表示を追加。
- 単一画像起動とバックグラウンドフォルダー走査を高速化。

## 既知の制限

- Windows 10 / 11 を主な対象としています。
- Windows の既定アプリ関連付けは `UserChoice` で保護されているため、手動確認が必要な場合があります。
- 十分な大きさの埋め込み JPEG がない NEF は、完全 RAW デコードへ切り替わります。
- NEF フォーカス表示は利用可能な座標データに依存し、すべてのカメラ・ファイルで保証されません。
- GIF は主に静止した先頭フレームとして表示されます。
- 非常に大きな RAW ファイルは、最初の完全デコードに時間がかかる場合があります。

## 不具合報告

GitHub **Issues** に次の情報を添付してください。

1. Windows のバージョン
2. アプリのバージョン
3. 再現手順
4. スクリーンショット
5. デバッグログ
6. 問題が発生した画像形式とおおよそのサイズ

NEF 関連の場合：

- カメラ機種
- NEF ファイルサイズ
- 高速 NEF プレビューの有効 / 無効
- `exiftool.exe` の設定有無

## ソースコードと利用条件

このリポジトリは、My-First-view のソフトウェア作品と更新版を公開するためのものです。

- ソースコードは公開していません。
- 作者の明示的な許可なく、リバースエンジニアリング、改変版の再配布、再パッケージ化、名称の詐称を行わないでください。
- 違法な目的で使用しないでください。
- ソフトウェア名、ロゴ、UI デザイン、配布ファイルの権利は作者に帰属します。
- 個人ユーザーは GitHub Releases で提供されるバージョンをダウンロードして利用できます。

---

## Acknowledgements / 致谢 / 謝辞

- [PyQt5](https://www.riverbankcomputing.com/software/pyqt/)
- [Pillow](https://python-pillow.org/)
- [rawpy](https://github.com/letmaik/rawpy)
- [ExifTool](https://exiftool.org/)
- [PyInstaller](https://pyinstaller.org/)

---

<p align="center">
  My-First-view 10.10<br>
  Windows Image Viewer / Windows 多格式图片浏览器 / Windows 向け画像ビューアー
</p>
