# 策略驾驶舱 · 只读镜像

主站（canonical）：Qoder Sites 上的私有在线快照站。
本仓库是**兜底通道**：当 Qoder Sites 管理面（openapi.qoder.com.cn）故障、推送与发布全停时，
由本机 `user_data/ops/sync_cockpit_mirror.sh` 把 `site_online/public` 快照推到此处。

- 内容 = 发布时刻的静态快照（页顶 `built` 时间戳即生成时刻）。
- **不含**实时数据接口：页面里的 `/functions/v1/app?action=live|news` 在 GitHub Pages 上会 404，
  此时页面回退到内联兜底快照，显示的是 build 当刻的实况数字，不会自动刷新。
- 主通道健康时每日一提；主通道故障期间降到每 5 分钟一提。
- 全部为 dry-run（模拟盘）数据，非真实资金。
