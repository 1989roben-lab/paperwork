# Paperwork Routing

Use this file to decide which paperwork reference to load.

## Default Context

- Company context: MongoDB.
- Default output: Chinese followed by English for every generated field.
- Default audience: manager, leader, internal approver, or cross-functional stakeholder.
- Default tone: concise, specific, professional, and low-hype.

## Supported Routes

### MongoDB New Workload

Load `mongodb-new-workload.md` when the request includes any of:

- `New Workload`
- `workload`
- `NARR`
- `close date`
- `close win`
- `Application Overview`
- `Discovery Notes`
- `Use Case`
- `Next Steps`
- `Why Anything`
- `Why MongoDB`
- `Why Now`
- customer name plus workload description plus estimated annual amount
- a request to create internal workload submission language

### Research Company

Load `research-company.md` when the request includes any of:

- `Research Company`
- `research company`
- `客户研究`
- `研究客户`
- `研究公司`
- `Marketing lead`
- `lead qualification`
- `account prep`
- `公司背景`
- `业务简介`
- `客户网址`
- `公司人数`
- `员工规模`
- `人数趋势`
- `营收趋势`
- `业务趋势`
- `海外业务`
- `全球业务`
- `近期新闻`
- `WeChat news`
- `微信公众号新闻`
- `公众号近期动态`
- `客户公众号`
- `微信新闻`
- a customer or company name plus a request to understand the business, employee size, revenue trend, overseas presence, recent news, or sales call talking points

## Future Routes

Add new references as the user introduces new real paperwork cases. Use these suggested route names unless the user chooses a different naming convention:

- `expense-justification.md`: expense, reimbursement, travel, procurement, exception request, business justification.
- `project-summary.md`: project summary, launch summary, executive update, decision summary, risk and tradeoff writeup.
- `performance-self-review.md`: self review, promotion, impact summary, performance narrative, manager feedback.
- `customer-follow-up.md`: customer meeting summary, follow-up note, next-step recap, account planning language.

## Ambiguity Handling

If more than one route fits, choose the route with the most explicit field names. If the user asks to research a company and create a New Workload, load `research-company.md` first, then `mongodb-new-workload.md`. If no route fits, ask for:

1. the paperwork type or target system,
2. the reader or approver,
3. the required fields or template.

Ask only for information that materially changes the output. If the user has provided enough context to draft a useful version, draft first and list assumptions.
