# Research Company Paperwork

Use this reference to generate Chinese customer research for MongoDB sales and Marketing lead follow-up.

## Purpose

Create a concise Chinese company research form from a customer name, company website, or Marketing lead. The output should help sales understand what the company does, whether it has overseas or global business, company size and trend, business/revenue trend, recent signals, and practical call talking points.

## Required Inputs

- Company name or company website.

## Optional Inputs

- Country, region, industry, lead source, product interest, target contact, known workload, or sales context.

## Source And Research Rules

- Browse the internet by default because employee size, revenue trend, overseas business, and recent news can change.
- Prefer public sources: company website, investor relations, annual reports, earnings releases, press releases, official blogs, official WeChat public accounts and reposts, hiring pages, LinkedIn, credible media, app stores, industry databases, and public company information pages.
- If the company is public, prioritize annual reports, financial reports, investor relations pages, and earnings releases for revenue and trend.
- If the company is private, do not stop at `未公开披露营收`. First search for approximate revenue scale, product revenue, GMV, downloads, grossing rankings, overseas revenue rankings, financing/valuation, IPO/prospectus materials, industry reports, and credible media estimates.
- For game, consumer internet, SaaS, ecommerce, or app companies, use third-party data providers and industry media as proxy sources when official revenue is unavailable. Useful sources include Sensor Tower, data.ai, 点点数据, 七麦数据, GameLook, 伽马数据, QuestMobile, Similarweb, App Store / Google Play rankings, financing reports, and credible business media.
- For private companies, do not invent exact revenue. If exact company revenue is unavailable, provide a clearly labeled approximate scale or trend based on third-party estimates, product-level revenue, publisher rankings, app rankings, financing/valuation, hiring, product launches, market expansion, customer growth, store footprint, partnerships, and media coverage.
- Mark third-party estimates clearly with wording such as `第三方估算口径`, `行业报告口径`, `媒体引用口径`, or `产品流水/榜单代理指标`.
- If sources conflict, say `公开来源口径不一致` and briefly explain the difference.
- Do not present unsupported precise numbers. Use ranges or qualitative wording when sources are incomplete.
- If the company name is ambiguous, use the provided website to confirm identity. If no website is provided and multiple companies plausibly match, ask the user to confirm the target company.
- For recent-news discovery, use `$wechat-weixin-search-skill-fast` or its fast workflow to search WeChat Official Account / 搜狗微信 results for the target company.
- Use WeChat sources mainly for product launches, version updates, brand events, exhibitions, partnerships, company announcements, AI/data/cloud signals, overseas expansion, and sales-useful business context; do not use them as the sole source for revenue, employee size, or financial trend.
- Treat 搜狗微信 links as reference/search-result links, not confirmed original `mp.weixin.qq.com` article links, unless the user explicitly asks for slower article resolution.
- If any WeChat/搜狗微信 result is selected as useful, list it as its own recent-news item with the concrete date, title/event, sales value, and source. Never collapse selected WeChat items into a generic summary such as `多条微信公众号结果`, `公众号相关信息`, or `版号、校招和 AI 相关信息`.
- Select recent news by usefulness for sales conversation, not just by search rank or source type. Prefer product launches, organization changes, business innovation, market feedback, financing, earnings, overseas expansion, major partnerships, regulatory issues, or risk events.
- Give timely and sales-useful WeChat/公众号 results a slight ranking boost in `近期新闻`, especially when they reveal fresh product launches, partnerships, overseas expansion, AI/data/cloud signals, security updates, or company announcements not yet well covered by official websites or mainstream media.
- Exclude low-value WeChat results such as hiring, campus recruiting, internships, referrals, training, course registration, stock-only posts, and pure reposts without business context when enough better results exist.

## Output Language

- Default to Chinese only.
- Keep English company names, product names, proper nouns, source titles, and URLs in their original form when useful.
- This reference overrides the shared bilingual default in `style-guide.md`.

## Output Fields

Generate these fields in this order.

### 公司名称

- Provide the official or commonly used company name.
- Include an English name only when it is useful for identification.
- If identity is uncertain, state the uncertainty briefly.

### 客户网址

- Provide the official website when found.
- If no official website is confirmed, write `公开信息未确认`.

### 业务简介

- About 100 Chinese characters.
- Summarize the main business, core products or services, target customers, and industry position.
- Keep it direct and useful for sales preparation.

### 海外 / 全球业务

- State whether the company appears to have overseas or global business.
- Mention overseas markets, international users, offices, product availability, subsidiaries, global distribution, or cross-border business when found.
- If not confirmed, write `公开信息未确认`.

### 公司人数与趋势

- Provide a public employee count or range when available.
- State the trend as one of: `增加`, `减少`, `持平`, or `公开信息未确认`.
- Explain the basis briefly, such as hiring activity, LinkedIn headcount, annual report employee count, layoff news, or company expansion.

### 营收 / 业务趋势

- For public companies, summarize the latest revenue direction from official reports when available.
- For private companies, search for approximate revenue scale before saying revenue is undisclosed. Look for IPO/prospectus materials, financing/valuation, credible media reports, industry reports, third-party estimates, product revenue, GMV, downloads, grossing rankings, overseas revenue rankings, and app/store ranking signals.
- If exact company revenue is unavailable but useful proxy data exists, write the proxy and label the source type, for example `Sensor Tower 口径`, `行业报告口径`, `媒体引用口径`, or `产品流水/榜单代理指标`.
- Summarize three things when possible: overall revenue scale or proxy scale, growth/decline direction, and the key growth or pressure signals.
- Use business-friendly conclusions such as `增长`, `下降`, `持平`, `收入规模较大但增长不稳定`, `海外业务增长明显`, `新品接力仍是关键变量`, or `公开信息未确认`, followed by concise evidence.
- Only use `公开信息未确认` after no useful public revenue, proxy, ranking, financing, or business-scale signal is found.

### 近期新闻

- List 5-10 recent items when available.
- Each item should include date or approximate timing, short title/event, why it matters for sales conversation, and source.
- Merge official website, credible media, LinkedIn, app stores, official WeChat public accounts, and credible WeChat/搜狗微信 results into one ranked list. Do not create a separate `官方微信公众号补充` field.
- When useful WeChat results exist, include about 2-4 WeChat/公众号 items in the 5-10 recent-news list. Only include WeChat results with `中`, `中高`, or `高` sales value.
- Each included WeChat/公众号 item must be listed individually with its specific title/event. Do not group multiple selected WeChat items into one bullet.
- Give newer WeChat/公众号 items a slight priority boost when they are sales-useful and concrete, but do not force low-value items into the list.
- If WeChat results are mostly hiring, training, stock-only, unrelated, or low-value reposts, reduce or omit them and state `公众号公开结果中未发现足够高价值销售信号`.
- Mark WeChat sources as `微信公众号/搜狗微信结果` or with the actual public account name when available.
- Rank by sales usefulness, recency, and source reliability. Every item should explain why it is useful for a sales conversation, not just repeat the headline.
- If fewer than 5 reliable items are found, list the reliable items and say that additional recent public news is limited.

### 销售沟通切入点

- Provide 3-5 concise call talking points or questions.
- Tie each point to business context, overseas expansion, product launch, market feedback, data growth, user experience, operations, or risk reduction.
- Write them as usable conversation prompts.

### MongoDB 相关性

- Explain likely MongoDB-relevant data scenarios based on the company's business.
- Examples include user profiles, orders, transactions, game data, IoT data, logs, real-time analytics, search, AI, content metadata, global deployment, operational dashboards, and event streams.
- Keep the wording as hypotheses unless confirmed by sources or user input.

### 信息来源

- List the key source links used.
- Prefer official sources first, then credible third-party sources.
- Include WeChat/搜狗微信 search-result links that were actually used in `近期新闻`.
- Do not include sources that were not actually used.

## Output Format

Use this exact field order and Chinese-only pattern:

```markdown
# 公司名称

...

### 客户网址

...

### 业务简介

...
```

Continue the same pattern for all required fields. Keep the result concise enough to paste into an internal form.

## Missing Information

If the company name and website are both missing, ask for the company name or website. If the company name is ambiguous and no website is provided, ask the user to confirm which company to research.

## Example Input

研究米哈游这家公司，看看他们有没有海外业务、公司人数趋势、最近有什么新闻，方便我后续电话沟通。

## Example Output Style

# 公司名称

米哈游（miHoYo / HoYoverse）

### 客户网址

https://www.mihoyo.com/

### 业务简介

米哈游是一家游戏与互动娱乐公司，核心产品包括《原神》《崩坏：星穹铁道》等，业务覆盖游戏研发、发行、社区运营和相关内容生态，用户群体具有明显全球化特征。

### 海外 / 全球业务

米哈游有明确的全球业务布局，海外品牌 HoYoverse 面向国际市场运营多款游戏，产品在多个国家和地区发行，并通过全球社区、活动和多语言服务触达海外玩家。

### 公司人数与趋势

公开信息显示公司规模较大，但不同来源口径可能不一致。若近期招聘、海外发行和新产品运营持续活跃，可判断人数趋势偏 `增加` 或至少保持较高运营投入；最终应以官网招聘、LinkedIn 或年报类来源核验。

### 营收 / 业务趋势

米哈游为非上市公司，不应编造官方营收，但应继续查找第三方估算和产品流水代理指标。若 Sensor Tower、data.ai、点点数据、七麦数据、GameLook、伽马数据或可信媒体披露产品收入、发行商排名、海外收入榜或下载/畅销榜表现，可用 `第三方估算口径` 或 `产品流水/榜单代理指标` 描述收入量级和趋势。若没有公司整体营收，可结合核心产品长线流水、全球发行、新内容更新、市场排名和新品表现判断业务趋势，并明确来源口径。

### 近期新闻

1. 近期产品更新或版本发布：可用于了解其内容生产节奏和玩家运营压力。来源：官网/官方公告。
2. 海外品牌或全球活动动态：可用于切入全球化运营和多区域数据管理话题。来源：可信媒体或官方新闻。
3. 2026-05-27｜5 月游戏版号观察，莉莉丝新品在列：可用于判断国内产品储备和上线节奏。来源：微信公众号/搜狗微信结果。
4. 2026-02-27｜2 月游戏版号下发，莉莉丝产品在列：可作为持续产品管线信号。来源：微信公众号/搜狗微信结果。

### 销售沟通切入点

1. 近期版本更新和活动是否带来玩家峰值、数据增长或实时运营压力？
2. 海外发行过程中，不同区域的数据合规、性能和运维是否需要统一平台支持？
3. 新产品或新玩法是否带来更复杂的玩家画像、事件数据和内容配置管理？

### MongoDB 相关性

可能相关的数据场景包括玩家画像、账号与角色状态、活动配置、游戏事件日志、实时运营分析、内容元数据、社区互动数据和全球多区域部署。

### 信息来源

实际研究时列出官网、新闻稿、财报/报告、招聘页面、LinkedIn、可信媒体、应用商店，以及被采用的微信公众号/搜狗微信搜索结果链接。
