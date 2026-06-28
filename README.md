# 蜜学热榜 - 全球 AI 科技热点聚合站

> 一个页面看完 12 个平台的实时热点。零成本，永久在线。

**在线体验：[mixuecoding.github.io/mihoc-hot](https://mixuecoding.github.io/mihoc-hot/)**

---

## 扫码关注公众号

<div align="center">
  <img src="mixuecodingQR.jpg" width="160" alt="蜜学编程公众号">
  <p>👆 微信扫码关注「蜜学编程」</p>
  <p>氛围编程实战派。像喝蜜雪一样写代码。</p>
</div>

---

## 覆盖平台

| 类型 | 平台 |
|------|------|
| 🌍 全球 | Hacker News、GitHub Trending、Stack Overflow、Google Trends、Wikipedia、Bluesky、Dev.to、Lobste.rs |
| 📦 开发 | npm、PyPI、Docker Hub |
| 💬 微信 | 微信 24h 热文榜（公众号爆款文章） |
| 🪙 其他 | CoinGecko 加密货币趋势 |

## 技术栈

- **数据采集**: trend-pulse (37 源) + Scrapling (微信热文)
- **自动翻译**: Google Translate API (英文标题 → 中文)
- **定时更新**: GitHub Actions 每小时自动抓取
- **托管部署**: GitHub Pages (免费)

## 自己也搭一套

```bash
git clone https://github.com/mixuecoding/mihoc-hot.git
cd mihoc-hot
python -m http.server 8080
# 打开 http://localhost:8080
```

要部署到公网，直接推到自己的 GitHub 仓库，在 Settings → Pages 中启用即可。

## 自定义数据源

编辑 `.github/workflows/collect.yml`，修改 `GLOBAL` 数组：

```python
GLOBAL = [
    'hackernews', 'github', 'stackoverflow',
    'google_trends', 'reddit',  # 加 Reddit（需代理）
    ...
]
```

完整可用源列表运行 `python -c "from trend_pulse.aggregator import TrendAggregator; print([s['name'] for s in TrendAggregator().list_sources()])"` 查看。
