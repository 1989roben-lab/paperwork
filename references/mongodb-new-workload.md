# MongoDB New Workload Paperwork

Use this reference to generate MongoDB New Workload paperwork.

## Purpose

Create concise bilingual text for a new MongoDB workload submission. The user typically provides a customer, workload scenario, expected close date, and NARR.

## Required Inputs

- Customer name.
- Workload name or workload type.
- Expected close date or close win timing.
- Annual NARR amount. Treat NARR as annual estimated revenue unless the user says otherwise.

## Optional Inputs

- Application behavior.
- Data types expected to be stored in MongoDB.
- Storage, throughput, availability, or region hints.
- Competitor or current platform.
- Cloud provider or region preference.
- Business driver or urgency.

## Pricing And Sizing Rules

- For Discovery Notes, use live MongoDB Atlas official pricing internally when the user expects a sizing estimate.
- Default region for internal estimates: AWS Virginia / `us-east-1`.
- Estimate a cluster and disk configuration whose annual cost is roughly within +/-20% of the provided annual NARR, but do not show hourly rates, annualized math, price multiplication, or pricing source details in the final paperwork.
- Do not recommend a single Atlas node tier above `M60`.
- If the internal estimate would otherwise require `M80` or higher, recommend multiple `M60` shards instead. For example, use `2 M60 shards` instead of `M80`, and scale the number of M60 shards as needed for larger NARR targets.
- If the target NARR is too small or too large for a simple single-cluster estimate, state a practical recommendation such as dev/test plus production, multiple M60 shards, larger disk, backup, or scaling headroom.
- Include disk assumptions when the workload may store large volumes of player, agent, conversation, vector, telemetry, or event data.
- Do not invent exact official prices from memory. Browse or otherwise verify current official pricing before using prices.
- If live pricing cannot be accessed, provide a clearly labeled rough sizing recommendation without exact price claims.
- Final Discovery Notes should read like natural sales or SA discovery notes. Say the customer needs or is currently planning a specific Atlas configuration; do not phrase it as an algorithmic estimate derived from NARR or close date.
- Avoid openings such as `Based on the USD ... annual NARR`, `the recommended estimate is`, or similar agent-like sizing language in final Discovery Notes.
- Final Discovery Notes should include only the customer requirement, recommended configuration, concise business/technical rationale, key assumptions, and follow-up confirmations.

## Output Fields

Generate these fields in this order.

### New Workload Name

- Put a concise New Workload name at the very top before all other fields.
- Mix Chinese and English naturally when helpful.
- Keep it under 8 words.
- Do not add a language label.
- Example: `Cognosphere 智能 NPC Agent Workload`.

### Application Overview

- Chinese: about 80 Chinese characters.
- English: one complete business sentence of similar detail.
- Summarize the customer, application/workload, what it supports, and the business or user value.

### Discovery Notes

- Chinese and English.
- Mention the customer's required or currently planned Atlas configuration, region if useful, storage/scaling assumption, and business/technical rationale.
- Keep each shard at `M60` or below. Use multiple `M60` shards when more capacity is needed.
- Do not include hourly prices, annualized cost calculations, price multiplication, pricing source details, or step-by-step evaluation process.
- Do not write Discovery Notes as `Based on NARR, recommend/estimate...`. Prefer phrasing like `客户的 ... 系统需要一套生产级 MongoDB Atlas 环境，当前建议按 ... 规划` and `The customer's ... system requires a production-grade MongoDB Atlas environment. The current recommendation is to plan for ...`.
- State assumptions and follow-up confirmations clearly.

### Use Case

- Chinese: about 30 Chinese characters.
- English: about 30 words.
- Describe what data MongoDB can store for this application, such as users, profiles, agent state, conversation history, embeddings, metadata, events, logs, or configuration.

### Next Steps

- Chinese and English.
- Provide three concise follow-up steps based on the expected close date, each with an approximate date or date range.
- Work backward from the close date: qualification and sizing first, then technical/commercial confirmation, then procurement and close execution.
- Keep the total around 80 Chinese characters or 70 English words when date ranges are included.
- Focus on qualification, technical sizing, stakeholder alignment, pricing confirmation, and close plan.

### Why Anything?

Choose exactly one of:

- Maximize Competitive Advantage to Drive Growth
- Accelerate Time to Value
- Reduce Risk for Business Applications
- Lower Total Cost of Ownership

Show the selected option as the first line under the field heading, then add a brief Chinese explanation and a brief English explanation of about 20 words each.

Do not label the selected option with `Selected Option`.

For AI, NPC, or new product workloads, prefer `Accelerate Time to Value` unless the user provides a stronger reason to choose another option.

### Why MongoDB?

- Chinese and English.
- About 20 Chinese characters or 20 English words.
- Emphasize flexible document model, scalability, Atlas managed operations, search/vector capability, or developer velocity based on the case.

### Why Now?

- Chinese and English.
- Explain why the project must move now.
- Tie urgency to close date, launch timeline, customer adoption, AI/product roadmap, risk reduction, or revenue capture.

## Output Format

Use this exact field order and bilingual pattern:

```markdown
# Cognosphere 智能 NPC Agent Workload

### Application Overview

...

...

### Discovery Notes

...

...
```

Continue the same pattern for all required fields. Under each field heading, put the Chinese paragraph first and the English paragraph second. Do not use `中文:`, `English:`, `Chinese:`, `Selected Option`, or other labels.

## Missing Information

If required information is missing, ask for only the missing required item. If the user gives partial information, draft with assumptions only when the missing item is not essential.

Critical missing items:

- no customer name,
- no workload description,
- no expected close timing,
- no NARR amount.

## Example Input

Customer: Cognosphere Pte Ltd  
Workload: NPC intelligent agent workload  
Close date: 2026-10-30  
Annual NARR: USD 100,000  
Context: AI-powered NPCs need persistent player state, conversation history, agent memory, and event data.

## Example Output Style

# Cognosphere 智能 NPC Agent Workload

### Application Overview

Cognosphere 计划为游戏中的智能 NPC Agent 构建新工作负载，用于支持 NPC 的长期记忆、玩家交互上下文、实时状态更新和个性化行为生成，提升游戏角色的智能化体验与玩家沉浸感。

Cognosphere plans to build a new workload for intelligent NPC agents, supporting long-term memory, player interaction context, real-time state updates, and personalized behavior generation to improve in-game intelligence and player immersion.

### Discovery Notes

Cognosphere 的智能 NPC Agent 工作负载需要一套生产级 MongoDB Atlas 环境，当前建议按 **Atlas M60 分片集群** 规划，单个 shard 不超过 **M60**，并按生产环境预留存储和扩展空间。该配置可支持玩家状态、对话历史、Agent 记忆、事件日志和后续数据增长；上线前需进一步确认实际存储量、读写峰值、备份策略和生产区域。

Cognosphere's intelligent NPC Agent workload requires a production-grade MongoDB Atlas environment. The current recommendation is to plan for an **Atlas M60 sharded cluster**, keeping each shard at **M60** or below, with production-ready storage and scaling headroom. This setup can support player state, conversation history, agent memory, event logs, and future data growth. Before launch, the team should confirm actual storage volume, read/write peaks, backup requirements, and production region.

### Use Case

MongoDB 可存储玩家画像、NPC 状态、对话历史、Agent 记忆、事件日志与配置数据。

MongoDB can store player profiles, NPC state, conversation history, agent memory, event logs, metadata, and configuration data for intelligent gameplay.

### Next Steps

**9 月上旬**确认上线计划、数据容量和读写峰值；**9 月下旬**完成 Atlas sizing、技术方案和价格确认；**10 月中下旬**推进采购流程、stakeholder alignment，并确保 **2026 年 10 月 30 日** close。

In **early September**, confirm launch timing, data capacity, and read/write peaks. In **late September**, finalize Atlas sizing, technical architecture, and pricing. In **mid to late October**, drive procurement, stakeholder alignment, and close execution for the **October 30, 2026** target.
