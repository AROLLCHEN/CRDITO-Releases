<div align="center">
  <img src="src/Lcsc2Ad.App/Assets/Crdito.png" width="104" alt="CRDITO Logo">
  <h1>CRDITO</h1>
  <p><strong>连接嘉立创 / LCSC 与 Altium Designer 的器件库工具</strong></p>
  <p>搜索、校验并预览器件，一键导出或直接放置到 Altium Designer。</p>
  <p>
    简体中文 · <a href="README.en.md">English</a> · <a href="README.ja.md">日本語</a>
  </p>
  <p>
    <a href="https://github.com/AROLLCHEN/CRDITO-Releases/releases/latest"><img src="https://img.shields.io/github/v/release/AROLLCHEN/CRDITO-Releases?display_name=tag&style=flat-square&color=0969da" alt="最新版本"></a>
    <a href="https://github.com/AROLLCHEN/CRDITO-Releases/releases"><img src="https://img.shields.io/github/downloads/AROLLCHEN/CRDITO-Releases/total?style=flat-square&color=1f883d" alt="下载量"></a>
    <img src="https://img.shields.io/badge/Windows-10%20%7C%2011-0078d4?style=flat-square" alt="Windows 10/11">
    <img src="https://img.shields.io/badge/Altium-22%20%7C%2026-a35c00?style=flat-square" alt="Altium Designer 22/26">
    <img src="https://img.shields.io/badge/license-Proprietary-555?style=flat-square" alt="专有许可证">
  </p>
  <p>
    <a href="https://github.com/AROLLCHEN/CRDITO-Releases/releases/download/v1.0.9/CRDITO-Setup-1.0.9-win-x64.exe"><strong>下载 CRDITO 1.0.9</strong></a>
    ·
    <a href="https://github.com/AROLLCHEN/CRDITO-Releases/releases/latest">查看发行说明</a>
  </p>
</div>

---

CRDITO 是一款面向电子设计流程的 Windows 桌面工具。它将嘉立创 / LCSC 器件数据转换为经过校验的 Altium Designer 原理图库与 PCB 封装库，并提供原理图、封装和 STEP 3D 模型预览。

## 界面预览

<p align="center">
  <img src="docs/images/online-3d-preview-gpu.png" width="92%" alt="CRDITO 3D 模型预览">
</p>

<table>
  <tr>
    <td width="50%" align="center">
      <img src="docs/images/online-component-details.png" alt="CRDITO 器件参数"><br>
      <sub>器件信息与可复制参数</sub>
    </td>
    <td width="50%" align="center">
      <img src="docs/images/online-footprint-preview.png" alt="CRDITO PCB 封装预览"><br>
      <sub>PCB 封装与实际焊盘预览</sub>
    </td>
  </tr>
</table>

所有界面图片均由当前版本窗口直接捕获，不包含系统鼠标、桌面背景或后期生成的界面元素。

## 常用操作指南

### 1. 搜索并校验器件

1. 在顶部选择数据源，在线器件使用“嘉立创EDA在线模型”。
2. 输入立创编号、MPN、厂商、关键字或封装；需要时启用“有库存”和“有 EDA 模型”筛选。
3. 点击“搜索”并在左侧选择唯一结果。软件会依次显示“加载中”和“校验中”，完成后再开放导出与放置。
4. 在标题区核对制造商型号、封装、描述和数据手册。出现校验错误时不要继续导出，可先刷新或改选正确器件。

### 2. 检查原理图、封装和 3D 模型

- 使用“原理图”“PCB 封装”“3D 模型”“参数”选项卡逐项检查，也可以通过“视图 → 四视图”同时比较。
- 原理图和封装支持滚轮缩放、按住左键拖动画布；3D 模型支持拖动旋转、滚轮缩放以及等轴、顶、底、前、后、左、右视角。
- 通过“视图 → 显示封装尺寸”查看整体尺寸；通过“工具 → 测量长度”点击两个测量点。测量支持边缘、顶点、中心和水平/垂直吸附，按 `Esc` 退出。

### 3. 导出 Altium 库

1. 在“设置 → 导出原理图默认显示”中选择位号、注释、引脚名称和引脚编号。
2. 选择器件后点击底部“导出 AD 库”，再选择输出目录。
3. 等待二进制回读与引脚—焊盘映射校验完成。成功后目录中会包含 `.SchLib`、`.PcbLib`、STEP 和 `.validation.json`。

### 4. 直接放置到 Altium Designer

1. 在 AD 中打开目标工程与原理图文档，并让原理图画布处于可编辑状态。
2. 在 CRDITO 中点击“放置到 AD”。同一时间只会保留一个待放置任务。
3. 切换到 AD，在原理图画布内真实点击一次后开始放置；器件会附着到鼠标并使用工程目录中的统一 SchLib/PcbLib 关联封装。
4. 在“设置 → 按 Esc 时”选择“删除当前器件”或“仅结束放置”，即可控制取消行为。

> 提示：按住 `Ctrl` 点击顶部可配置的菜单项，可以设置快捷键；重复快捷键会在保存前提示冲突。需要连续放置时，可启用“窗口置顶”和“置顶时进入轻量模式”。

## 核心能力

| 能力 | 说明 |
| --- | --- |
| 器件搜索 | 按立创编号、MPN、关键字或封装搜索，并支持滚动加载与本地缓存 |
| 一致性预览 | 使用与最终导出相同的转换规则渲染原理图、PCB 封装和 3D 模型 |
| 原生库导出 | 生成 `.SchLib`、`.PcbLib`、STEP 和机器可读校验报告，无需启动 AD |
| 直接放置 | 从 CRDITO 创建放置任务，在 AD 原理图画布中定位并关联统一封装库 |
| 严格校验 | 检查引脚、焊盘、槽孔、异形焊盘、多单元符号、模型映射和库回读结果 |
| 高效预览 | 支持四视图、平滑缩放、尺寸测量、多视角切换和大型 STEP 网格缓存 |

## 快速开始

1. 从 [Releases](https://github.com/AROLLCHEN/CRDITO-Releases/releases/latest) 下载并安装最新版。
2. 搜索并选择器件，在原理图、PCB 封装和 3D 视图中检查结果。
3. 导出独立库文件，或点击“放置到 AD”进入 Altium Designer 放置流程。

安装包适用于 Windows 10/11 x64，已包含 .NET、NPNP、OCC、VC++ 运行库和 AD 放置扩展。安装时可以自由选择目录，需要管理员权限；Altium Designer 本体及商业授权不包含在安装包中。

> 未安装 Altium Designer 时，搜索、预览和独立导出仍可正常使用。直接放置与 PCB 更新需要兼容的 Altium Designer 环境。

## 输出内容

```text
器件数据
├── Altium 原理图库 (.SchLib)
├── Altium PCB 封装库 (.PcbLib)
├── STEP 3D 模型 (.step)
└── 校验报告 (.validation.json)
```

CRDITO 会在发布库文件前进行独立二进制回读。引脚缺失、编号重复、引脚与焊盘映射不一致或几何结果异常时，导出会被阻止。

## 更多信息

- [版本与发行说明](https://github.com/AROLLCHEN/CRDITO-Releases/releases)
- [问题反馈](https://github.com/AROLLCHEN/CRDITO-Releases/issues)
- [软件许可](LICENSE)
- [第三方组件声明](docs/THIRD-PARTY-NOTICES.md)

## 数据、商标与许可

在线器件数据仅在用户主动查询时获取，不进行后台批量抓取，也不绕过登录或验证码。请遵守嘉立创、LCSC、EasyEDA、Altium Designer 及相关内容权利人的条款。

CRDITO 是独立的互操作工具，与上述公司不存在隶属、赞助或背书关系。CRDITO 为专有软件，版权所有 © 2026 AROLLCHEN。完整条款见 [LICENSE](LICENSE)。源码仓库保持私有，官方安装包和更新元数据仅通过公开的 [CRDITO-Releases](https://github.com/AROLLCHEN/CRDITO-Releases) 仓库分发。

<p align="right"><a href="#crdito">返回顶部</a></p>
