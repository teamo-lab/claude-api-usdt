# 用 USDT 充值 Claude / GPT / 生图 API（不办 U卡、不用海外信用卡）

[English](#english) · [Русский](#русский) · [Tiếng Việt](#tiếng-việt) · 中文

想用 Claude、GPT 但没有海外信用卡，U卡办不下来，野卡也停了？可以直接用 USDT 给 [TeamoRouter](https://teamorouter.com/zh) 充值，一个 Key 按量调用 Claude、GPT（含 Codex 用的 GPT-6 系列）、GPT Image 生图、Gemini、DeepSeek 等 30 多个模型，适合个人开发者，也适合要同时接很多模型的产品和中转站，能开多个 Key 分开统计。

在充值弹窗点 **「USDT支付」** 会跳到收银台页面：选好网络，再用币安、OKX 等交易所 App 或任意钱包，把 USDT 或 USDC 转到页面给出的地址即可。不用装浏览器钱包插件，手机上也能付，最低 5 美元。

完整图文步骤见官方指南：[用 USDT 充值 Claude API](https://teamorouter.com/zh/blogs/pay-claude-with-usdt?utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt)。

## 要准备什么

1. 一个 TeamoRouter 账号。
2. 交易所或钱包里的 **USDT 或 USDC**，数量要够付充值金额，再加上提币手续费。

不需要别的。收银台就是一个普通网页，手机上开着交易所 App 就能付。

## 支持哪些币和网络

| 币种 | 网络 | 说明 |
|---|---|---|
| USDT | BEP20（BNB Smart Chain） | 推荐，币安提币手续费约 0.01 USDT |
| USDT | TRC20（Tron 波场） | 币安提币手续费约 1.5 USDT |
| USDT | ERC20（以太坊） | |
| USDT | TON | |
| USDC | Base | |
| USDC | BSC（BNB Smart Chain） | |

以收银台页面显示的为准。提币手续费由各交易所定，会调整，以提币页面显示的为准。

## 充值步骤

1. 登录 TeamoRouter，在控制台打开充值弹窗，选择金额（不低于 5 美元）。
2. 点 **「USDT支付」**，页面会跳到收银台。
3. 在收银台选你要转出的币种和网络。页面会显示要转的数量和收款地址，这一单 **60 分钟内有效**。
4. 打开交易所 App 发起提币（用钱包的话就是「发送/转账」）：选**同一个币种、同一个网络**，粘贴收银台上的地址，填写数量时保证**到账数量不少于页面上的数量**。如果收银台上还显示了备注（memo/tag），也要一起填上。
5. 等链上确认。付款确认后余额会自动到账，中途关掉收银台页面也不影响。如果暂时没看到，过一会儿再刷新，不要重复付款。
6. 到账后在控制台 [创建 API Key](https://teamorouter.com/dashboard?tab=api-keys&utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt)。

## 这几种情况会导致付款失败，提前避开

- **提币网络和收银台选的不一致。** 提币时选的网络必须和收银台上选的一样。比如 BEP20 和 ERC20 的地址都是 0x 开头，交易所允许你用 ERC20 往收银台给的 BEP20 地址转 USDT，但这笔转账不会算作这一单的付款。不同交易所对网络的叫法不一样：BEP20 也可能写作 BSC 或 BNB Smart Chain，TRC20 写作 Tron，ERC20 写作 Ethereum。交易所里这个币没有你想用的网络，就回收银台换一个交易所支持的网络。
- **提币手续费让到账金额变少。** 很多交易所是从你填的数量里扣手续费。确认提币前看一眼提币页面上的「到账数量」，要不少于收银台上的数量；手续费是从填写数量里扣的，就把手续费加上去再填。少付不超过 1% 仍按付清处理；少得更多，不要再补转一笔，带上 TxID 联系客服。多付的话，余额按订单金额到账，多出的部分可以联系客服处理。
- **交易所审核太久，订单 60 分钟过期。** 交易所有时会把提币转人工审核，用时可能超过 60 分钟。点「USDT支付」之前，先确认币已经在你要提币的交易所账户里。还没转订单就过期了：回收银台续期，或回控制台重新下一单，按页面上当前有效的地址转，不要用之前复制的旧地址。已经转了订单才过期：不要再转第二笔，先回收银台续期这一单，还解决不了就带上 TxID 联系客服。

## TxID 去哪找

TxID（也叫交易哈希、Txn Hash）是这笔转账在链上的编号，客服查款要用。

- **交易所 App：** 打开提币记录，点进这笔提币，在详情里复制 TxID。交易所真正把币转出后才会有 TxID；还在审核中的提币暂时没有。
- **钱包：** 在钱包的交易记录里点开这笔转账，详情里就有交易哈希。

联系客服时请一起提供：TxID、网络、金额、转出时间，以及充值的 TeamoRouter 账号。

## 常见问题

- **要付手续费吗？** 收银台不额外收手续费。你只需要付交易所的提币手续费；用钱包转的话，付该网络的 gas。
- **哪个网络最省钱？** 一般是 BEP20：币安提 USDT 走 BEP20 手续费约 0.01 USDT，走 TRC20 约 1.5 USDT。
- **手机能付吗？** 能。手机上打开收银台页面，把地址和数量复制到交易所 App 里提币即可。
- **转了钱，余额没变？** 不要重复付款，链上可能还在确认，过一会儿刷新控制台。如果订单过期了或少付了，按上面「这几种情况会导致付款失败」处理；还解决不了，带上 TxID 联系客服。

## 已经有 X Layer 上的 USDT？用 OKX 钱包付款

OKX Wallet 和其他钱包一样，可以直接在收银台付款：在收银台选好网络，从钱包里转过去。用钱包转账要有该网络上付 gas 的币，比如 BEP20 要有 BNB。

如果你的 USDT 已经在 X Layer 上（链上显示为 USD₮0），也可以不走收银台：在电脑浏览器里装好并解锁 OKX Wallet 插件（[Chrome 应用商店](https://chromewebstore.google.com/detail/okx-wallet/mcohilncbfahbmgdjkbpemcciiolgcge)），充值弹窗里会多出一个链接 **「已有 OKX 钱包（X Layer）？用钱包付款」**。点这个链接，不要点「USDT支付」按钮：

1. 在充值弹窗选择金额（最低 5 美元），点 **「已有 OKX 钱包（X Layer）？用钱包付款」**，钱包弹出连接请求，确认。
2. 钱包提示切换到 X Layer（第一次会提示添加网络），确认。
3. 钱包弹出签名请求，确认后等待到账。这一步是签名授权，不需要准备 OKB 付 gas。

币要在钱包的 X Layer 上，交易所里的余额、其他链上的 USDT 都不算。把 USDT 转到 X Layer：

| USDT 在哪 | 怎么转 |
|---|---|
| OKX 交易所 | 资产 → 提币 → USDT → 网络选 **X Layer** → 收款地址填自己的 OKX Wallet 地址 |
| 币安或其他交易所 | 先转到 OKX（网络选两边都支持的，比如 TRC20），再提到 X Layer；不想开 OKX 账号的话，币安提币网络选 Arbitrum（提出来就是 USDT0），再用 usdt0.to 转到 X Layer |
| 没有 OKX 账号 / 所在地区用不了 OKX | 用 USDT0 官方站 [usdt0.to](https://usdt0.to) 的 Transfer 跨链到 X Layer（来源链要付 gas，先转小额） |

这条路线的常见报错：

| 提示 | 原因 | 处理 |
|---|---|---|
| 找不到钱包 | 没装插件或没解锁 | 装好 OKX Wallet 并解锁，刷新页面 |
| 已拒绝签名 | 在钱包里点了拒绝 | 重新点「已有 OKX 钱包（X Layer）？用钱包付款」 |
| 余额不足 | X Layer 上的 USDT 不够 | 往钱包的 X Layer 地址转够 USDT |
| 网络切换失败 | 钱包没切到 X Layer | 在钱包里手动切换后重试 |

## 充值后怎么用

- 一个 API Key 调用 Claude（Haiku / Sonnet / Opus / Fable）、GPT、Gemini、DeepSeek 等，按实际用掉的 token 扣费，没有订阅。
- Claude 走 Anthropic 原生协议，[Claude Code 接入教程](https://teamorouter.com/zh/docs/install-claude-code)。
- 想了解它和其他中转的区别：[Claude API 中转](https://teamorouter.com/zh/claude-api-zhongzhuan)。

## 给中转站、做产品要接多个模型的人

- 一个余额覆盖 Claude、GPT（含 gpt-image 生图）、Gemini、DeepSeek 等 30 多个模型，不用每家各开账号、各充一次值。
- 可以建多个 API Key，每个 Key 的用量分开统计，方便按客户或按项目对账。
- Claude 走 Anthropic 原生协议，其他模型走 OpenAI 兼容协议，现有代码一般只要换 base URL 和 Key。
- 用 USDT 充值没有拒卡和跨境手续费，适合没有海外公司卡的团队。

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

You can pay for Claude, GPT (including the GPT-6 models Codex uses), GPT Image, Gemini and DeepSeek API usage with USDT or USDC by topping up [TeamoRouter](https://teamorouter.com). One balance covers 30+ models, multiple API keys and tools like Claude Code and Codex.

**What you need:** a TeamoRouter account and USDT or USDC on an exchange or in a wallet, enough to cover the top-up amount plus the withdrawal fee. No browser extension is needed, and it works on a phone.

**Coins and networks:** USDT on BEP20, TRC20, ERC20 or TON, and USDC on Base or BSC; the checkout page shows the current list. Pick **USDT on BEP20** if you can: Binance charges about 0.01 USDT to withdraw on BEP20, against about 1.5 USDT on TRC20. Withdrawal fees are set by each exchange and change over time, so check the fee on the withdrawal screen.

**Steps:**

1. Sign in, open the top-up dialog and choose an amount ($5 or more).
2. Click **"Pay with crypto"** (on a narrow screen the button reads **"Crypto"**). You're taken to the checkout page.
3. Pick the coin and network you'll send from. The page shows the amount to send and a deposit address. The invoice is valid for **60 minutes**.
4. In your exchange app, start a withdrawal (in a wallet, a send): choose the **same coin and the same network**, paste the address, and enter the amount so that what arrives is **no less than the amount on the page**. If the page also shows a memo or tag, enter it too.
5. Wait for the network to confirm. Your balance is credited once the payment is confirmed, even if you close the checkout page. If it hasn't shown up yet, refresh in a while and don't pay again.
6. Create an API key and connect it, e.g. [Claude Code setup](https://teamorouter.com/docs/install-claude-code).

**What makes a payment fail:**

- **A different network.** A transfer on a network other than the one you picked on the checkout page doesn't count as payment, even when the exchange accepts the address (BEP20 and ERC20 addresses both start with 0x). Exchanges may call BEP20 "BSC" or "BNB Smart Chain", TRC20 "Tron" and ERC20 "Ethereum".
- **The withdrawal fee.** Many exchanges take it out of the amount you type. Check that the "amount received" is at least the amount on the checkout page; if not, add the fee on top. An invoice up to 1% short still counts as paid. If more is missing, don't send again; contact support with your TxID. If you send more, your balance is credited with the order amount, and you can contact support about the extra.
- **The 60-minute invoice.** An exchange's manual review can take longer than that, so have the coins in your exchange account before you click "Pay with crypto". Expired before you sent: renew the invoice on the checkout page or start a new top-up, and send to the address that's currently valid. Expired after you sent: don't send again; renew the invoice on the checkout page, then contact support with your TxID if that doesn't resolve it.

**Finding your TxID** (transaction hash, Txn Hash): in your exchange app, open the withdrawal history, tap this withdrawal and copy the TxID from its details. It only appears once the exchange has actually sent the transfer. In a wallet, it's in the transaction details. When you contact support, include the TxID, network, amount, time sent and your TeamoRouter account.

**Already have USDT on X Layer?** OKX Wallet works on the checkout page like any other wallet (sending from a wallet needs the network's coin for gas, e.g. BNB on BEP20). If your USDT is already on X Layer (shown on-chain as USD₮0), you can skip the checkout page: with the **OKX Wallet** extension ([Chrome Web Store](https://chromewebstore.google.com/detail/okx-wallet/mcohilncbfahbmgdjkbpemcciiolgcge)) installed and unlocked in a desktop browser, the top-up dialog shows an extra link, **"Have USDT on X Layer? Pay with OKX Wallet"**. Click that link instead of "Pay with crypto", approve the connection, switch to X Layer when asked, and sign. You sign an authorization, so you don't need OKB for gas. Exchange balances and USDT on other chains don't count; OKX can withdraw USDT straight to X Layer, and without an OKX account you can move USDT there with the Transfer page on [usdt0.to](https://usdt0.to) (you pay gas on the source chain).

Full walkthrough: [Pay for the Claude API with USDT](https://teamorouter.com/blogs/pay-claude-with-usdt?utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt). Russian version: [Оплата Claude API в USDT](https://teamorouter.com/ru/blogs/pay-claude-with-usdt?utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt).

**Card declined on Claude?** See [How to pay for Claude when your card gets declined](https://teamorouter.com/blogs/claude-card-declined-payment-fixes-2026).

---

## Русский

### Оплата Claude, GPT и API генерации изображений в USDT, без зарубежной карты

Если карта не проходит, а подписка Claude или ChatGPT из России недоступна, можно пополнить баланс [TeamoRouter](https://teamorouter.com/ru?utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt) в USDT или USDC. Один ключ работает для Claude (Haiku / Sonnet / Opus), GPT (включая GPT-6 для Codex), GPT Image, Gemini и DeepSeek; списание только за использованные токены, без подписки. Claude Code подключается по родному протоколу Anthropic.

**Что понадобится:** аккаунт TeamoRouter и USDT или USDC на бирже или в кошельке — столько, чтобы хватило на сумму пополнения плюс комиссию за вывод. Расширение для браузера не нужно, оплатить можно и с телефона.

**Монеты и сети:** USDT в сетях BEP20, TRC20, ERC20 и TON, USDC в сетях Base и BSC; актуальный список — на странице оплаты. Если есть выбор, берите **USDT в BEP20**: Binance берёт за вывод в BEP20 около 0,01 USDT, а в TRC20 — около 1,5 USDT. Комиссии за вывод устанавливает каждая биржа, и они меняются, поэтому сверяйтесь с экраном вывода.

**Шаги:**

1. Войдите в консоль, откройте окно пополнения и выберите сумму (от $5).
2. Нажмите **«Оплатить криптовалютой»** (на узком экране кнопка называется **«Крипто»**) — откроется страница оплаты.
3. Выберите монету и сеть, с которой будете отправлять. Страница покажет сумму к отправке и адрес для перевода. Счёт действует **60 минут**.
4. В приложении биржи оформите вывод (в кошельке — отправку): выберите **ту же монету и ту же сеть**, вставьте адрес со страницы оплаты и укажите сумму так, чтобы к зачислению пришло **не меньше суммы на странице**. Если на странице есть memo или tag, укажите и его.
5. Дождитесь подтверждения в сети. Баланс зачисляется после подтверждения платежа, даже если вы закрыли страницу оплаты. Если баланс ещё не обновился, обновите консоль чуть позже и не платите повторно.
6. После зачисления создайте API-ключ.

**Из-за чего платёж не проходит:**

- **Другая сеть.** Перевод в сети, отличной от выбранной на странице оплаты, не засчитывается как оплата, даже если биржа принимает адрес (адреса BEP20 и ERC20 оба начинаются с 0x). Биржи называют сети по-разному: BEP20 — BSC или BNB Smart Chain, TRC20 — Tron, ERC20 — Ethereum.
- **Комиссия за вывод.** Многие биржи вычитают её из введённой суммы. Проверьте, что сумма «к получению» не меньше суммы на странице оплаты; если меньше, прибавьте комиссию сверху. Недоплата до 1% всё равно считается оплатой. Если не хватает больше, не отправляйте второй перевод — напишите в поддержку и приложите TxID. При переплате баланс пополняется на сумму заказа, по излишку можно обратиться в поддержку.
- **Счёт на 60 минут.** Ручная проверка вывода на бирже может занять больше, поэтому монеты должны уже лежать на бирже до того, как вы нажмёте «Оплатить криптовалютой». Счёт истёк до отправки — продлите его на странице оплаты или начните новое пополнение и отправляйте на действующий адрес. Истёк после отправки — не отправляйте повторно: продлите счёт на странице оплаты, а если это не помогло, напишите в поддержку и приложите TxID.

**Где найти TxID** (хеш транзакции, Txn Hash): в приложении биржи откройте историю выводов, нажмите на этот вывод и скопируйте TxID из деталей. Он появляется только после того, как биржа действительно отправила перевод. В кошельке хеш указан в деталях транзакции. В поддержку пришлите TxID, сеть, сумму, время отправки и аккаунт TeamoRouter.

**Уже есть USDT в X Layer?** OKX Wallet работает на странице оплаты как любой другой кошелёк (для отправки из кошелька нужна монета сети для газа, например BNB в BEP20). Если USDT уже в X Layer (в блокчейне отображается как USD₮0), можно обойтись без страницы оплаты: когда в браузере на компьютере установлено и разблокировано расширение **OKX Wallet** ([Chrome Web Store](https://chromewebstore.google.com/detail/okx-wallet/mcohilncbfahbmgdjkbpemcciiolgcge)), в окне пополнения появляется ссылка **«Есть USDT в X Layer? Оплатить через OKX Wallet»**. Нажмите её (а не кнопку «Оплатить криптовалютой»), подтвердите подключение кошелька, переключитесь на X Layer и подпишите запрос. Это подпись, а не перевод, поэтому платить за газ не нужно. Баланс на бирже и USDT в других сетях не считаются; с OKX USDT выводится прямо в X Layer, а без аккаунта OKX перевести USDT в X Layer можно через раздел Transfer на [usdt0.to](https://usdt0.to) (газ платится в исходной сети).

Подробная инструкция с частыми ошибками: [Как оплатить Claude API в USDT](https://teamorouter.com/ru/blogs/pay-claude-with-usdt?utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt). Нет USDT — можно оплатить в рублях (СБП, Т-Банк, ЮMoney, SberPay): [Claude Code в России](https://teamorouter.com/ru/blogs/claude-code-in-russia?utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt).

---

## Tiếng Việt

### Thanh toán Claude, GPT và API tạo ảnh bằng USDT, không cần thẻ quốc tế

Không có thẻ Visa quốc tế, hoặc thẻ bị từ chối khi mua Claude? Bạn có thể nạp USDT hoặc USDC vào [TeamoRouter](https://teamorouter.com?utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt-vi) và dùng một API key cho Claude (Haiku / Sonnet / Opus), GPT (kể cả GPT-6 cho Codex), GPT Image, Gemini và DeepSeek. Trả theo lượng token dùng thực tế, không thuê bao, nạp từ $5. Claude chạy giao thức gốc của Anthropic, nên Claude Code chỉ cần đổi base URL.

**Cần chuẩn bị:** tài khoản TeamoRouter và USDT hoặc USDC trên sàn hoặc trong ví, đủ cho số tiền nạp cộng phí rút. Không cần tiện ích trình duyệt, thanh toán được cả trên điện thoại.

**Coin và mạng hỗ trợ:** USDT trên BEP20, TRC20, ERC20, TON và USDC trên Base, BSC; danh sách hiện hành xem trên trang thanh toán. Nên chọn **USDT BEP20**: Binance thu khoảng 0,01 USDT khi rút qua BEP20, so với khoảng 1,5 USDT qua TRC20. Phí rút do từng sàn đặt và có thể thay đổi, hãy xem trên màn hình rút.

**Các bước:**

1. Đăng nhập, mở cửa sổ nạp tiền và chọn số tiền (từ $5).
2. Bấm **"Pay with crypto"** (trên màn hình hẹp nút hiển thị **"Crypto"**), bạn sẽ được chuyển tới trang thanh toán.
3. Chọn coin và mạng bạn sẽ gửi. Trang hiển thị số tiền cần gửi và địa chỉ nhận. Hóa đơn có hiệu lực **60 phút**.
4. Trong ứng dụng sàn, tạo lệnh rút (trong ví là lệnh gửi): chọn **đúng coin và đúng mạng**, dán địa chỉ từ trang thanh toán, nhập số tiền sao cho số tiền nhận được **không ít hơn số tiền trên trang**. Nếu trang có hiển thị memo hoặc tag, hãy nhập cả memo/tag.
5. Chờ mạng xác nhận. Số dư được cộng sau khi thanh toán được xác nhận, kể cả khi bạn đã đóng trang thanh toán. Nếu chưa thấy, hãy tải lại sau ít phút và đừng thanh toán lại.
6. Khi số dư đã vào, tạo API key và bắt đầu gọi mô hình.

**Những lỗi khiến thanh toán thất bại:**

- **Rút sai mạng.** Giao dịch trên mạng khác với mạng đã chọn ở trang thanh toán sẽ không được tính là thanh toán, kể cả khi sàn chấp nhận địa chỉ (địa chỉ BEP20 và ERC20 đều bắt đầu bằng 0x). Tên mạng mỗi sàn một khác: BEP20 có thể là BSC hoặc BNB Smart Chain, TRC20 là Tron, ERC20 là Ethereum.
- **Phí rút làm hụt số tiền.** Nhiều sàn trừ phí vào số tiền bạn nhập. Hãy kiểm tra dòng "số tiền nhận được" ít nhất bằng số tiền trên trang thanh toán; nếu chưa đủ, cộng thêm phí. Hóa đơn thiếu tối đa 1% vẫn được tính là đã thanh toán. Thiếu nhiều hơn thì đừng gửi thêm lần nữa, hãy liên hệ hỗ trợ kèm TxID. Nếu gửi dư, số dư được cộng theo số tiền đơn hàng, phần dư có thể liên hệ hỗ trợ.
- **Hóa đơn 60 phút.** Sàn đôi khi giữ lệnh rút để duyệt thủ công, có thể lâu hơn 60 phút, nên hãy để sẵn coin trong tài khoản sàn trước khi bấm "Pay with crypto". Hết hạn khi chưa gửi: gia hạn hóa đơn trên trang thanh toán hoặc tạo lệnh nạp mới, và gửi tới địa chỉ đang hiệu lực. Hết hạn sau khi đã gửi: đừng gửi lại; gia hạn hóa đơn trên trang thanh toán, nếu vẫn chưa được thì liên hệ hỗ trợ kèm TxID.

**TxID ở đâu** (transaction hash, Txn Hash): trong ứng dụng sàn, mở lịch sử rút, chọn lệnh rút này và sao chép TxID trong phần chi tiết. TxID chỉ xuất hiện khi sàn đã thực sự gửi đi. Trong ví, hash nằm trong chi tiết giao dịch. Khi liên hệ hỗ trợ, gửi kèm TxID, mạng, số tiền, thời gian gửi và tài khoản TeamoRouter đã nạp.

**Đã có USDT trên X Layer?** OKX Wallet cũng dùng được trên trang thanh toán như mọi ví khác (gửi từ ví cần coin của mạng đó để trả gas, ví dụ BNB trên BEP20). Nếu USDT của bạn đã ở trên X Layer (trên chuỗi hiển thị là USD₮0), có thể bỏ qua trang thanh toán: khi tiện ích **OKX Wallet** ([Chrome Web Store](https://chromewebstore.google.com/detail/okx-wallet/mcohilncbfahbmgdjkbpemcciiolgcge)) đã được cài và mở khóa trên trình duyệt máy tính, cửa sổ nạp tiền hiện thêm liên kết **"Have USDT on X Layer? Pay with OKX Wallet"**. Bấm liên kết đó (không phải nút "Pay with crypto"), xác nhận kết nối ví, chuyển sang X Layer khi được hỏi và ký. Đây là chữ ký ủy quyền, không phải bạn tự gửi giao dịch, nên không tốn phí gas. Số dư trên sàn và USDT trên mạng khác không được tính; từ Binance có thể rút USDT qua mạng Arbitrum (đó là USDT0) về địa chỉ OKX Wallet rồi chuyển sang X Layer bằng trang Transfer của [usdt0.to](https://usdt0.to) (cần một ít ETH trên Arbitrum để trả phí).

Hướng dẫn chi tiết (tiếng Anh): [How to pay with crypto](https://teamorouter.com/blogs/pay-claude-with-usdt?utm_source=github&utm_medium=readme&utm_campaign=claude-api-usdt-vi).
