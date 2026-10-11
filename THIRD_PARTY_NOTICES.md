# 第三方元件

遊譯工坊以 PyInstaller 6.22.2 打包成單一 exe，內含 CPython 3.10.6、Tcl/Tk 8.6 與 Python 標準函式庫。

- Python（PSF 授權）：見 `licenses/PYTHON-LICENSE.txt`。
- PyInstaller 的 bootloader 採 GPL，並附有允許分發打包程式的例外條款：見 `licenses/PYINSTALLER-COPYING.txt`。

## Unity 修改面板用的載入器

Unity 遊戲的修改面板需要 BepInEx 載入器。發佈的 exe 不內含這些檔案；第一次替 Unity 遊戲安裝面板時，工坊才從官方發行頁下載未修改的壓縮檔，並以固定的 SHA-256 核對。

- BepInEx 5.4.23.5（MIT 授權，Copyright (c) 2018 Bepis）：Mono 遊戲使用，取自 <https://github.com/BepInEx/BepInEx/releases/tag/v5.4.23.5>，授權見 `licenses/BEPINEX-LICENSE.txt`。
- BepInEx 6.0.0-be.788（MIT 授權）：IL2CPP 遊戲使用，取自 <https://builds.bepinex.dev/projects/bepinex_be>，內含 Il2CppInterop、Cpp2IL 與隨附的 .NET 執行環境，授權見各元件的原始倉庫與 `licenses/BEPINEX-LICENSE.txt`。
- Unity Doorstop（LGPL-2.1）：BepInEx 發行檔內的 `winhttp.dll` 與 `doorstop_config.ini`，原始碼見 <https://github.com/NeighTools/UnityDoorstop>，授權見 `licenses/UNITY-DOORSTOP-LICENSE.txt`。工坊以未修改的形式安裝這些檔案，可以從「解除安裝修改面板」完整移除。

工坊放進遊戲的 Unity 面板（`YouyiUnityPanel.dll`、`YouyiUnityPanelIl2Cpp.dll`）與 RPG Maker 面板（`rpg_workbench_runtime.js`）都是本專案的原創程式碼，只使用 BepInEx、Unity 與 RPG Maker 的公開 API。

## Ren'Py 與 RPG Maker XP／VX／VX Ace 修改面板

Ren'Py 的面板（`youyi_workbench.rpy`、`youyi_workbench_renpy.py`）與 RPG Maker XP／VX／VX Ace 的面板（`youyi_workbench.rb`）都是本專案的原創程式碼，只使用引擎公開的腳本介面與 Windows 內建的 Winsock。工坊不附帶也不下載 Ren'Py 或 RGSS 執行檔；讀取加密封裝檔只為了取出遊戲自己的腳本，不會修改或重新封裝。

## numpy

記憶體數值搜尋使用 numpy 2.2.6（BSD 3-Clause 授權，wheel 內附的 OpenBLAS 等元件授權一併收在同一份檔案），隨程式打包。授權全文見 `licenses/NUMPY-LICENSE.txt`。

## Godot 修改面板

Godot 遊戲的面板（`youyi_workbench_panel.gd`）是本專案的原創 GDScript，只使用 Godot 引擎的公開 API，透過遊戲資料夾的 `override.cfg` 載入。工坊不附帶也不下載 Godot 引擎本身。
