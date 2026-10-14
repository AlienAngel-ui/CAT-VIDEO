# CAT VIDEO (v1.0.0) — 第三方授權與對應原始碼來源索引

本軟體 **CAT VIDEO (v1.0.0)** 為依據開放標準打造之參考素材下載工具。本產品之組件授權、相依性與上游原始碼對應資訊彙整如下：

---

## 一、隨發行包散布之元件 (Bundled Components)

以下元件隨公開發行包（`CAT-VIDEO-v1.0.0-win-x64.zip`）直接提供：

### 1. CAT VIDEO UI & Core
- **授權**：QIAU studio Free Public Edition
- **用途**：桌面介面互動、下載狀態管理、非同步程序呼叫與防呆控制。

### 2. Microsoft .NET 10.0.11 Runtime (win-x64)
- **檔案數量**：395 個檔案（Self-Contained 部署）
- **核對依據**：全部雜湊經與微軟官方 NuGet package 比對 100% 相符。
- **適用授權**：
  - 核心程式庫：**MIT License**（請參閱隨包 `licenses/NETCore-MIT-LICENSE.txt` 與 `licenses/WindowsDesktop-MIT-LICENSE.txt`）。
  - 第三方相依聲明：請參閱隨包 `licenses/NETCore-THIRD-PARTY-NOTICES.txt`。
  - 微軟專屬 Native 程式庫（`coreclr.dll`, `Microsoft.DiaSymReader.Native.amd64.dll`, `PresentationNative_cor3.dll`, `vcruntime140_cor3.dll`, `wpfgfx_cor3.dll`）：受 **Microsoft .NET Library License** 管轄（請參閱隨包 `licenses/Microsoft-DotNet-Library-License.html`）。
  - 微軟 Windows SDK 程式庫（`D3DCompiler_47_cor3.dll`）：受 **Microsoft Windows SDK License** 管轄（請參閱隨包 `licenses/Microsoft-Windows-SDK-License.txt`）。
- **對應原始碼**：
  - .NET Runtime：`https://github.com/dotnet/runtime/tree/v10.0.11`
  - .NET WPF：`https://github.com/dotnet/wpf/tree/v10.0.11`

### 3. Node.js
- **版本**：v24.19.0 (win-x64)
- **檔案**：`tools/node.exe`
- **適用授權**：**MIT License**（請參閱隨包 `licenses/Node-LICENSE.txt`）。
- **對應原始碼**：`https://github.com/nodejs/node/tree/v24.19.0`

---

## 二、首次執行自動取得之元件 (Runtime-Fetched Components)

為符合自由軟體散布規範並減輕公開發行包體積，以下元件**不包含在公開 ZIP 內**，而是由軟體於首次點擊下載時，由終端環境自動自原廠官方 HTTPS 取得，並於本機私有快取目錄進行嚴格 SHA256 雜湊核對：

### 1. yt-dlp (純 zipapp 版)
- **版本**：2026.08.19
- **檔案**：`yt-dlp` (純 zipapp，免除內建微軟 VCRUNTIME 之授權問題)
- **官方來源**：`https://github.com/yt-dlp/yt-dlp/releases/download/2026.08.19/yt-dlp`
- **SHA256**：`1fa6733c37ea6fb51c99ad8fe785e7b7e5f3246c9b980230329d4fb72ed8d4d6`
- **授權**：**The Unlicense (Public Domain)**（隨包備有 `licenses/Downloaded-components/yt-dlp-2026.08.19-UNLICENSE.txt`）。
- **原始碼**：`https://github.com/yt-dlp/yt-dlp/tree/2026.08.19`

### 2. Python (嵌入式環境)
- **版本**：3.14.7 (Windows x64 Embeddable zip)
- **官方來源**：`https://www.python.org/ftp/python/3.14.7/python-3.14.7-embed-amd64.zip`
- **SHA256**：`d297e5ff019966817ad8502465176139f2d3d840fa4ed84b13bed399a6ab1f15`
- **授權**：**Python Software Foundation License Version 2**（隨包備有 `licenses/Downloaded-components/Python-3.14.7-LICENSE.txt`）。
- **原始碼**：`https://github.com/python/cpython/tree/v3.14.7`

### 3. FFmpeg & FFprobe (BtbN 月末 LGPL 構建版)
- **版本**：n9.0.2-17-g2a571b6068 (Windows x64 LGPL)
- **官方來源**：`https://github.com/BtbN/FFmpeg-Builds/releases/download/autobuild-2026-09-30-13-08/ffmpeg-n9.0.2-17-g2a571b6068-win64-lgpl-9.0.zip`
- **SHA256**：`6b264b9e6019103f601d98c292bd332fd87acf1c5e941ddff4fb71760fe63432`
- **授權**：**GNU Lesser General Public License version 3 (LGPLv3)**（隨包備有 `licenses/Downloaded-components/FFmpeg-COPYING.LGPLv3.txt`）。
- **對應原始碼與編譯指令碼**：
  - FFmpeg 精確 Commit：`https://github.com/FFmpeg/FFmpeg/tree/2a571b6068`
  - BtbN Build Recipes：`https://github.com/BtbN/FFmpeg-Builds`

### 4. 輔助 Python 輪子庫 (Wheels from PyPI)
- **`curl_cffi` 0.16.0** (MIT License, SHA256: `e22a8212...`)
- **`cffi` 2.1.0** (MIT License, SHA256: `1b96bfe2...`)
- **`certifi` 2026.7.22** (MPL-2.0, SHA256: `62f22742...`)
- **`pycparser` 2.23** (BSD-3-Clause, SHA256: `e5c6e8d3...`)
- 以上元件條款全文均存放於 `licenses/Downloaded-components/`。
