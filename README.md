# IPLC 测评：MkCloud 广港/沪日/沪美三线实测数据、全套餐价格表与选购避坑指南

搜“IPLC 测评”的人，想看的东西其实很固定：延迟到底多少、晚高峰稳不稳、IP 干不干净、多少钱能拿下。这篇文章就把 MkCloud（mkcloud.net）这条线上的 IPLC 套餐拆开讲清楚——三条主流线路的实测数据口径、目前在售的全部套餐价格、优惠码怎么叠加，以及付款前你必须知道的几条限制。

MkCloud 是 2023 年创建的国人商家，主营广港 IEPL、沪港 IPLC、沪日 IPLC、沪美 IPLC 和上云互联（IXP）专线 VPS，所有专线都是“双端独立 IP”套餐：一台机器一个国内入口 IP 加一个海外出口 IP。要注意的是，购买前需要用国内手机号完成实名认证，这一点和普通海外 VPS 完全不同。

## 先说结论：三条线路各自的延迟和适合场景

MkCloud 官网和产品页给出的端内参考延迟如下，这也是选线路的第一依据：

| 线路 | 路径 | 端内延迟 | 典型用途 |
| --- | --- | --- | --- |
| 广港 IEPL | 广州入口 → 香港出口 | 1~2ms | 香港、新加坡方向的电商与通用出海 |
| 沪港 IPLC | 上海入口 → 香港出口 | 21ms | 华东用户接香港，入口离自己近 |
| 沪日 IPLC | 上海入口 → 日本出口 | 25~28ms | 日本电商平台、日区服务 |
| 沪美 IPLC | 上海入口 → 美国出口 | 124~134ms | 美国站、北美业务 |

“端内延迟”指的是从国内入口到海外出口这段专线的延迟，不包含你本地到入口、以及出口到目标网站的时间。所以选线路时，除了看这个数字，还要看你自己在哪个省份——入口是绑定省份的，广港绑定广东方向，沪系绑定上海方向，虽然可以切换，但入口离你越近，全程延迟越低。

## 第三方测评数据怎么说

自己测过的人不多，但网上能找到几份第三方测评，口径基本一致，这里如实转述：

- 广港 IEPL 方向，有测评记录实测下载速度接近 150Mbps、上行同样跑满，超过官方标注的峰值带宽；丢包率基本在 0%~1%，晚高峰没有明显波动。
- IP 纯净度方面，有测评用 scamalytics 检测，欺诈值为 0，属于没有滥用历史的干净 IP，对做 TikTok Shop、eBay 这类怕关联的电商业务比较友好。
- 沪日 IPLC 的 25~28ms 延迟，在访问日本平台时接近本地体验；沪美 IPLC 的 124~134ms 是跨太平洋的物理极限，做美国方向业务属于正常水平，别拿它和美西 CN2 的数字直接比。

需要说明的是，以上数据来自第三方测评文章，不是本站的实测结果，不同批次、不同入口的实际表现会有差异。MkCloud 官方知识库也建议：验收时先用低负载短时测试，再用 iperf3 测吞吐，保存好测试时间和两端信息——真出了质量问题，退款审核要看这些证据。

## 全套餐价格表（流量计费 + 独享带宽 + IXP）

下面是目前官网商店页和知识库能确认的在售套餐。MkCloud 的 IPLC 产品分两种计费：**流量计费**（共享带宽峰值，月流量双向合计，超量暂停）和**独享带宽**（按 Mbps 计费，流量不限，可 24 小时持续跑满）。价格可能随库存和活动调整，下单时以购物车页面为准。

**IPLC / IEPL 流量计费套餐（共享带宽）**

| 套餐 | 配置 | 带宽峰值 | 月流量 | 价格 | 购买链接 |
| --- | --- | --- | --- | --- | --- |
| 广港 IEPL 500GB | 1核2G / 20GB | 150Mbps | 500GB | ¥228/月 | [ 查看广港IEPL套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 广港 IEPL 1TB | 1核2G / 20GB | 200Mbps | 1TB | ¥358/月 | [ 查看广港IEPL套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 广港 IEPL 2TB | 2核4G / 40GB | 300Mbps | 2TB | ¥568/月 | [ 查看广港IEPL套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 广港 IEPL 4TB | 2核4G / 40GB | 300Mbps | 4TB | ¥998/月 | [ 查看广港IEPL套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 广港 IEPL 6TB | 4核8G / 60GB | 500Mbps | 6TB | ¥1388/月 | [ 查看广港IEPL套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 广港 IEPL 10TB | 4核8G / 60GB | 500Mbps | 10TB | ¥2288/月 | [ 查看广港IEPL套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 广港 IEPL 20TB | 4核8G / 60GB | 1Gbps | 20TB | ¥4500/月 | [ 查看广港IEPL套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 沪日 IPLC 500GB | 1核2G / 20GB | 150Mbps | 500GB | ¥228/月 | [ 查看沪日IPLC套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 沪日 IPLC 1TB | 1核2G / 20GB | 200Mbps | 1TB | ¥358/月 | [ 查看沪日IPLC套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 沪日 IPLC 2TB | 2核4G / 40GB | 300Mbps | 2TB | ¥568/月 | [ 查看沪日IPLC套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 沪日 IPLC 4TB | 2核4G / 40GB | 300Mbps | 4TB | ¥998/月 | [ 查看沪日IPLC套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 沪日 IPLC 6TB | 4核8G / 60GB | 500Mbps | 6TB | ¥1388/月 | [ 查看沪日IPLC套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 沪日 IPLC 10TB | 4核8G / 60GB | 500Mbps | 10TB | ¥2288/月 | [ 查看沪日IPLC套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 沪日 IPLC 20TB | 4核8G / 60GB | 1Gbps | 20TB | ¥4500/月 | [ 查看沪日IPLC套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 沪美 IPLC 100GB | 1核2G / 20GB | 150Mbps | 100GB | ¥198/月 | [ 查看沪美IPLC套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 沪美 IPLC 500GB | 1核2G / 20GB | 150Mbps | 500GB | ¥258/月 | [ 查看沪美IPLC套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 沪美 IPLC 1TB | 1核2G / 20GB | 200Mbps | 1TB | ¥428/月 | [ 查看沪美IPLC套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 沪美 IPLC 2TB | 2核4G / 40GB | 300Mbps | 2TB | ¥698/月 | [ 查看沪美IPLC套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 沪美 IPLC 4TB | 2核4G / 40GB | 300Mbps | 4TB | ¥1258/月 | [ 查看沪美IPLC套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 沪美 IPLC 6TB | 4核8G / 60GB | 500Mbps | 6TB | ¥1758/月 | [ 查看沪美IPLC套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 沪美 IPLC 10TB | 4核8G / 60GB | 500Mbps | 10TB | ¥2888/月 | [ 查看沪美IPLC套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 沪港 IPLC（共享入门） | 1核2G / 20GB | 200Mbps | 1024GB | ¥288/月 | [ 查看沪港IPLC套餐](https://bit.ly/MKCLoud) |

**独享带宽套餐（流量不限，可 24 小时持续跑满）**

| 线路 | 档位 | 配置 | 价格 | 购买链接 |
| --- | --- | --- | --- | --- |
| 沪港 IPLC | 5M 独享 | 2核4G / 40GB | ¥650/月 | [ 查看沪港独享套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-ex) |
| 沪港 IPLC | 10M 独享 | 2核4G / 40GB | ¥950/月 | [ 查看沪港独享套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-ex) |
| 沪港 IPLC | 20M 独享 | 2核4G / 40GB | ¥1760/月 | [ 查看沪港独享套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-ex) |
| 沪日 IPLC | 5M 独享 | 2核4G / 40GB | ¥600/月 | [ 查看沪日独享套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fshh-jp-ex) |
| 沪日 IPLC | 10M 独享 | 2核4G / 40GB | ¥800/月 | [ 查看沪日独享套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fshh-jp-ex) |
| 沪日 IPLC | 20M 独享 | 2核4G / 40GB | ¥1560/月 | [ 查看沪日独享套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fshh-jp-ex) |
| 沪日 IPLC | 50M 独享 | 4核8G / 60GB | ¥3500/月 | [ 查看沪日独享套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fshh-jp-ex) |
| 沪日 IPLC | 100M 独享 | 4核8G / 60GB | ¥6000/月 | [ 查看沪日独享套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fshh-jp-ex) |
| 沪美 IPLC | 5M 独享 | 2核4G / 40GB | ¥800/月 | [ 查看沪美独享套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fshh-us-ex) |
| 沪美 IPLC | 10M 独享 | 2核4G / 40GB | ¥1100/月 | [ 查看沪美独享套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fshh-us-ex) |
| 沪美 IPLC | 20M 独享 | 2核4G / 40GB | ¥2100/月 | [ 查看沪美独享套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fshh-us-ex) |
| 沪美 IPLC | 50M 独享 | 4核8G / 60GB | ¥5000/月 | [ 查看沪美独享套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fshh-us-ex) |
| 沪美 IPLC | 100M 独享 | 4核8G / 60GB | ¥9000/月 | [ 查看沪美独享套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fshh-us-ex) |

**上云互联 IXP 套餐（同线路里的低价位选项）**

| 线路 | 档位 | 配置 | 价格 | 购买链接 |
| --- | --- | --- | --- | --- |
| 沪日上云 BGP | 1TB | 2核4G / 200Mbps | ¥166/月 | [ 查看上云互联套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 沪日上云 BGP | 2TB | 2核4G / 300Mbps | ¥268/月 | [ 查看上云互联套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 沪日上云 BGP | 6TB | 4核8G / 1Gbps | ¥688/月 | [ 查看上云互联套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 沪美上云 BGP | 1TB | 2核4G / 200Mbps | ¥266/月 | [ 查看沪美上云套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-us-sh) |
| 沪美上云 BGP | 2TB | 2核4G / 200Mbps | ¥430/月 | [ 查看沪美上云套餐](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-us-sh) |
| 深港 IX（共享入门） | — | — | ¥158/月起 | [ 查看IXP全线套餐](https://bit.ly/MKCLoud) |

除了表里的标准档位，三条 IPLC 线路都支持独享带宽定制，独享档位覆盖 5M 到 5G，所有配置可以按需求定制，量大可议价。另外官网还有上海 CN2（¥4500/月起）和厦港/泉港高防这类企业向产品，篇幅原因不展开，需要的话进商店页能看到。

## 优惠码：能省多少，怎么叠

MkCloud 的活动比较频繁，常见的几类优惠码如下，多数要求在活动期内使用，下单前在购物车试一下最稳妥：

| 优惠码 | 适用范围 | 力度 |
| --- | --- | --- |
| MK-8.8 | 流量计费产品 | 循环 8.8 折 |
| MK-7.8 | 独享带宽产品 | 首月 7.8 折 |
| MK-IEPL-WELCOME | IEPL 线路 | 9 折 |
| MK-IPLC-WELCOME | IPLC 线路 | 9 折 |
| MK-NEW | 新客专享活动机（2核4G / 268Mbps / 666GB） | 236 元/月 |
| CLOUD-2T-NEW | 沪日上云 2TB 套餐 | 折后 126 元/月 |

举个实际的例子：沪日 IPLC 1TB 原价 ¥358/月，用 MK-8.8 循环 8.8 折后约 ¥315/月；如果是第一次买 IPLC，先试 MK-IPLC-WELCOME 的 9 折对比一下哪个更低。深港 IX 的 2TB 档用 CLOUD-2T-NEW 能到 126 元/月，是整个产品线里单位流量最便宜的档位之一。活动码随时可能过期，最终以结账页显示的优惠金额为准。

## 按场景选套餐，不按“最便宜”选

- **跨境电商店铺（TikTok Shop / eBay / Shopee）**：广港 IEPL 1TB（¥358）是性价比最均衡的一档，1~2ms 端内延迟加独立出口 IP，应付店铺运营和防关联足够；预算紧就选 500GB（¥228），流量是上行加下行双向合计，注意别按下载量估。
- **日本方向业务（日区电商、日服运维）**：沪日 IPLC 1TB（¥358）或 2TB（¥568）。要持续大带宽的话，沪日独享 10M（¥800/月，流量不限）比流量计费更适合跑长期任务。
- **美国站 / 北美业务**：先拿沪美 IPLC 100GB（¥198）试线路效果，确认目标平台访问正常再加到 500GB 或 1TB；预算敏感的话，沪美上云 1TB（¥266）便宜三成，代价是走互联网交换路径而非全程专线。
- **直播推流、数据库同步这类持续大流量**：直接看独享带宽档，共享款带宽是峰值、不保证持续跑满，官方文档里写得很明确。

## 付款前必须知道的几条规则

这些限制都来自官方购物车页面和知识库，属于容易踩坑的部分，买前过一遍：

> 计量型套餐按上行、下行双向统计流量，超量后会暂停服务，可自助购买流量重置或提交工单补差价升级；共享带宽为峰值带宽，不保证持续跑满。

> 仅支持质量问题退款，需要在工单中提交测试截图和问题信息（如具体延迟、速度数据），由官方审核判断，不是无条件试用；服务开通后不支持更换到其他地域的产品。

其他几条同样值得记住：目前只支持支付宝付款；出口 IP 不支持外部连入，所以这套机器适合做出站业务（店铺运营、API 调用、采集、跨境办公），不适合拿来建面向公众的网站或做支付回调；平台明确禁止机场、回国专线等违规用途，违规会被停服且不退款。标准套餐默认没有 SLA 承诺，对企业级可用性要求的话，先走工单确认。

升降级都要通过工单操作，而且降级到更低价格的套餐时差价不退，所以首单尽量按实际用量选档，宁可先小后大。

## 常见问题

**IPLC 和 IEPL 有什么区别？** 广义上 IEPL 是以太网专线、IPLC 是传统点对点专线，但在 MkCloud 这类专线 VPS 产品语境里，两者差异主要体现在路径和入口位置：广港 IEPL 是广州入口接香港，沪港/沪日/沪美是上海入口。选型时看延迟和入口位置就行，不用纠结名称。

**个人能买吗？** 能，但需要国内手机号实名认证。个人用户要提供手机号、姓名和身份证号，企业用户提交营业执照信息和对公账户。

**IP 会被平台判定为风险 IP 吗？** 第三方测评显示其 IPv4 在 scamalytics 的欺诈值为 0，属于较干净的住宅/机房混合口碑。但 IP 信誉是动态的，任何服务商都无法保证某个平台永远不风控，敏感业务建议先小额套餐验证。

**流量用超了会怎样？** 计量型套餐超量后暂停（不是扣费），可以自助购买流量重置，或者补差价升级套餐。部分 IXP 活动产品历史上是超量限速不停机，但那属于活动期规则，现售以购物车说明为准。

**和普通海外 VPS 比，贵出来的钱买的是什么？** 买的是跨境段的路由质量：普通 VPS 从国内访问要过公网，晚高峰丢包和限速躲不掉；IPLC/IEPL 的国内入口到海外出口走的是专线内网，这段不受公网拥堵影响。25ms 稳定到日本、1~2ms 稳定到香港，这是同价位的普通 VPS 给不了的。

如果你已经想清楚方向，最省事的路径是：先确定目标市场对应的线路 → 选流量档或独享档 → 结账时把 MK-8.8 和对应的 WELCOME 码都试一遍 → 首月小额验证延迟和丢包，再决定要不要长期投入。 [👉 进入 MkCloud 商店查看全部在售套餐](https://bit.ly/MKCLoud)
