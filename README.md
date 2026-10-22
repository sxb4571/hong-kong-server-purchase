# 香港服务器怎么购买：从选线路、挑配置到付款开通的完整流程，附全系套餐价格与下单避坑清单

买香港服务器的动作本身很简单：定需求、挑套餐、选计费周期、付款，然后等系统开通。真正让人吃亏的是中间几个细节，比如优惠码填在哪一页、年付到底便宜多少、到期有没有宽限期、流量超了是限速还是直接停机。这几个问题在服务商的销售页上通常不会写得很显眼。

下面按实际下单顺序走一遍，用 GoMami 的后台作为例子（它走的是标准 WHMCS 流程，多数香港服务商的操作路径也差不多），顺带把它家当前在售的套餐和价格整理清楚。

> **选购速览**：面向中国大陆用户建站或跑应用，GoMami 香港 Pulse.Mini（2 核 / 4GB / 60GB NVMe / 1TB 流量 / 1Gbps）是多数人的起点，第三方库存站 2026 年 8 月抓取价 $59/月；对单核性能有硬需求就上 Turin.Mini（Ryzen 9 9950X，$69/月）；只想先测线路，Pulse.Nano $49/月 够用。👉 [查看 GoMami 香港 Pulse 系列当前套餐](https://gomami.io/aff.php?aff=415&pid=4)

## 买香港服务器之前，先定三件事

香港服务器的实际体验九成由线路决定，配置和流量额度排在后面，价格反而是最后才该看的东西。同一台 2 核 4G 的机器，走优化回程和走国际线路，晚八点的表现可以差出一倍以上。

**线路**。香港机房到大陆有三家运营商的回程问题，市面上常见的优化方案是电信 CN2、联通 CUAS9929、移动 CMCMIN2 这几条。GoMami 官方文档写的是电信 / 联通 / 移动三网优化，第三方库存站标注的具体回程为 CN2 + CUAS9929 + CMCMIN2。厂商自己在首页宣称中国大陆全境 RTT 低于 50ms、DDoS 清洗能力最高 600 Gbps，这两个数字目前只有官方口径，没有第三方实测支撑，当参考值看就行。

需要警惕的是另一类情况：不少标着“香港节点”的机器实际路由绕道美国，白天测速漂亮，晚高峰延迟直接冲到 200ms 以上。这类问题在低价方案里尤其常见。

**配置**。跑 WordPress、小型 API、代理节点，2 核 4G 是够用的门槛。要跑 Windows 远程桌面或游戏服，先看套餐页有没有标 “Windows-ready”，GoMami 这边是 Pro 和 Ultra 档才标。数据库、编译、转码这类吃单核的活，机型代次比核心数更重要。

**流量与超额规则**。香港带宽成本高，所以几乎都按流量计费。买之前一定要确认两件事：流量按出站算还是双向算，超额之后是限速还是停机。这两个条件直接决定这台机器能不能长期扛住突发流量。

## GoMami 全系套餐与价格

GoMami 官网当前在售三条产品线，香港、日本、新加坡三个节点，可下单的 VPS 套餐共 19 个，另有 2 个香港独服套餐。要注意 store 页本身不显示价格，官网首页的价格卡又和 store 页的磁盘容量对不上，所以下表的价格取自第三方库存站 2026 年 8 月 21 日的抓取记录，配置取自官网 store 页。下单时以结算页显示的金额为准。

官方文档确认的节点只有三个：香港、日本东京、新加坡。产品线分三条：Turin 是 Ryzen 9 9950X 的性能线（仅香港），Pulse 是均衡线（三地都有，香港节点为 EPYC 7763），Forge 是香港的独立服务器。

### 香港 VPS（Turin / Pulse）

| 套餐 | vCPU / 内存 / NVMe | 流量 · 端口 | 月付 | 购买 |
| --- | --- | --- | --- | --- |
| HKG.Turin.Mini | 2 / 4GB / 100GB | 1TB · 2Gbps | $69 | [选购](https://gomami.io/aff.php?aff=415&pid=14) |
| HKG.Turin.Air | 4 / 8GB / 140GB | 2TB · 2Gbps | $129 | [选购](https://gomami.io/aff.php?aff=415&pid=15) |
| HKG.Turin.Pro | 6 / 16GB / 180GB | 5TB · 5Gbps | $299 | [选购](https://gomami.io/aff.php?aff=415&pid=16) |
| HKG.Turin.Ultra | 12 / 32GB / 220GB | 10TB · 5Gbps | $599 | [选购](https://gomami.io/aff.php?aff=415&pid=22) |
| HKG.Pulse.Nano | 2 / 2GB / 40GB | 500GB · 1Gbps | $49 | [选购](https://gomami.io/aff.php?aff=415&pid=26) |
| HKG.Pulse.Mini | 2 / 4GB / 60GB | 1TB · 1Gbps | $59 | [选购](https://gomami.io/aff.php?aff=415&pid=4) |
| HKG.Pulse.Air | 4 / 8GB / 80GB | 2TB · 1Gbps | $119 | [选购](https://gomami.io/aff.php?aff=415&pid=5) |
| HKG.Pulse.Pro | 8 / 16GB / 100GB | 5TB · 3Gbps | $269 | [选购](https://gomami.io/aff.php?aff=415&pid=6) |
| HKG.Pulse.Ultra | 12 / 32GB / 300GB | 10TB · 3Gbps | $499 | [选购](https://gomami.io/aff.php?aff=415&pid=25) |

**Peak X5 系列**：官网另有一个独立页面，机型也是 Ryzen 9 9950X，三档配置分别是 Mini（2 核 / 4GB / 40GB / 1TB · 2Gbps）、Air（4 核 / 8GB / 60GB / 2TB · 2Gbps）、Pro（6 核 / 16GB / 80GB / 5TB · 5Gbps，标 Windows-ready）。它不在官方产品线的介绍表里，页面上也不标价。第三方测评里出现过 $59 和 $69 两种说法，无法确认哪个是当前价格，所以没放进上面的价格表。👉 [可以去 Peak X5 页面确认当前标价](https://gomami.io/aff.php?aff=415&url=https%3A%2F%2Fgomami.io%2Fstore%2Fhkg-peak)

### 日本 / 新加坡 Pulse

| 套餐 | vCPU / 内存 / NVMe | 流量 · 端口 | 月付 | 购买 |
| --- | --- | --- | --- | --- |
| JPN.Pulse.Nano | 2 / 2GB / 40GB | 500GB · 1Gbps | $29 | [选购](https://gomami.io/aff.php?aff=415&pid=13) |
| JPN.Pulse.Mini | 2 / 4GB / 60GB | 1TB · 1.5Gbps | $49 | [选购](https://gomami.io/aff.php?aff=415&pid=10) |
| JPN.Pulse.Air | 4 / 8GB / 80GB | 2TB · 1Gbps | $89 | [选购](https://gomami.io/aff.php?aff=415&pid=11) |
| JPN.Pulse.Pro | 8 / 16GB / 100GB | 5TB · 3Gbps | $169 | [选购](https://gomami.io/aff.php?aff=415&pid=12) |
| JPN.Pulse.Ultra | 12 / 32GB / 300GB | 10TB · 3Gbps | $338 | [选购](https://gomami.io/aff.php?aff=415&pid=24) |
| SIN.Pulse.Nano | 2 / 2GB / 40GB | 500GB · 1Gbps | $29 | [选购](https://gomami.io/aff.php?aff=415&pid=21) |
| SIN.Pulse.Mini | 2 / 4GB / 60GB | 1TB · 1Gbps | $49 | [选购](https://gomami.io/aff.php?aff=415&pid=17) |
| SIN.Pulse.Air | 4 / 8GB / 80GB | 2TB · 1Gbps | $89 | [选购](https://gomami.io/aff.php?aff=415&pid=18) |
| SIN.Pulse.Pro | 8 / 16GB / 100GB | 5TB · 3Gbps | $169 | [选购](https://gomami.io/aff.php?aff=415&pid=19) |
| SIN.Pulse.Ultra | 12 / 32GB / 300GB | 10TB · 3Gbps | $338 | [选购](https://gomami.io/aff.php?aff=415&pid=23) |

日本和新加坡的 Pulse 配置几乎完全一致，唯一差别是 Mini 档的端口：日本 1.5Gbps，新加坡 1Gbps。价格相同。

### 香港独立服务器 Forge

| 套餐 | 硬件 | 内存 / 存储 | 流量 | 月付 | 购买 |
| --- | --- | --- | --- | --- | --- |
| HKG.Forge.Mini | EPYC 7663 56C/112T，TYAN B8033 | 128GB / 960GB NVMe | 10TB | $599 | [选购](https://gomami.io/aff.php?aff=415&url=https%3A%2F%2Fgomami.io%2Fstore%2Fhkg-forge) |
| HKG.Forge.Air | EPYC 7663 56C/112T，TYAN B8033 | 256GB / 4TB NVMe | 20TB | $899 | [选购](https://gomami.io/aff.php?aff=415&url=https%3A%2F%2Fgomami.io%2Fstore%2Fhkg-forge) |

两个 Forge 套餐都是 2G 端口，超额流量按 $0.06/GB 计费，额外 IP 每个 $10、每台最多 4 个，付款后即时开通，控制面板里随时可以重装系统。

## 香港服务器怎么购买：六步走完下单流程

GoMami 的下单流程一共六步。其中优惠码那一步的位置和大多数人的直觉不太一样，它不在结账页，而在购物车页。

1. **登录后台，在左侧边栏选机房和产品线**。选 HONG KONG 会看到 HKG Turin、HKG Pulse、HKG Forge 三条线；选 JAPAN 只有 JPN Pulse；SINGAPORE 只有 SIN Pulse。点中某个系列之后，右侧才会列出该系列的全部套餐。
2. **在套餐卡片上点 Order Now**，进入 Configure 页。这一页会列出该套餐的完整规格，同时在右侧 Order Summary 实时显示费用拆解。
3. **在 Configure 页选计费周期**。可选月付、季付、半年付、年付，周期越长单价越低。选完点 Continue 加入购物车。
4. **在 Review & Checkout 购物车页填优惠码**。页面上有 Promo Code 输入框，填进去点应用，价格会当场重算。不少人会跳过这一步，直接点 Checkout 到结账页再找输入框，然后找不到。
5. **在 Checkout 页选支付方式**。支持信用卡（Stripe，Visa / Mastercard 等）、Stripe Alipay（支持人民币付款）、加密货币（USDT 等）。账户里如果预先充了余额，可以勾选 “Apply credit balance to this order” 直接抵扣。
6. **勾选 “I have read and agree to the Terms of Service”，点 Complete Order**。提交之后系统开始自动部署。

另外两个下单时可能会用到的操作：需要发票的话走工单，提交公司名、税号、发票金额和联系方式；支付失败时按顺序排查，先看账户余额够不够，再看信用卡有没有开国际交易，然后看浏览器有没有拦支付弹窗，最后换一种支付方式再试。

## 付款之后：1–5 分钟开通，第一件事是装系统

付款成功后系统自动部署，通常在 1 到 5 分钟内完成，IP 地址和登录凭据会发到注册邮箱。开通之后第一件事是进面板挂载 ISO 装系统。

可选模板覆盖 Ubuntu 22.04 / 24.04 LTS、Debian 11 / 12、CentOS Stream 9、AlmaLinux 8 / 9、Windows Server 2019 / 2022。想装列表外的系统，用 Custom ISO 自己挂载安装。

除了重装系统，面板里还有几项可以自助完成的操作：换公网 IP 不用开工单，流量快用完时可以直接买流量包而不必升级套餐，不再需要某台实例时可以把它转移给其他用户。需要程序化管理的话，GoMami 提供 RESTful API，账户和服务器都能通过接口操作。有问题走工单系统或发邮件到 support@gomami.io。

从选址角度看，官方给的节点建议挺实在：面向华南用户选香港，物理距离最近；面向华北用户日本和香港都行，联通的回程优化不错；面向整个中国大陆还是香港综合延迟最好；做东南亚业务选新加坡；游戏加速选香港。👉 [如果只是先跑个测试环境，JPN.Pulse.Mini 月付 $49 起步](https://gomami.io/aff.php?aff=415&pid=10)

## 下单前必须看清的五条规则

这五条都写在官方文档和 FAQ 里，每一条都会实际影响你怎么用这台机器，但销售页面上不会主动提。

**1. 到期没有宽限期。** 到期日当天服务器就暂停，数据保留但服务停掉；逾期 5 天终止，数据可能无法恢复。系统会在到期前 7 天生成续费账单并发邮件，提前充值余额可以自动扣款。这条对长期跑业务的机器很关键，别指望“晚两天再续”。

**2. 退款和取消是两回事。** 退款是「不想要了要拿回钱」，走 Billing 工单，开通后 24 小时内全额退，仅限首次购买、每位用户一次，续费订单不适用；到账时间支付宝 1–3 个工作日、信用卡 5–10 个工作日、加密货币 1–3 个工作日，批准后实例和数据立即删除。取消是「不续费但本周期用完」，在后台 Services > My Services 里自己点 Request Cancellation 就行，不用开工单。

不予退款的情形包括超过 24 小时的订单、因违反服务条款被终止的服务、续费订单、已使用的充值余额，以及因 DDoS 攻击导致 IP 被牵引的情况。

**3. 流量超额是限速，不是停机。** 超出月度额度后带宽会被限速，具体策略依套餐规格而定，额度按计费周期重置。流量不够可以单独买流量包，不用为了加流量去升级套餐。不过官方没公布具体的限速数值。

**4. 长期满载 CPU 会被罚。** 官方 FAQ 明确写了：如果实例被判定为 “noisy neighbor”，也就是持续高负载影响到同节点其他用户，会遭到 CPU 性能限速。这条对挖矿、长期编译、渲染这类场景是硬约束，官方不保证可以长期跑满。

**5. 升降配要开工单。** 面板里不能自助改套餐，得联系客服处理。

## 优惠码怎么用，年付到底省多少

年付比月付省 15%–20%，这是官方文档的口径，具体折扣因产品线而异。长期项目直接上年付是合理的，短期试水就先月付。

优惠码单独说。第三方优惠码站标注 `GOMAMI365` 为全产品年付循环 8 折，有效期到 **2026 年 12 月 31 日**。这个码出现在多个第三方来源，但官方页面上没有公开说明，也没说明它能否在年付价的基础上再打一次折。所以别把两个折扣叠着算，年付本身省的那 15%–20% 是官方明确的，优惠码能不能再省一部分，要以下单时购物车页重算出来的数字为准。优惠码通常是循环折扣，即每个续费周期都按折后价，但不能叠加使用。

算笔账，只算官方明确的年付折扣：香港 Pulse.Mini 月付 $59，一年 $708；按 15%–20% 的年付折扣，一年大约落在 $566 到 $602 之间。如果优惠码还能用上，实际数字会更低，但那部分不属于官方口径。

如果你打算长期用，比较稳的做法是先月付开一台跑两周，确认晚高峰线路表现符合预期，再联系客服确认能否把计费周期改为年付。👉 [先开一台 HKG.Pulse.Nano（$49/月）把线路跑一遍](https://gomami.io/aff.php?aff=415&pid=26)

## 几个买之前最常问的问题

**香港服务器需要备案吗？**
香港机房不涉及中国大陆的 ICP 备案，这是选香港而不是内地机房的常见原因。至于服务商自己要不要实名或 KYC，GoMami 的文档里没有提到这一点，下单前看一眼条款更稳。

**能装 Windows 吗？**
Pro 和 Ultra 档标了 Windows-ready，Mini 和 Air 没有标。Windows 授权是否包含在套餐价格里，官方资料里没有说明，需要问客服确认。

**流量用完了会被停机吗？**
不会停机，是限速。额度按计费周期重置，不够可以单独购买流量包。

**可以先试用吗？**
资料里没有免费试用的明确说明。能依赖的兜底机制是 24 小时全额退款，仅限首次购买且每人一次，用它来实测线路是可行的。

**续费价格和首单价格一样吗？**
官方页面没有标首年特价这类结构，续费按标价计算；如果下单时用了循环优惠码，后续每个续费周期都按折后价走。

## 该怎么选：按你的情况对号入座

预算敏感、只是搭个博客或小 API：香港 Pulse.Nano（$49）或 Pulse.Mini（$59）。2GB 和 4GB 内存的差别在跑数据库和缓存时很明显，能上 4GB 就上 4GB。

建站加一定访问量、需要稳定跑 WordPress 或中小型 Web 应用：Pulse.Air（$119）或 Pulse.Pro（$269），后者的 8 核 16G 是能撑住并发的位置。

单核性能决定成败，比如游戏服、实时应用、编译：Turin 系列。Ryzen 9 9950X 的差距在单线程任务上才看得出来，多开轻负载反而是 Pulse 更划算。Peak X5 同为 9950X 机型，磁盘小一截，价格需要自己去页面确认。

整机资源要独占、需要自己控制硬件：Forge，$599 起，56 核 112 线程 / 128GB 内存 / 960GB NVMe / 含 10TB 流量，超额 $0.06/GB 计费不停机，额外 IP 每个 $10 最多 4 个。

亚洲多地区部署：日本 Pulse 和新加坡 Pulse 同价，日本 Mini 的端口给到 1.5Gbps，面向华北用户时联通回程表现不错。

下单前最后确认两件事：结算页显示的实际金额（官网 store 页不标价，以结算页为准），以及你选的计费周期和优惠码是否真的生效。👉 [从 GoMami 香港 Pulse 系列开始挑一台](https://gomami.io/aff.php?aff=415&pid=4)
