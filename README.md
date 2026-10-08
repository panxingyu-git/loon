# loon-config

自用的 Loon 完整配置。策略组和分流规则对照自用的 Clash（Mihomo）配置生成，两边保持一致。

## 使用

1. Loon「配置 → 从 URL 下载」，填本仓库 `Loon.lcf` 的 raw 地址。
2. 在「配置 → 订阅节点」添加自己的节点订阅。本仓库不含订阅地址和任何密钥。
3. 两个链式家宽节点（Clash 里的 `dialer-proxy`）已写在 `[Proxy Chain]` 里，先经「🇺🇸 美国中转」再到落地节点。
4. 需要 MITM 的插件，自行生成并信任证书。

## 内容

- 30 个策略组，地区组用节点名正则筛选（`[Remote Filter]`）。
- 43 个订阅规则集，来自 [MetaCubeX/meta-rules-dat](https://github.com/MetaCubeX/meta-rules-dat) 的 `classical/*.list`。
- 本地规则：家庭网段、私网、`GEOIP,CN`，以及 Cloudflare / Google / Telegram 的 `IP-ASN`。
- `192.168.50.0/24` 不在 `skip-proxy` / `bypass-tun` 里，由规则交给「🏚️ 内网节点」。

## 来源与许可

`[General]` 和 `[Plugin]` 取自[可莉的 Loon 进阶配置模板](https://github.com/luestr/ProxyResource)并有改动，按其 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) 许可使用；本仓库以相同许可发布。
