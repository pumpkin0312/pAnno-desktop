# 版权与第三方组件声明

pAnno-desktop 发行包由以下几部分组成。图形界面部分以 MIT 许可发布（见 `LICENSE`）；
其余组件的版权与许可各自独立，列于下文。

---

# 一、分析程序

## pAnno

- 开发者：中国科学院计算技术研究所 pFind 团队（王凯菲 等）
- 位置：`pAnnobin/`（`pAnno.exe`、`SplicingFinder.exe` 及同目录的 `lib*.dll`）
- 版权归原作者所有。本发行包中的 `pAnno.exe` 包含 v0.3.0 的修复（见《更新说明》）。

## DBReducer

- 开发者：王凯菲（中国科学院计算技术研究所）
- 位置：`pAnnobin/thirdparty/DBReducer/`
- 版权归原作者所有。本发行包中的 `DBReducer.exe` 包含 v0.3.0 的修复。

## pFind（pAnno 定制版）

- 本包中的 pFind 是**基于 pFind 3.2.3 定制、专门用于 pAnno 的版本**
- 开发者：中国科学院计算技术研究所 pFind 团队
- 项目主页：http://pfind.org
- 位置：`pAnnobin/thirdparty/pFind3/`
- 版权归 pFind 团队所有，**经 pFind 团队授权随本发行包分发**。
- 与 pFind 3.2.3 相比，`libTagFlow.dll`、`libETagFlow.dll`、`libProSalvoFT.dll`、`libPeXSDK.dll` 四个动态库经过修改：
  - 修复了搜索线程等待中偶发的卡死；
  - 读库时不再一开始就按整个库的条目数预留内存。
- 随附的用户手册（`pFind 3 UserGuide.pdf`、`pBuild user manual.pdf`、`pFind3-result-interpretation-v3.1.5.pdf`）版权同属 pFind 团队。

### pFind 3 中未随本包分发的部分

pFind 3 的完整安装目录里还捆绑了一批厂商库与工具。本包只保留 pAnno 两轮搜库实际用到的
8 个可执行文件和 12 个动态库，**以下组件不在本包内**：

- Thermo Fisher Scientific CommonCore / RawFileReader（读 `.raw`）
- SCIEX Clearcore2（读 `.wiff`）
- E-iceblue Spire.Doc / Spire.Pdf（生成 Word / PDF 报告）
- DocumentFormat.OpenXml、PdfSharp、Xceed.Wpf.Toolkit、log4net
- Bruker timsdata（读 timsTOF）
- Oracle JRE 安装器
- pParse / pParse2Plus 及各 `xtract_*`（原始质谱格式转换；pAnno 直接读取 `.mgf`，不经过这一步）

如果你从别处获取完整的 pFind 3，这些组件各自的条款仍然适用。

---

# 二、运行库

## MinGW-w64 / GCC 运行库

- 文件：`libgcc_s_seh-1.dll`、`libgcc_s_sjlj-1.dll`、`libstdc++-6.dll`、`libgomp-1.dll`、`libwinpthread-1.dll`
  （分布在 `pAnnobin/`、`pAnnobin/thirdparty/DBReducer/`、`pAnnobin/thirdparty/pFind3/bin/` 中）
- `libgcc_s`、`libstdc++`、`libgomp`：GNU GPLv3，附 **GCC Runtime Library Exception**。该例外允许以任意条款分发链接了它们的程序。
  条款见 https://www.gnu.org/licenses/gcc-exception-3.1.html
- `libwinpthread`：MinGW-w64 winpthreads，MIT 风格许可。见 https://www.mingw-w64.org

## GMP（GNU Multiple Precision Arithmetic Library）

- 文件：`libgmp-10.dll`、`libgmpxx-4.dll`
- 许可：**GNU LGPLv3**（或 GPLv2，二选一）
- 源代码：https://gmplib.org
- 以独立动态库形式提供，可以用兼容版本替换。

---

# 三、图形界面使用的组件

## Qt / PySide6

- 项目主页：https://www.qt.io/qt-for-python
- 版权：The Qt Company Ltd. 及贡献者
- 许可：**GNU Lesser General Public License v3 (LGPLv3)**，全文见 https://www.gnu.org/licenses/lgpl-3.0.html

图形界面通过 PySide6 动态调用 Qt 库，Qt 的动态链接库（`.dll`、`.pyd`）随包提供。

**关于替换 Qt 库（LGPLv3 第 4 节）**：
- 本程序采用 PyInstaller 的 one-folder 模式打包，Qt 动态库以独立文件存放在 `pAnnoGUI/_internal/` 下，没有加壳，也没有静态链接。
- 使用者可以用自行编译或修改过的、二进制兼容的 Qt 版本替换这些文件，程序会加载替换后的版本。
- Qt 源代码可从 https://download.qt.io/ 获取。

## Python 标准库及运行时

- 版权：Python Software Foundation
- 许可：Python Software Foundation License (PSF-2.0)，见 https://docs.python.org/3/license.html

## psutil

- 项目主页：https://github.com/giampaolo/psutil
- 版权：Giampaolo Rodola
- 许可：BSD 3-Clause

## PyInstaller 引导程序（bootloader）

- 项目主页：https://pyinstaller.org
- 许可：GPLv2，附例外条款。该例外明确允许用其打包的程序以任意许可分发。
  见 https://github.com/pyinstaller/pyinstaller/blob/develop/COPYING.txt

---

如发现遗漏或标注有误，欢迎提 issue 指出。
