# NCEI Go

NCEI Go 是一个纯前端小工具，用来在地图上选择全球气象站，并生成直达 NOAA/NCEI GHCND 日数据（CSV）的下载链接。

## 使用方法

1. 打开 `index.html`（或部署到 GitHub Pages 后访问对应网址）。  
2. 在地图上点击站点标记，或在顶部搜索框输入英文城市名并选择结果。  
3. 在右侧面板设置起始日期和结束日期，点击“生成数据下载链接”。  
4. 点击出现的绿色按钮，从 NCEI 官方服务器下载 CSV 文件。

## 数据来源

- 站点数据：`stations_core.json`（由 GHCN-Daily 官方站点列表整理而来）。  
- 气象数据：NOAA/NCEI Global Historical Climatology Network – Daily (GHCN-Daily)，
  通过 NCEI Access Data Service API 获取。

## 说明

- 本项目仅为数据导航界面，不对原始数据做任何修改或存储。  
- 若用于科研，请在论文/报告中按 NOAA/NCEI 要求引用 GHCN-Daily 数据集。
