# 用 USDT 充值 Claude API（不办 U卡、不用海外信用卡）

[English](#english) · 中文

想用 Claude、GPT 但没有海外信用卡，U卡办不下来，野卡也停了？可以直接用 USDT 给 [TeamoRouter](https://teamorouter.com/zh) 充值，按量调用 Claude、GPT、Gemini、DeepSeek 等模型，也能接 Claude Code 和 Codex。

## 要准备什么

1. 电脑浏览器（Chrome 等）装好 **OKX Wallet** 插件，并解锁钱包。
2. 钱包里有 **X Layer 网络上的 USDT**（链上显示为 USD₮0，和 USDT 1:1）。交易所里的余额不算，要先提到钱包。
3. 一个 TeamoRouter 账号。

## 把 USDT 转到 X Layer

| USDT 在哪 | 怎么转 |
|---|---|
| OKX 交易所 | 资产 → 提币 → USDT → 网络选 **X Layer** → 收款地址填自己的 OKX Wallet 地址 |
| 币安或其他交易所 | 先转到 OKX（网络选两边都支持的，比如 TRC20），再提到 X Layer |
| TRON 链钱包（TRC20） | 目前不能直接付，要先转到 OKX，再提到 X Layer |

第一次建议先转小额试一下，确认网络和地址都对。

## 充值步骤

1. 登录 TeamoRouter，在控制台打开充值弹窗，最低 5 美元。
2. 点 **「USDT支付」**，钱包弹出连接请求，确认。
3. 钱包提示切换到 X Layer（第一次会提示添加网络），确认。
4. 钱包弹出签名请求，确认后等待到账。这一步是签名授权，不需要准备 OKB 付 gas。
5. 到账后在控制台创建 API Key。

## 充值后怎么用

- 一个 API Key 调用 Claude（Haiku / Sonnet / Opus / Fable）、GPT、Gemini、DeepSeek 等，按实际用掉的 token 扣费，没有订阅。
- Claude 走 Anthropic 原生协议，[Claude Code 接入教程](https://teamorouter.com/zh/docs/install-claude-code)。
- 想了解它和其他中转的区别：[Claude API 中转](https://teamorouter.com/zh/claude-api-zhongzhuan)。

## 常见报错

| 提示 | 原因 | 处理 |
|---|---|---|
| 找不到钱包 | 没装插件或没解锁 | 装好 OKX Wallet 并解锁，刷新页面 |
| 已拒绝签名 | 在钱包里点了拒绝 | 重新点「USDT支付」 |
| 余额不足 | X Layer 上的 USDT 不够 | 往钱包的 X Layer 地址转够 USDT |
| 网络切换失败 | 钱包没切到 X Layer | 在钱包里手动切换后重试 |

## 和办 U卡 / 虚拟卡订阅官方比

| | USDT 直接充值 | U卡 / 虚拟卡订阅官方 |
|---|---|---|
| 要不要办卡、实名 | 不用 | 要 |
| 会不会被拒卡 | 不走信用卡 | 卡段可能被 Stripe 拒 |
| 计费 | 按量付费 | 月订阅 |
| 模型 | Claude、GPT、Gemini 等多家 | 只有订阅的那一家 |

没有 USDT 也可以用支付宝，见 [Claude 支付失败？没有海外银行卡的解决方案](https://teamorouter.com/zh/blogs/claude-payment-failed-no-overseas-card)。

---

## English

### Pay for the Claude API with USDT — no credit card, no crypto card

You can pay for Claude, GPT and Gemini API usage with USDT by topping up [TeamoRouter](https://teamorouter.com). The balance also works with Claude Code and Codex.

**What you need:** a desktop browser with the **OKX Wallet** extension, and **USDT on the X Layer network** (shown on-chain as USD₮0). Exchange balances don't count until you withdraw them to your wallet. OKX can withdraw USDT straight to X Layer; from other exchanges, send it to OKX first.

**Steps:** sign in, open the top-up dialog (minimum $5), click **"Pay with crypto"**, approve the connection, switch to X Layer when asked, and sign. You sign an authorization, so you don't need OKB for gas. Then create an API key and connect it, e.g. [Claude Code setup](https://teamorouter.com/docs/install-claude-code).

**Card declined on Claude?** See [How to pay for Claude when your card gets declined](https://teamorouter.com/blogs/claude-card-declined-payment-fixes-2026).
