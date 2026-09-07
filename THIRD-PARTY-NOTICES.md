# Third-Party Notices

CantoFlow (derived from [SuperSec](https://github.com/Garionhk/SuperSec)) is
licensed under the **Apache License 2.0** (see [LICENSE](LICENSE)).
It bundles or depends on the third-party components listed below. Each remains
under its own license, and those licenses govern the corresponding components.

Versions listed reflect a representative build; check `requirements.txt` and
your environment for the exact versions you ship.

---

## Runtime dependencies (bundled in distributed binaries)

| Component | Version | License | Project |
|---|---|---|---|
| PySide6 (Qt for Python) | 6.11.1 | **LGPL-3.0-only** (or GPL-2.0 / GPL-3.0) | https://wiki.qt.io/Qt_for_Python |
| shiboken6 | 6.11.1 | **LGPL-3.0-only** (or GPL-2.0 / GPL-3.0) | https://wiki.qt.io/Qt_for_Python |
| pynput | 1.8.2 | **LGPL-3.0** | https://github.com/moses-palmer/pynput |
| sounddevice | 0.5.5 | MIT | https://github.com/spatialaudio/python-sounddevice |
| PortAudio (via sounddevice) | — | MIT-style | https://www.portaudio.com/ |
| NumPy | 2.5.1 | BSD-3-Clause | https://numpy.org/ |
| Requests | 2.34.2 | Apache-2.0 | https://requests.readthedocs.io/ |
| opencc-python-reimplemented | 0.1.7 | Apache-2.0 | https://github.com/yichen0831/opencc-python |
| cffi (via sounddevice) | 2.1.0 | MIT | https://cffi.readthedocs.io/ |

## Build-time only (not redistributed inside the application)

| Component | Version | License | Notes |
|---|---|---|---|
| PyInstaller | 6.21.0 | GPL-2.0-or-later **with bootloader exception** | The exception explicitly permits distributing bundled applications under any license. |
| Pillow | 12.3.0 | MIT-CMU (HPND) | Used only by `build_icons.py` to generate the icon pack. |

## Downloaded at first run (not redistributed with the application)

These are fetched by the user's own installation into
`%LOCALAPPDATA%\SuperSec\` (Windows) or `~/.local/share/SuperSec/` (Linux).
They are **not** included in the SuperSec source tree or its binaries.

| Component | License | Source |
|---|---|---|
| llama.cpp (`llama-server` + `libggml`/`libllama` libraries) | MIT | https://github.com/ggml-org/llama.cpp |
| Qwen3-ASR model weights (GGUF, incl. `mmproj` audio encoder) | Apache-2.0 | https://huggingface.co/ggml-org/Qwen3-ASR-0.6B-GGUF |

Model weights are subject to the terms published on their model card; verify
those terms before redistributing the weights themselves.

---

## LGPL compliance note (PySide6 / Qt and pynput)

SuperSec links against **PySide6/Qt** and **pynput**, which are licensed under
the **LGPL-3.0**. When distributing a bundled binary (the single-file
`SuperSec.exe`, an AppImage, or similar), the LGPL requires that recipients be
able to replace those libraries with modified versions and relink the
application.

This project satisfies that by:

1. Distributing the **complete application source** under Apache-2.0, so any
   user can rebuild the application against their own build of Qt/PySide6 or
   pynput (see the Packaging section of the README).
2. Providing this notice, which identifies the LGPL components, their versions,
   and where to obtain their source.

The LGPL-3.0 text is available at https://www.gnu.org/licenses/lgpl-3.0.html.
Qt/PySide6 sources: https://download.qt.io/official_releases/QtForPython/ —
pynput sources: https://github.com/moses-palmer/pynput.

No modifications have been made to any of the above components; they are used
as published.
