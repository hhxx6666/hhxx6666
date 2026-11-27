### hhxx6666

**Hardware test and experiment regression — turning one-off measurements and debugging into tests you can run again.**

把一次性的实验和故障排查，变成可以反复跑的回归测试。

做过硬件或固件的人应该都熟悉这个场景：抓一次示波器波形、复现一次偶发故障、手动升级一次服务，验证完就结束了。下次改动，全部重来一遍。

我写的这几个工具，就是想把这几步变成回归测试。

| 项目 | 做什么 | 从这里开始 |
| --- | --- | --- |
| [RailTrace](https://github.com/hhxx6666/railtrace) | 用示波器或仿真 CSV 做电源上电时序回归，输出带波形与限值的 HTML 报告 | [跑通过与失败的波形样例](https://github.com/hhxx6666/railtrace#try-the-examples) |
| [TraceLab CSV](https://github.com/hhxx6666/tracelab-csv) | 在浏览器按触发事件对齐两次实验，定位超差区间并导出离线报告 | [打开在线工具，载入电机样例](https://hhxx6666.github.io/tracelab-csv/) |
| [FaultReplay Agent](https://github.com/hhxx6666/faultreplay-agent) | 在回放预算内缩减能复现同一断言失败的事件序列，导出 pytest 回归 | [运行离线回放示例](https://github.com/hhxx6666/faultreplay-agent#verify-the-corridor-light-regression) |
| [Upgrade Rehearsal](https://github.com/hhxx6666/upgrade-rehearsal) | 在隔离的 Docker Compose 里验证 Immich 升级路径，按 SHA-256 校验选定原图 | [查看真实 Docker 集成运行](https://github.com/hhxx6666/upgrade-rehearsal/actions/runs/46001628557) |

这四个项目都采用 MIT 协议，并附测试套件与 CI。工具对你的工作有帮助，欢迎给对应仓库点个 Star。如果碰到无法处理的采样或日志格式，也欢迎开 Issue，附上能复现问题的最小样例。

### 另外几个，纯属好玩

- [weiqi-ai](https://github.com/hhxx6666/weiqi-ai) — 浏览器里的围棋 AI，支持胜率估算、教学提示和 SGF 复盘。[在线试玩](https://hhxx6666.github.io/weiqi-ai/)
- [glanceproof](https://github.com/hhxx6666/glanceproof) — 主动视觉工作台：首帧证据不足时让相机换个角度，再把答案挂到支撑它的那一帧上。
- [touch-to-act](https://github.com/hhxx6666/touch-to-act) — 触觉试探实验：三只等重的不透明杯，靠试探判断里面什么在动，并对照不同的试探预算。
- [diana-live-like](https://github.com/hhxx6666/diana-live-like) — 一个 manifest v3 扩展的实践。

<sub>Currently focused on making the four tooling repos above into things an engineer can adopt in five minutes. Issues and corrections are welcome — especially from people who actually run bench measurements.</sub>
