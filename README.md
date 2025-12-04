# NCEI Go

**NCEI Go** 是一个基于 Web 的纯前端可视化气象数据获取工具。它采用独特的 **Dual-Core（双核）架构**，在地图上交互式展示全球气象站点，并生成直达 NOAA NCEI 官方服务器的 CSV 数据下载链接。

> **核心特性**：纯前端无后端 · 双核索引引擎 · 批量多选 · 官方全尺度支持

## 🌟 主要功能

* **全尺度数据支持**：
    * **Hourly**: GHCN-Hourly (GHCNh) / Synoptic / Airways
    * **Daily**: GHCN-Daily (GHCNd)
    * **Monthly**: GSOM (Global Summary of the Month)
    * **Yearly**: GSOY (Global Summary of the Year)
* **双核数据引擎 (Dual-Core)**：
    * 自动识别并切换底层索引文件（`isd-history.csv` vs `ghcnd-stations.txt`），彻底解决不同时间尺度下站点 ID 不匹配的问题。
* **智能交互**：
    * **批量操作**：支持按住 `Shift` 键在地图上框选区域，一键获取多站点数据。
    * **梦幻光效**：采用 "Deep Space" 深空青蓝主题与呼吸光晕交互。
* **高可用性**：
    * **Auto-Loader**：自动加载同目录下的官方索引文件。
    * **Fallback 机制**：若本地索引文件缺失，自动降级加载内置的全球 Top 50 核心城市数据，确保演示可用。

## 🛠️ 使用方法

1.  **启动**：双击打开 `index.html`（或将其部署至 GitHub Pages/静态服务器）。
2.  **选择模式**：在右侧控制台选择数据类型（**Hourly** / Daily / Monthly / Yearly）。
    * *注意：切换模式会重置地图上的站点分布。*
3.  **选择站点**：
    * **单选**：点击地图上的站点圆点。
    * **多选**：开启“批量多选”开关，或按住 `Shift` 并在地图上拖拽框选。
    * **搜索**：在搜索框输入 City Name (如 `Beijing`) 或 Station ID。
4.  **下载**：设置时间范围，点击底部的 **"下载数据 (CSV)"** 按钮，系统将自动拼接 API 链接并触发下载。

## 📂 数据来源与文件结构

本项目依赖以下 NOAA 官方索引文件（请与 `index.html` 放置在同一目录以获得完整体验）：

* **核心程序**: `index.html` (单文件应用，包含所有逻辑与样式)
* **索引文件 (可选，推荐下载)**:
    * `ghcnd-stations.txt`: 用于 Daily/Monthly/Yearly 模式 (源自 GHCN-Daily)。
    * `isd-history.csv`: 用于 Hourly 模式 (源自 GHCN-Hourly)。

> **注意**：如果不提供上述索引文件，系统将使用内置的 Demo 数据（全球主要核心城市）进行演示。

## ⚠️ 版权与引用说明

* **数据归属**：所有气象数据均直接请求自 [NOAA NCEI](https://www.ncei.noaa.gov/) 官方 API，本项目不进行任何存储或中间处理。
* **引用规范**：若用于学术研究，请根据数据类型引用相应的官方文献：
    * *GHCN-Daily*: Menne et al. 2012
    * *GHCN-Hourly*: Menne et al. 2023
    * *(详细引用格式可在工具内的 "Citation" 侧边栏查看)*
* **免责声明**：本项目仅供学术研究与教育用途 (Educational Purpose Only)。开发者不对数据的准确性及 NOAA 服务的可用性承担责任。