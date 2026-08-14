# 第三方组件声明

pAnnoGUI 的分发包中包含以下第三方组件。它们各自的许可条款独立于本程序的
MIT 许可，以下列出以履行相应义务。

---

## Qt / PySide6

- 项目主页：https://www.qt.io/qt-for-python
- 版权：The Qt Company Ltd. 及贡献者
- 许可：**GNU Lesser General Public License v3 (LGPLv3)**
- 许可全文：https://www.gnu.org/licenses/lgpl-3.0.html

pAnnoGUI 通过 Python 的 PySide6 绑定动态调用 Qt 库，并将 Qt 的动态链接库
（`.dll`、`.pyd`）随分发包一同提供。

**关于替换 Qt 库的说明（LGPLv3 第 4 节）**

本程序采用 PyInstaller 的 one-folder 模式打包，Qt 的动态链接库以独立文件的
形式存放在 `pAnnoGUI/_internal/PySide6/`（或同级目录）下，未经加壳、未静态
链接。使用者可以用自行编译或修改过的、二进制兼容的 Qt 版本替换这些文件，
程序会加载替换后的版本。

Qt 的源代码可从 https://download.qt.io/ 获取。

---

## Python 标准库及运行时

- 项目主页：https://www.python.org
- 版权：Python Software Foundation
- 许可：Python Software Foundation License (PSF-2.0)
- 许可全文：https://docs.python.org/3/license.html

---

## psutil

- 项目主页：https://github.com/giampaolo/psutil
- 版权：Giampaolo Rodola
- 许可：BSD 3-Clause

---

## PyInstaller 引导程序 (bootloader)

- 项目主页：https://pyinstaller.org
- 许可：GPLv2 **附带例外条款**，该例外明确允许用其打包的程序以任意许可
  （包括专有许可）分发。
- 许可全文：https://github.com/pyinstaller/pyinstaller/blob/develop/COPYING.txt

---

如发现遗漏或标注有误，欢迎提 issue 指出。
