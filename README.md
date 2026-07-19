# ScraperAPI Free Trial Complete Guide: Step-by-Step from Signup to Your First 5,000 Credits — Credit Multipliers, Plan Tiers, Real Testing Tips, and Verified Discount Codes Explained

If you've ever tried to scrape a website at scale, you already know the pain. You write a clean little Python script, fire off a hundred requests, and somewhere around request number twelve your IP gets rate-limited, a CAPTCHA wall pops up, or Cloudflare quietly sends you to a "verifying you're human" page that never finishes verifying. So you start rotating proxies. Then you start solving CAPTCHAs. Then you start running headless browsers. And before long, the simple data-gathering project you started on a Tuesday has eaten an entire week of engineering time.

That gap — between "I just want the data" and "I now operate a fragile proxy empire" — is exactly where ScraperAPI lives. And the good news is that you don't have to commit to a paid plan to find out if it actually works for your targets. The **scraperapi free trial** hands you 5,000 API credits, runs for seven days, and doesn't ask for a credit card. That's enough runway to point it at your real scraping targets and watch the numbers come back, not just poke at a sample page.

This guide walks through everything you actually need to know before, during, and after that trial: what you get, how to set it up, why those 5,000 credits can disappear faster than you'd expect, how each paid plan compares when the trial ends, what real users say, and the discount codes that actually work at checkout.

## Why the Free Trial Is the Most Important Part of Evaluating ScraperAPI

Here's something most reviews gloss over: ScraperAPI's pricing page lists clean round numbers — 100,000 credits on Hobby, 1,000,000 on Startup, 3,000,000 on Business — and those numbers are technically accurate. But the number of *actual requests* you get out of those credits depends on what you're scraping. A plain blog post costs 1 credit. An Amazon product page costs 5. A Google SERP costs 25. LinkedIn costs 30. Add JavaScript rendering or premium proxies and the per-request cost climbs again, in ways that aren't always intuitive.

This is why the trial matters more than it sounds. The 5,000 credits aren't a marketing freebie — they're the only reliable way to find out what your real per-request cost looks like against your specific targets. Run the trial against your actual use case, watch the dashboard, and you'll know which plan to pick before you've spent a dollar. Skip the trial, eyeball the pricing page, and you're guessing.

👉 [Start your free trial — 5,000 credits, no credit card required](https://www.scraperapi.com/?fp_ref=coupons)

## What You Actually Get with the ScraperAPI Free Trial

The trial is straightforward and genuinely useful for evaluation purposes.

- **5,000 API credits**, granted the moment you create an account
- **7-day duration**, starting from signup
- **No credit card required** at signup
- **5 concurrent threads**, matching the free plan's concurrency limit
- Access to **all core features**: proxy rotation across 40M+ IPs in 50+ countries, automatic CAPTCHA solving, JavaScript rendering, structured data endpoints for Amazon/Google/Walmart/eBay/Redfin, custom headers, sessions, automatic retries
- Full access to the **dashboard**, including the Domain Cost Estimator that tells you exactly how many credits a given URL will burn before you scrape it

After the 7-day trial expires, your account drops down to the permanent free tier: 1,000 credits per month with 5 concurrent connections, refreshed automatically each month. That's enough to keep small projects running indefinitely without paying anything, but it's not enough for production-scale work.

The trial credits are the same credits you'd buy on a paid plan — there are no feature gates or "trial-only" limitations. If a feature works during the trial, it works the same way on Hobby, Startup, and beyond.

## Step-by-Step: How to Sign Up and Activate Your Free Trial

The signup flow is one of the genuinely smooth parts of ScraperAPI. Most people are up and running in under five minutes.

1. **Head to the signup page** through the promotional link. The trial activates automatically when you create your account — there's no separate "claim trial" step or promo code you need to enter.
2. **Create your account** with an email and password. No credit card prompt at this stage.
3. **Grab your API key** from the dashboard. It's displayed prominently on the overview page the moment you log in.
4. **Test your first request** by replacing your existing HTTP request URL with ScraperAPI's endpoint, passing your API key as a parameter. A minimal Python example looks like this:

   python
   import requests

   API_KEY = "your_api_key_here"
   url = "https://example.com"
   response = requests.get(
       f"http://api.scraperapi.com?api_key={API_KEY}&url={url}"
   )
   print(response.status_code, response.text[:200])
   

5. **Check the Domain Cost Estimator** in the dashboard before running batch jobs. Paste your target URL and the tool tells you how many credits each request will consume, including any domain multipliers and feature flags.
6. **Watch your usage** in the analytics view. The dashboard shows credits consumed, average latency, success rates, and concurrent thread usage. Trial credits don't roll over, so anything you don't use disappears at the end of day seven.

The official SDKs (Python, Node, PHP, Ruby, Java) are available if you'd rather not build the URL yourself, but the raw HTTP endpoint works fine for most use cases and keeps dependencies minimal.

## The Credit System Decoded: Why 5,000 Credits Isn't Always 5,000 Requests

This is the part that catches almost everyone off guard, and it's the single most important thing to understand during your trial.

### Domain-Based Pricing (Automatic — You Don't Choose This)

| **Domain Category** | **Base Credits per Request** | **Examples** |
| --- | --- | --- |
| Normal websites | 1 | Blogs, news sites, simple HTML |
| E-commerce | 5 | Amazon, eBay, Walmart |
| SERP (search engines) | 25 | Google, Bing |
| Social media | 30 | LinkedIn |

These multipliers are applied automatically the moment ScraperAPI detects the domain. You don't opt in. A request to amazon.com always costs 5 credits minimum, regardless of which plan you're on.

### Feature-Flag Multipliers (Optional — You Choose These)

| **Parameter** | **Extra Credits** | **Notes** |
| --- | --- | --- |
| `render=true` (JS rendering) | +10 | All plans |
| `premium=true` (premium proxy) | +10 | All plans |
| `screenshot=true` | +10 | All plans |
| `ultra_premium=true` | +30 | Paid plans only |
| Anti-bot bypass (Cloudflare, DataDome, PerimeterX) | +10 each | Auto-detected |
| `premium=true` + `render=true` combined | **+25 total** | NOT +20 |
| `ultra_premium=true` + `render=true` combined | **+75 total** | NOT +40 |

That last row is the one that bites people. Combining features doesn't add linearly — premium proxy plus JavaScript rendering costs 25 credits, not the 20 you'd expect from adding 10 + 10. Ultra-premium plus rendering costs 75, nearly double the 40 you'd expect from 30 + 10. This non-linear stacking is documented but not prominently advertised, and it's the primary reason trial credits can vanish faster than the headline number suggests.

### What 5,000 Trial Credits Actually Get You

- **5,000 requests** to plain HTML blogs or news sites
- **1,000 requests** to Amazon product pages (5 credits each)
- **200 requests** to Google SERPs (25 credits each)
- **~166 requests** to LinkedIn (30 credits each)
- **~66 requests** to a hard-protected site using ultra-premium proxy plus JavaScript rendering (75 credits each)

Run those numbers against your real workload during the trial. If you're scraping 1,000 Amazon products a day with rendering enabled (15 credits each = 15,000 credits/day), the 5,000-credit trial gets you through about a third of one day's work — which tells you immediately that you need at least the Business tier or higher. If you're scraping 50 blog posts a week, the trial alone might cover you for a month and the free tier might be enough permanently.

## Full Plan Comparison: Every Tier on the Official Pricing Page

When the trial ends and you're ready to commit, here's the complete current lineup. All paid plans include JavaScript rendering, premium residential and mobile IPs, advanced anti-bot bypass, structured data endpoints, DataPipeline access, custom sessions, automatic retries, unlimited bandwidth, and a 99.9% uptime guarantee. The differences between tiers come down to volume, concurrency, geotargeting scope, and whether pay-as-you-go overflow is available.

| **Plan** | **Monthly Price** | **Annual (per month, 10% off)** | **API Credits / Month** | **Concurrent Threads** | **Geotargeting** | **Get Started** |
| --- | --- | --- | --- | --- | --- | --- |
| Free Trial | $0 (7 days) | — | 5,000 (one-time) | 5 | — |  [Start free trial](https://www.scraperapi.com/?fp_ref=coupons) |
| Free Plan | $0 | — | 1,000 | 5 | — |  [Sign up](https://www.scraperapi.com/?fp_ref=coupons) |
| Hobby | $49 | $44.10 | 100,000 | 20 | US & EU only |  [Get Hobby](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | $149 | $134.10 | 1,000,000 | 50 | US & EU only |  [Get Startup](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business | $299 | $269.10 | 3,000,000 | 100 | Global (50+ countries) |  [Get Business](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling | $475 | $427.50 | 5,000,000 | 200 | Global |  [Get Scaling](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Professional | $975 | $877.50 | 10,500,000 | 300 | Global |  [Get Professional](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Advanced | $1,975 | $1,777.50 | 21,500,000 | 500 | Global |  [Get Advanced](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Enterprise | Custom | Custom | 22,000,000+ | 500+ | Global |  [Contact sales](https://www.scraperapi.com/?fp_ref=coupons) |

A few non-obvious things worth noting from this table:

- **Geotargeting is gated by tier.** Hobby and Startup are limited to US and EU proxies only. If your project needs country-level targeting in Asia, Latin America, or anywhere else, you need at least Business.
- **Pay-as-you-go overflow is only available from Scaling upward.** On Hobby, Startup, and Business, exhausting your credits mid-cycle means either upgrading to the next tier or waiting for renewal. Scaling and above let you keep scraping at a fixed per-credit rate.
- **Credits don't roll over.** Whatever you don't use resets at renewal. Match plan size to your real monthly volume rather than overbuying "just in case."
- **Analytics history is tiered.** Hobby and Startup are capped at 30 days of dashboard history. Business and above get unlimited analytics retention.

## After the Trial: Which Plan Should You Actually Pick?

The trial exists to answer this question for your specific use case, but here's the general guidance based on the credit math above.

**Pick Hobby ($49/mo)** if you're running a personal project, a side hustle, or a prototype — checking competitor prices on a handful of products, monitoring a few dozen pages, building a proof of concept. 100,000 credits sounds like a lot until you remember Amazon costs 5x and Google costs 25x; for plain unprotected pages, though, this plan genuinely covers meaningful ground.

**Pick Startup ($149/mo)** if you've outgrown casual scraping and need consistent volume — a small SaaS product, an agency running scraping jobs for a few clients, regular price monitoring across a moderate product catalog. The 10x credit jump from Hobby to Startup makes this the sweet spot for most professional use cases, though you're still capped at US/EU geotargeting.

**Pick Business ($299/mo)** if you need global geotargeting, unlimited analytics history, or you're running production-grade infrastructure other parts of your business depend on. This is also the first tier where the jump in concurrent threads (100) starts to matter for larger parallel jobs.

**Pick Scaling ($475/mo) and above** if you're past the "which plan" question and into "how do we keep this predictable at high volume" territory. These tiers add pay-as-you-go overflow billing so you're never hard-capped mid-month, plus priority support starting at Professional.

**Enterprise** is custom-quoted. If you're running tens of millions of requests monthly and want a dedicated Slack channel with the support team, reach out to sales directly.

👉 [Compare plans side by side on the official pricing page](https://www.scraperapi.com/pricing/?fp_ref=coupons)

## What Real Users Say About ScraperAPI

Independent review aggregation paints a fairly consistent picture across the major platforms.

| **Platform** | **Rating** | **Reviews** |
| --- | --- | --- |
| Trustpilot | 4.5/5 | 43 |
| G2 | 4.4/5 | 16 |
| Capterra | 4.6/5 | 62 |

Capterra's sub-ratings are particularly telling: Ease of Use sits at 4.9/5, Customer Service at 4.6/5, Features at 4.5/5, and Value for Money at 4.5/5. The recurring praise points are the same across most platforms — clean documentation, a genuinely simple integration (drop it into existing code as a proxy replacement), and responsive support that typically replies within 24 hours.

> "ScraperAPI was extremely easy to use out of the box. We are able to get around website blocks easily."

That's a typical Trustpilot review. The pattern repeats: people describe swapping out a single line of code — replacing their direct HTTP request with the ScraperAPI endpoint — and being done.

On the critical side, the most common complaint isn't about reliability. It's about the credit math being less intuitive than the headline number suggests, especially once you start mixing in rendering and premium-proxy parameters on harder targets. A few users on Reddit have reported being quoted one price and billed at a higher rate after domain multipliers kicked in. Independent benchmarking from third parties has also noted that performance varies significantly by target: ScraperAPI tends to perform very well on mainstream e-commerce and SERP targets (Amazon, Google, Zillow, Walmart), but less consistently on sites with aggressive, frequently-changing anti-bot systems like Instagram, Twitter/X, or Booking.com.

The takeaway from user sentiment: ScraperAPI is well-regarded for ease of initial setup and performs reliably on popular, well-supported targets. The complaints cluster around pricing surprises and the credit multiplier system — both of which the free trial is specifically designed to surface before you commit.

## Tips to Squeeze Maximum Value Out of Your Free Trial

The trial is short and the credits are finite. Here's how to use them well.

1. **Test against your real targets, not synthetic examples.** The trial only tells you something useful if you point it at the actual websites you plan to scrape in production. Skip the "let me try it on example.com" step.
2. **Use the Domain Cost Estimator before every batch.** The dashboard tool tells you exactly how many credits a URL will cost before you scrape it. Run your full target list through it once and you'll have a realistic credit budget before burning anything.
3. **Disable premium features unless the target requires them.** ScraperAPI does *not* auto-enable `render=true`, `premium=true`, or `ultra_premium=true`. But domain-based pricing *is* automatic — Amazon always costs 5, Google always costs 25. Know which of your requests genuinely need rendering or premium proxies and which don't.
4. **Track success rates per domain.** If a target returns below a 90% success rate during the trial, plan for retries or a fallback provider. Don't assume a 100% success rate on a few test requests means the same rate at scale.
5. **Don't burn credits on retry loops.** ScraperAPI already does automatic retries internally. If you're also retrying on your end, you're paying twice for the same failures.
6. **Document your real per-request cost.** After the trial, divide your total credits consumed by your successful request count. That number — not the headline plan credit count — is what you should use to size your paid plan.
7. **Check the analytics dashboard daily during the trial.** There are no proactive usage alerts; you have to look. The dashboard shows average latency, domains scraped, and concurrency metrics. Build intuition for how fast credits burn on your specific targets.

## Verified Discount Codes That Actually Work

Most coupon sites for ScraperAPI are filled with unverified, auto-generated, or simply non-functional codes. Let's be honest about what's actually confirmed.

- **START10** — 10% off your first month on any paid plan. Verified across multiple independent sources. Apply it at checkout after choosing your plan.
- **Annual billing** — automatic 10% discount on every plan when you choose annual billing instead of monthly. No code needed; it's applied at checkout. Stack this with START10 on your first renewal for compound savings.
- **ANWAR10** and **ARCHANA** — both reported as 10%-off codes on independent forums. Less consistently verified than START10, but worth trying if START10 doesn't activate for you.

The 10% annual discount is the most reliable savings mechanism and applies to every renewal, not just the first month. If you're confident the service fits your use case after the trial, annual billing is the better long-term play.

👉 [Claim your free trial and apply START10 at checkout for 10% off](https://www.scraperapi.com/?fp_ref=coupons)

## Common Questions About the ScraperAPI Free Trial

**Is the free trial really free?**
Yes. No credit card is required at signup, and you won't be auto-charged when the trial ends. Your account simply drops to the permanent free tier (1,000 credits/month) unless you actively choose a paid plan.

**What happens to my unused trial credits when the 7 days end?**
They disappear. Credits don't roll over on any plan, including the trial. The permanent free plan's 1,000 monthly credits are granted separately and refresh each month.

**Can I scrape Amazon and Google during the trial?**
Yes. All features are available during the trial, including structured data endpoints for Amazon, Google, Walmart, eBay, and Redfin. Just remember that Amazon costs 5 credits per request and Google SERPs cost 25, so your 5,000 credits go fast on those targets.

**Does the trial include ultra-premium proxies?**
No. Ultra-premium proxies (`ultra_premium=true`) are only available on paid plans. Premium proxies (`premium=true`) are available during the trial.

**Can I extend the trial if I need more testing time?**
The 7-day window is fixed, but you can contact ScraperAPI support through the dashboard to request additional trial credits for evaluation purposes. They're generally responsive to legitimate testing requests.

**Do failed requests consume trial credits?**
Only successful requests (HTTP 200 and 404 responses) consume credits. Failed requests — timeouts, blocks, anything outside that range — don't burn your credits. This is one of ScraperAPI's genuinely fair policies.

**Can I cancel anytime after upgrading to a paid plan?**
Yes. Cancellation is available anytime from the dashboard or by contacting support, and there's a 7-day, no-questions-asked refund policy if you're not satisfied with the service.

## The Bottom Line

The **scraperapi free trial** isn't a marketing freebie — it's the only reliable way to figure out which paid plan fits your actual workload. The 5,000 credits and 7 days are enough to point the API at your real targets, watch the dashboard, and calculate your true per-request cost before you've spent a dollar. Skip that step and you're guessing at plan size against a credit system that doesn't behave intuitively.

If your scraping targets are mostly plain HTML pages without heavy anti-bot protection, the Hobby plan at $49/month genuinely covers a lot of ground for personal projects and early-stage products. The moment Amazon, Google, LinkedIn, or Cloudflare-protected sites enter the picture, run your numbers through the credit table above first — the sticker price and the real cost per successful scrape are two different things, and the trial is what tells you which one you're actually paying.

The cleanest path forward: sign up for the trial, point it at your real targets, watch your credit consumption for a week, then decide. The free tier will keep small projects running indefinitely even if you never upgrade, and the START10 code plus annual billing will take 10% + 10% off your first paid cycle when you do.

👉 [Start your free ScraperAPI trial — 5,000 credits, 7 days, no credit card](https://www.scraperapi.com/?fp_ref=coupons)
