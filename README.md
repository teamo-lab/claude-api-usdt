# 用 USDT 充值 Claude / GPT / 生图 API（不办 U卡、不用海外信用卡）

[English](#english) · [Русский](#русский) · 中文

想用 Claude、GPT 但没有海外信用卡，U卡办不下来，野卡也停了？可以直接用 USDT 给 [TeamoRouter](https://teamorouter.com/zh) 充值，一个 Key 按量调用 Claude、GPT（含 Codex 用的 GPT-6 系列）、GPT Image 生图、Gemini、DeepSeek 等 30 多个模型，适合个人开发者，也适合要同时接很多模型的产品和中转站，能开多个 Key 分开统计。

完整图文步骤见官方指南：[用 USDT 充值 Claude API](https://teamorouter.com/zh/blogs/pay-claude-with-usdt?utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt)。

## 要准备什么

1. 电脑浏览器（Chrome 等）装好 **OKX Wallet** 插件，并解锁钱包。
2. 钱包里有 **X Layer 网络上的 USDT**（链上显示为 USD₮0，和 USDT 1:1）。交易所里的余额不算，要先提到钱包。
3. 一个 TeamoRouter 账号。

## 把 USDT 转到 X Layer

| USDT 在哪 | 怎么转 |
|---|---|
| OKX 交易所 | 资产 → 提币 → USDT → 网络选 **X Layer** → 收款地址填自己的 OKX Wallet 地址 |
| 币安或其他交易所 | 先转到 OKX（网络选两边都支持的，比如 TRC20），再提到 X Layer；不想开 OKX 账号的话，币安提币网络选 Arbitrum（提出来就是 USDT0），再用 usdt0.to 转到 X Layer |
| TRON 链钱包（TRC20） | 目前不能直接付，要先转到 OKX，再提到 X Layer |
| 没有 OKX 账号 / 所在地区用不了 OKX | 用 USDT0 官方站 [usdt0.to](https://usdt0.to) 的 Transfer 跨链到 X Layer（来源链要付 gas，先转小额） |

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

## 给中转站、做产品要接多个模型的人

- 一个余额覆盖 Claude、GPT（含 gpt-image 生图）、Gemini、DeepSeek 等 30 多个模型，不用每家各开账号、各充一次值。
- 可以建多个 API Key，每个 Key 的用量分开统计，方便按客户或按项目对账。
- Claude 走 Anthropic 原生协议，其他模型走 OpenAI 兼容协议，现有代码一般只要换 base URL 和 Key。
- 用 USDT 充值没有拒卡和跨境手续费，适合没有海外公司卡的团队。

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

野卡停了在找替代的，见 [野卡停了怎么办](https://teamorouter.com/zh/blogs/yeka-wildcard-tingfu-zenmeban?utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt)。

没有 USDT 也可以用支付宝，见 [Claude 支付失败？没有海外银行卡的解决方案](https://teamorouter.com/zh/blogs/claude-payment-failed-no-overseas-card)。

---

## English

### Pay for Claude, GPT and image-generation APIs with USDT, no credit card needed

You can pay for Claude, GPT (including the GPT-6 models Codex uses), GPT Image, Gemini and DeepSeek API usage with USDT by topping up [TeamoRouter](https://teamorouter.com). One balance covers 30+ models, multiple API keys and tools like Claude Code and Codex.

**What you need:** a desktop browser with the **OKX Wallet** extension, and **USDT on the X Layer network** (shown on-chain as USD₮0). Exchange balances don't count until you withdraw them to your wallet. OKX can withdraw USDT straight to X Layer; from other exchanges, send it to OKX first. Without an OKX account, move USDT to X Layer with the Transfer page on the official USDT0 site, [usdt0.to](https://usdt0.to) (you pay gas on the source chain).

**Steps:** sign in, open the top-up dialog (minimum $5), click **"Pay with crypto"**, approve the connection, switch to X Layer when asked, and sign. You sign an authorization, so you don't need OKB for gas. Then create an API key and connect it, e.g. [Claude Code setup](https://teamorouter.com/docs/install-claude-code).

Full walkthrough: [Pay for the Claude API with USDT](https://teamorouter.com/blogs/pay-claude-with-usdt?utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt). Russian version: [Оплата Claude API в USDT](https://teamorouter.com/ru/blogs/pay-claude-with-usdt?utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt).

**Card declined on Claude?** See [How to pay for Claude when your card gets declined](https://teamorouter.com/blogs/claude-card-declined-payment-fixes-2026).

---

## Русский

### Оплата Claude, GPT и API генерации изображений в USDT, без зарубежной карты

Если карта не проходит, а подписка Claude или ChatGPT из России недоступна, можно пополнить баланс [TeamoRouter](https://teamorouter.com/ru?utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt) в USDT. Один ключ работает для Claude (Haiku / Sonnet / Opus), GPT (включая GPT-6 для Codex), GPT Image, Gemini и DeepSeek; списание только за использованные токены, без подписки. Claude Code подключается по родному протоколу Anthropic.

**Что понадобится:** браузер на компьютере с расширением **OKX Wallet** и **USDT в сети X Layer** (в блокчейне отображается как USD₮0, 1:1 к USDT). Баланс на бирже не считается, пока вы не выведете его в кошелёк. С OKX USDT выводится прямо в X Layer; с других бирж сначала переведите USDT на OKX (например, по TRC20), затем выведите в X Layer. Без аккаунта OKX перевести USDT в X Layer можно через раздел Transfer на официальном сайте USDT0 [usdt0.to](https://usdt0.to) (газ платится в исходной сети).

**Шаги:** войдите в консоль, откройте окно пополнения (минимум $5), нажмите **«Оплатить криптовалютой»**, подтвердите подключение кошелька, переключитесь на X Layer и подпишите запрос. Это подпись, а не перевод, поэтому платить за газ не нужно.

Подробная инструкция с частыми ошибками: [Как оплатить Claude API в USDT](https://teamorouter.com/ru/blogs/pay-claude-with-usdt?utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt). Нет USDT — можно оплатить в рублях (СБП, карта Мир, ЮMoney, SberPay): [Claude Code в России](https://teamorouter.com/ru/blogs/claude-code-in-russia?utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt).
