# TRX 策略收益看板

纯静态 TRX 质押策略收益看板，暗色主题，使用 Chart.js 4.x 渲染图表。

## 功能

- **今日概览** — stat-card 显示今日总收益、年化收益率、累计收益、运行天数
- **收益趋势** — 折线图，每日总收益走势
- **收益构成** — 堆叠柱状图，分解能量授权 / 投票奖励 / 费率盈亏
- **费率盈亏** — 正负双色柱状图
- **周度/月度汇总** — 按周、月聚合的收益统计 + 柱状图
- **年化收益率** — 折线图 + 均值参考线

## 技术栈

- 纯静态 HTML + JS，无后端
- Chart.js 4.x (CDN)
- 响应式布局，移动端友好
- 暗色主题 (#0d1117)

## 部署

### GitHub Pages

1. 推送到 `main` 分支
2. 仓库 Settings → Pages → Source: Deploy from a branch → `main` / `/ (root)`
3. 访问 `https://zw-xlx.github.io/trx-dashboard/`

### 本地预览

```bash
cd trx-dashboard
python3 -m http.server 8080
# 访问 http://localhost:8080
```

## 数据更新

编辑 `index.html` 中的 `RAW_DATA` 数组，添加新的每日数据即可。

格式：
```js
{ date:"2026-04-09", energy:830, vote:134, rate:-100, total:864, apy:21.5 }
```

## 颜色方案

| 用途 | 颜色 |
|------|------|
| 收益/正值 | `#3fb950` (绿) |
| 亏损/负值 | `#f85149` (红) |
| 中性/主色 | `#58a6ff` (蓝) |
| 警告 | `#d29922` (橙) |
| 背景 | `#0d1117` |
| 卡片背景 | `#161b22` |
