# amazon product api pricing: what an Amazon page really costs you, with every plan and the annual totals

Most people searching "amazon product api pricing" want one thing: a real number they can plug into their budget. Here it is, using ScraperAPI as the reference point. Amazon requests on ScraperAPI cost **5 credits each**, not 1. That single detail changes every cost calculation you'll read online, because most articles compare monthly plan prices without converting them into actual Amazon pages.

On the Hobby plan ($49/month), those 100,000 credits translate into 20,000 Amazon product pages — about **$2.45 per 1,000 pages**. Pay annually and it drops to roughly $2.21 per 1,000. Whether that's cheap depends on what you're comparing against: DataForSEO's Amazon Product API charges $0.003–$0.005 per product (so $3–5 per 1,000), while Rainforest API's entry plan runs $18/month (billed annually) for only 500 credits. The rest of this article walks through every ScraperAPI plan, the credit math, and the small-print limits that decide what you'll actually pay.

> **Quick picks**
> - Testing the waters: start with the **7-day trial (5,000 credits, no credit card)**, then the free plan (1,000 credits/month) if you're still deciding.
> - Tracking a few hundred products: **Hobby, $49/month** — 20,000 Amazon pages monthly.
> - Production-scale monitoring: **Startup ($149) or Business ($299)**, which unlock country-level geotargeting.
>
> Most small and mid-size sellers land on Hobby. 👉 [Check current plan prices and start the free trial](https://www.scraperapi.com/pricing?fp_ref=coupons)

## What you're actually paying for

ScraperAPI handles the parts of Amazon scraping that eat engineering time: proxy rotation across a 40M IP pool in 50+ countries, CAPTCHA handling, and — if you use their structured endpoints — the parsing itself. Instead of fetching raw HTML and writing your own parser, you hit an endpoint like `/structured/amazon/product` with an ASIN and get back JSON: price, rating, review count, availability, best-seller rank, image URLs, even whether an A+ page exists.

Their own example response shows the level of detail: a Sony PXW-Z280 camcorder listing comes back with the price ($6,054.95), a 3.2-star rating from 3 reviews, "Only 8 left in stock - order soon.", category ranks in Electronics and Camcorders, and five image URLs. For price monitoring, competitive research, or repricing tools, that's most of what you need without writing a single XPath.

There are three Amazon-specific structured endpoints: the Product Scraper (details per ASIN), the Search Scraper (submit keywords, get ranked products back), and the Offers Scraper (track competitor promotions and discounts). Beyond the structured endpoints, you can also send regular requests to any Amazon URL and parse the HTML yourself, or use the no-code DataPipeline to monitor up to 10,000 ASINs per project and receive results via webhook.

## Every plan, side by side

Here's the complete lineup from the official pricing page, both monthly and annual billing. The annual discount is a flat 10% across all paid tiers.

| Plan | Monthly | Annual (per month) | Credits/mo | Threads | Get started |
| --- | --- | --- | --- | --- | --- |
| Free | $0 | — | 1,000 | 5 | [Sign up for the free plan](https://www.scraperapi.com/?fp_ref=coupons) |
| Hobby | $49 | $44.10 ($529.20/yr) | 100,000 | 20 | [Get Hobby at $44.10/mo annual](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Startup | $149 | $134.10 ($1,609.20/yr) | 1,000,000 | 50 | [Get Startup at $134.10/mo annual](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Business | $299 | $269.10 ($3,229.20/yr) | 3,000,000 | 100 | [Get Business at $269.10/mo annual](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Scaling | $475 | $427.50 ($5,130/yr) | 5,000,000 | 200 | [Get Scaling at $427.50/mo annual](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Professional | $975 | $877.50 ($10,530/yr) | 10,500,000 | 300 | [Get Professional at $877.50/mo annual](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Advanced | $1,975 | $1,777.50 ($21,330/yr) | 21,500,000 | 500 | [Get Advanced at $1,777.50/mo annual](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Enterprise | Custom | Custom | 22,000,000+ | 500+ | [Talk to sales about Enterprise](https://www.scraperapi.com/?fp_ref=coupons) |

All paid plans share the same feature set — JS rendering, premium residential and mobile IPs, advanced anti-bot bypassing, the structured data APIs, and DataPipeline access. What changes between tiers is volume, concurrency, geotargeting scope, and analytics history. Professional and Advanced currently carry limited-time bonus credits (+250K and +500K respectively). No end date is published for those bonuses, so treat them as a current snapshot rather than a permanent feature of the plans.

## The catch most pricing comparisons miss: Amazon costs 5 credits

This is where "amazon product api pricing" searches usually go wrong. ScraperAPI prices by *credit cost per request*, and the target site matters:

- Standard page: 1 credit
- **E-commerce (Amazon, Walmart, eBay): 5 credits**
- Google / Bing SERP: 25 credits
- LinkedIn: 30 credits

So a plan advertised as "100,000 credits" doesn't give you 100,000 Amazon pages — it gives you 20,000. Optional add-ons stack on top: JS rendering (`render=true`) adds 10 credits, premium proxies another 10, and if a request triggers bot-protection bypassing against Cloudflare or DataDome, that's 10 more. Geotargeting, sessions, device type, and auto-parsing are free.

Before committing to a plan, do the division for your own use case. If you also plan to monitor Google Shopping results (25 credits each) alongside Amazon products, a single mixed workload changes the math significantly. ScraperAPI gives you two tools to stay on top of this: every API response includes a `sa-credit-cost` header showing exactly what that request burned, and the dashboard's Domain Cost Estimator estimates the cost of any URL before you send it. You can also set a `max_cost` per scrape so a single misconfigured request can't eat your quota.

## Real cost per 1,000 Amazon pages

Dividing each plan's credit allowance by 5 gives you the actual Amazon page volume, and dividing the price by that volume gives the real unit cost:

| Plan | Amazon pages/mo | Cost per 1,000 pages (monthly billing) | Cost per 1,000 (annual billing) |
| --- | --- | --- | --- |
| Hobby | 20,000 | $2.45 | ~$2.21 |
| Startup | 200,000 | $0.75 | ~$0.67 |
| Business | 600,000 | $0.50 | ~$0.45 |
| Scaling | 1,000,000 | $0.48 | ~$0.43 |
| Professional | 2,100,000 | $0.46 | ~$0.42 |
| Advanced | 4,300,000 | $0.46 | ~$0.41 |

Two things stand out. First, the per-page price improves sharply going from Hobby to Startup — a 66% cut — then flattens out. Second, the annual discount saves real money but requires a full year upfront: $529.20 for Hobby, $1,609.20 for Startup, $3,229.20 for Business. If you're not sure your project will still exist in six months, monthly billing at a slightly higher unit cost is the safer bet.

## How this compares with other Amazon API providers

For context, here's what competitors charge — info only, since I'm not linking to them:

| Provider | Entry price | Model | Notes |
| --- | --- | --- | --- |
| ScraperAPI | $49/mo (20,000 Amazon pages) | Credits, 5/Amazon request | Free plan + 7-day trial; full suite beyond Amazon |
| DataForSEO | $0.003/product (queue), $0.005 (live) | Per product | $3,000 per 1M in queue mode; up to 1-minute turnaround |
| Rainforest API | $18/mo billed annually | Credits (~500/mo) | Amazon specialist; no perpetual free tier |
| Keepa | ~€49/mo (third-party figure) | Monthly fee + tokens | Focused on price history rather than on-demand scraping |

One wrinkle worth knowing: ScraperAPI acquired Traject Data — Rainforest API's parent company — in April 2026, and the SERP and e-commerce APIs are being folded into the same credit economy. If you were weighing Rainforest against ScraperAPI as competing options, they're now under the same roof, which makes the comparison less a choice between vendors and more a choice between billing models and interface styles.

Each option has a defensible niche. If you need price *history* charts for arbitrage decisions, Keepa's model fits better than a per-request scraper. If you're pulling millions of product records in batch and don't care about latency, DataForSEO's $0.003 queue pricing undercuts everyone. Where ScraperAPI earns its price is the combination: on-demand structured endpoints plus the general scraping API, DataPipeline scheduling, async batches of millions of requests, and geotargeted results (you can switch the Amazon TLD to get localized shipping and pricing) — all under one credit pool.

## Small-print limits that change the real price

A few rules from the billing FAQ that rarely make it into comparison articles:

- **Credits never roll over.** Every plan, including Enterprise. Unused credits from one month vanish at renewal. If your usage is spiky — a big monitoring push one month, quiet the next — this hurts more than any headline price difference.
- **What happens when you run out depends on your plan.** By default, scraping pauses until credits renew. On Hobby through Professional you can opt into auto-upgrade, which bumps you to the next tier automatically when credits run out. On Scaling and above, pay-as-you-go lets you keep scraping at a fixed per-credit rate up to a monthly spending cap you set — no plan change needed.
- **Geotargeting is limited on the cheap tiers.** Hobby and Startup are locked to US & EU locations. Country-level targeting worldwide starts at Business. If your use case needs prices from specific marketplaces outside those regions, the cheap plans won't do it.
- **Analytics history is 30 days on Hobby and Startup**, unlimited from Business up. For debugging usage patterns or auditing spend, this matters more than you'd think.
- **Concurrency overages are free.** Exceeding your thread limit returns a 429 and the request is turned away rather than queued — no surprise charges, but your job slows down.

None of these are dealbreakers, but two of them — no rollover and the US/EU geotargeting cap — are exactly the kind of thing people discover after paying for a year.

## Testing before you pay

The trial path costs nothing: a 7-day trial with 5,000 credits, no credit card required. That's 1,000 Amazon product pages or a smaller number of mixed requests — enough to verify the JSON structure fits your pipeline and measure your real credit burn per workflow. When the trial ends you can drop to the free plan (1,000 credits/month, 5 concurrent threads) and keep testing indefinitely, or jump straight to a paid tier. Need extra testing credits or a custom setup? Contact sales for a custom trial.

Because the trial requires no card, there's no billing to unwind if you walk away. 👉 [Start the 7-day free trial with 5,000 credits](https://www.scraperapi.com/signup)

A quick technical note for evaluating fit: the Python starter is as simple as it looks — pass your `api_key`, the ASIN (their docs use `B07G4J7TY5` as the example), and a `country` parameter, then parse the JSON response. If your stack can make an HTTP GET, you're integrated in an afternoon.

## FAQ

**Is there a genuinely free option?**
Yes. The free plan gives 1,000 credits monthly with 5 concurrent threads — 200 Amazon pages a month, forever, no card. It's meant for testing, not production.

**How many Amazon products can I scrape per month on each plan?**
Divide credits by 5: Hobby 20,000, Startup 200,000, Business 600,000, Scaling 1 million, Professional 2.1 million, Advanced 4.3 million. Amazon requests are billed at the e-commerce rate of 5 credits per request across the product, search, and offers use cases.

**Does JS rendering or premium proxying cost extra on Amazon product pages?**
Yes — +10 credits each, so a rendered Amazon page with premium proxies runs 25 credits instead of 5. The structured Amazon endpoint returns parsed JSON directly, and its documented example requests don't use either add-on, so you can start at the base 5-credit rate.

**What happens to unused credits?**
They expire. There's no rollover on any plan, though annual plans can renew early to receive a fresh batch.

**Is there a refund if I change my mind?**
The published guarantee is the trial itself: 7 days and 5,000 credits with no card attached, so you never enter a paid commitment to evaluate the product. No separate refund policy is published on the pricing page, which is one more reason to validate your workload during the trial before choosing annual billing.

## Which plan makes sense for you

Match the plan to your actual ASIN count and refresh frequency, and the decision mostly makes itself:

- **Monitoring under ~15,000 product pages a month** (a few hundred ASINs refreshed daily, plus headroom): Hobby at $49 does it, and annual billing takes it to $44.10.
- **Repricing or competitor tracking across thousands of ASINs with daily refreshes**: Startup. At 200,000 Amazon pages monthly, you're paying $0.75 per 1,000 pages with room to grow via auto-upgrade.
- **Production pipelines that need geotargeting beyond US/EU, longer analytics history, or pay-as-you-go headroom**: Business or Scaling.
- **Millions of requests, dedicated support, custom volumes**: that's Enterprise territory, and pricing is negotiated rather than published.

One last check before you commit: open the Domain Cost Estimator in the dashboard and run your real URL mix through it, because the difference between 5-credit and 15-credit requests is the difference between Hobby and Business. If the numbers hold up, 👉 [pick your plan and start scraping today](https://www.scraperapi.com/pricing?fp_ref=coupons).
