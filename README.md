### hhxx6666

**Hardware test and experiment regression — turning one-off measurements and debugging into tests you can run again.**

把一次性的实验和故障排查，变成可以反复跑的回归测试。

做过硬件或固件的人应该都熟悉这个场景：抓一次示波器波形、复现一次偶发故障、手动升级一次服务，验证完就结束了。下次改动，全部重来一遍。

我写的这几个工具，就是想把这几步变成回归测试。

| 项目 | 环节 | 做什么 |
| --- | --- | --- |
| [railtrace](https://github.com/hhxx6666/railtrace) | 采集 | 用示波器 / 仿真导出的 CSV 做电源上电时序回归，输出带波形与限值的 HTML 报告 |
| [tracelab-csv](https://github.com/hhxx6666/tracelab-csv) | 对齐 | 按同一触发事件对齐两次实验的 CSV，标出超差区间，导出离线报告 |
| [faultreplay-agent](https://github.com/hhxx6666/faultreplay-agent) | 缩减 | 把事件日志缩减到仍能触发同一断言的最小序列，导出 pytest 回归 |
| [upgrade-rehearsal](https://github.com/hhxx6666/upgrade-rehearsal) | 演练 | 在隔离的 Docker Compose 里预演 Immich 升级，按 SHA-256 校验原图 |

都是零依赖或低依赖的命令行工具，MIT 协议，可商用。每个仓库都有测试套件和 CI。

### 另外几个，纯属好玩

- [weiqi-ai](https://github.com/hhxx6666/weiqi-ai) — 浏览器里的围棋 AI，实时胜率曲线 + 教学提示，单文件零依赖。[在线试玩](https://hhxx6666.github.io/weiqi-ai/)
- [glanceproof](https://github.com/hhxx6666/glanceproof) — 主动视觉工作台：首帧证据不足时让相机换个角度，再把答案挂到支撑它的那一帧上。
- [diana-live-like](https://github.com/hhxx6666/diana-live-like) — 一个 manifest v3 扩展的实践。

### 联系

想要某个功能、或者发现了 bug，直接开 issue。

<sub>Currently focused on making the four tooling repos above into things an engineer can adopt in five minutes. Issues and corrections are welcome — especially from people who actually run bench measurements.</sub>
