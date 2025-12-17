# Daasity Data Analyst - Tailored Behavioral Interview Answers

## 1. Tell me about a time you identified and resolved data quality issues across multiple systems

### STAR Answer (Tailored for Daasity)

**Situation:**
"At my previous role supporting an e-commerce company, I was responsible for creating a unified customer analytics dashboard that pulled data from three systems: Shopify for online sales, a legacy POS system for retail stores, and Mailchimp for email marketing. The executive team needed accurate customer lifetime value (CLV) calculations to make budget allocation decisions between online and retail channels—similar to how Daasity clients need unified views across their omnichannel operations."

**Task:**
"I was tasked with ensuring data accuracy across all three sources, but I quickly discovered significant discrepancies. Customer counts varied by 15% between systems, purchase histories didn't match, and email engagement data wasn't properly linked to transactions."

**Action:**

*Discovery Phase:*
- "I conducted data profiling on each system, documenting field definitions, data formats, and update frequencies"
- "Created a data quality scorecard tracking error rates, completeness, and consistency across sources"

*Specific Issues Identified:*
1. **Customer ID Mismatch**: Shopify used email as primary key, POS used phone numbers, Mailchimp used subscriber IDs—no universal identifier
2. **Duplicate Records**: Same customer appeared 2-3 times with variations like 'John Smith' vs 'J. Smith' vs 'Jonathan Smith'
3. **Timing Lag**: POS data synced daily at midnight, but Shopify was real-time, causing same-day purchase discrepancies
4. **Missing Data**: 32% of Shopify customers had no email in system, breaking the Mailchimp link

*Solutions Implemented:*
1. **Master Customer ID**: Built a fuzzy matching algorithm using email + phone + name similarity (Levenshtein distance) to create unified customer records
2. **Data Enrichment Pipeline**: Created Python script to fill missing emails by:
   - Pulling from order history metadata
   - Matching against Mailchimp records
   - Flagging accounts needing manual review (reduced missing emails from 32% to 8%)
3. **Synchronization Schedule**: Implemented timestamp-based reconciliation that accounted for the POS delay
4. **Validation Rules**: Set up automated checks comparing daily record counts and flagging anomalies >5%
5. **Data Dictionary**: Documented all transformation rules and field mappings so stakeholders understood how metrics were calculated

**Result:**
- "Reduced data discrepancies from 15% to under 2%"
- "Enabled accurate CLV calculations that revealed retail customers actually had 23% higher lifetime value than online-only customers—counter to previous assumptions"
- "This insight led to reallocation of $85K marketing budget toward retail partnerships"
- "The data quality framework I built became the template for integrating two additional data sources later that year"
- "Saved the analytics team 12 hours per week previously spent manually reconciling data"

**Why This Matters for Daasity:**
"I understand that at Daasity, ensuring data quality across 300+ data sources is critical. Clients are making major business decisions based on the unified data, so the accuracy and reliability I demonstrated would directly translate to maintaining client trust and driving actionable insights—just like in your wellness supplement case study where discovering the 12-day shipping delay was only possible because the data pipeline was reliable."

---

## 2. Describe a dashboard you built that had significant impact on business decisions

### STAR Answer (Tailored for Daasity)

**Situation:**
"At [Company], I worked with a subscription-based consumer goods brand—similar to Daasity's wellness supplement client in your case study. They were experiencing declining subscription retention but leadership was making decisions based on lagging indicators from monthly static reports. They couldn't identify problems until weeks after they started."

**Task:**
"I was asked to create a real-time subscription health dashboard that would help the retention team proactively identify at-risk subscribers and take action before cancellations occurred."

**What Made It Effective:**

**1. Started with Decision-Making, Not Data Dumps**

*Discovery Phase:*
- "I interviewed the retention manager, customer success team, and CMO to understand: What decisions do you need to make? What would change your actions?"
- Identified 3 critical decisions:
  1. Which subscribers to contact this week for retention outreach?
  2. Is our new onboarding flow improving retention?
  3. Which products/cohorts need intervention?

**2. Dashboard Design Principles**

*Top Section - Executive Summary (The "So What"):*
- Current overall retention rate vs. target (with trend arrow)
- Month-over-month churn rate change
- Estimated revenue at risk this month
- Top 3 actionable insights (auto-generated based on data)

*Middle Section - Cohort Analysis (The Deep Dive):*
- Retention curves by acquisition month (visual similar to your wellness case study showing single-product vs. multi-product customers)
- Churn rate by order number (revealing the dangerous orders 2-3 pattern)
- Customer segmentation: new (0-30 days), growing (30-90 days), established (90+ days)

*Bottom Section - Actionable Lists:*
- "At-Risk This Week" - subscribers showing warning signals (reduced engagement, missed order, usage drop)
- "Win-Back Opportunities" - recently churned customers in 30-day window
- "Upsell Ready" - single-product customers likely to accept cross-sell

**3. Key Features That Drove Adoption**

*Automated Insights:*
- Built logic that automatically flagged patterns like:
  - "Cohort from March showing 12% higher churn than average—investigate onboarding changes"
  - "Subscribers who skip 2nd order have 68% churn rate—target this group"

*Predictive Scoring:*
- Created "health score" (0-100) for each subscriber based on:
  - Days since last order
  - Engagement with emails (opens/clicks)
  - Customer support ticket history
  - Product mix (single vs. multi-product)
- Scores updated daily

*Interactivity:*
- Filters for product line, acquisition channel, subscription length
- Drill-down capability: click cohort → see individual customers
- "Export to CRM" button to push at-risk lists directly to Salesforce

*Mobile-Responsive:*
- Retention team could check on phones during customer calls

**4. Data Quality Foundation**
- Added "Last Updated" timestamps on every metric
- Built in data validation checks with alerts for anomalies
- Cross-referenced with billing system weekly to ensure accuracy

**5. Training & Adoption Strategy**
- Ran two 30-minute training sessions with retention team
- Created one-page "Quick Start Guide" with key questions the dashboard answered
- Scheduled daily automated email at 8 AM with "Today's Top 10 At-Risk Customers"
- Held weekly office hours for first month to address questions

**Result:**

*Immediate Impact:*
- "Within 60 days, the retention team was using it daily for prioritization"
- "Identified a cohort from specific Facebook campaign with 45% churn rate (vs. 22% average)—led to pausing that campaign, saving $15K/month in wasted acquisition spend"
- "Discovered subscribers who purchased 3+ products had 71% higher retention—drove new bundling strategy"

*Three Months Later:*
- "Overall subscription retention improved from 67% to 79%"
- "Saved an estimated $127K in annual revenue that would have been lost to churn"
- "Reduced average time-to-intervention from 14 days (when problems were noticed) to 3 days (proactive outreach)"
- "Customer success team efficiency improved 35%—they stopped wasting time on healthy customers and focused on at-risk ones"

*Long-term Impact:*
- "Dashboard became the template for product team's usage analytics dashboard"
- "CFO cited improved retention metrics in board meetings"
- "The health scoring model was adopted by sales team for lead scoring"

**Why This Matters for Daasity:**
"This experience directly aligns with Daasity's mission. I built a dashboard that didn't just show data—it drove decisions and revenue impact. The cohort analysis approach I used mirrors your wellness supplement case study methodology. I understand that Daasity clients need dashboards that are both analytically rigorous and actionable for non-technical stakeholders. The combination of predictive scoring, automated insights, and clean design is exactly what I'd bring to building client dashboards at Daasity."

---

## 3. Describe your experience integrating data between CRM and other systems

### STAR Answer (Tailored for Daasity)

**Situation:**
"At [Company], I worked with a consumer brand selling through multiple channels—Shopify for DTC, Amazon for marketplace, and they'd just expanded into Target stores. This multi-channel scenario mirrors Daasity's typical client profile. They needed to integrate Salesforce (CRM), Shopify, Amazon Seller Central, and a retail syndication data provider to create a unified view of customer interactions and sales performance."

**Task:**
"My role was to design and implement the integration architecture that would allow the sales and customer success teams to see complete customer journeys across all channels, similar to how Daasity provides that unified view for brands."

**Action:**

**Phase 1: Discovery & Architecture Design**
- "Mapped data flows and established 'system of record' for each data entity:
  - Customer contact info → Salesforce (source of truth)
  - Online transactions → Shopify/Amazon
  - Retail sales → Syndication provider
  - Customer support history → Zendesk → sync to Salesforce"

**Phase 2: Technical Implementation**

*Built Three-Tier Integration:*

1. **Real-Time Sync (Critical Data)**:
   - Customer contact updates: Salesforce ↔ Shopify (bidirectional via APIs)
   - Order notifications: Shopify/Amazon → Salesforce (within 5 minutes)
   - Used Salesforce REST API with webhook triggers

2. **Hourly Batch (Important Data)**:
   - Amazon sales data (API rate limits required batching)
   - Customer support ticket status updates
   - Built Python ETL pipeline with error handling and retry logic

3. **Daily Aggregation (Reporting Data)**:
   - Retail syndication data (only updated daily by provider)
   - Historical analytics and trend data
   - Scheduled via cron jobs to run at 2 AM

**Challenges Overcome:**

**Challenge 1: Data Schema Mismatches**
- *Problem*: Customer IDs formatted differently across platforms
  - Salesforce: 18-character alphanumeric
  - Shopify: numeric customer ID
  - Amazon: no persistent customer ID (order-based)
  - Retail data: aggregated (no individual customer level)

- *Solution*:
  - Created master customer mapping table in PostgreSQL
  - Used email as universal key where available
  - For Amazon (no customer ID), matched orders by: email + order date + product + amount
  - Built fuzzy matching for name/address variations
  - Achieved 94% match rate; 6% flagged for manual review

**Challenge 2: Handling Amazon's Lack of Customer Data**
- *Problem*: Amazon doesn't provide customer contact info due to privacy policies
- *Solution*:
  - Focused on product-level insights instead: "Product X sold Y units on Amazon with Z return rate"
  - Created aggregate view: "Customers who buy on both Shopify and Amazon have 2.3x higher LTV"
  - Built logic to identify likely same customer based on: shipping address patterns, purchase timing, product preferences

**Challenge 3: Retail Syndication Data Format**
- *Problem*: Nielsen/IRI data came as weekly CSV files with different SKU naming conventions than internal systems
- *Solution*:
  - Built product mapping table linking retail SKUs to internal product IDs
  - Created automated ETL script (Python + Pandas) to:
    - Parse CSV files
    - Standardize SKU formats
    - Aggregate by week/store/region
    - Load into data warehouse
  - Added validation checks: total units sold should match invoice data ±2%

**Challenge 4: API Rate Limits & Throttling**
- *Problem*: Shopify limited to 2 requests/second; Amazon to 1 request/second
- *Solution*:
  - Implemented queueing system with exponential backoff
  - Prioritized real-time sync for critical data (orders, customer updates)
  - Batched less-critical calls during off-peak hours
  - Added monitoring dashboard showing API usage vs. limits

**Challenge 5: Data Conflicts & "Last Write Wins"**
- *Problem*: Customer updates contact info in Shopify, but old address still in Salesforce—which is correct?
- *Solution*:
  - Implemented timestamp-based conflict resolution
  - Added "last_updated" field to every record
  - Created audit log tracking all changes with source system
  - Built dashboard for data stewards to review conflicts manually (flagged ~30 per week)
  - Established business rules: "Most recent update wins, unless marked as 'verified' in Salesforce"

**Challenge 6: Testing Without Breaking Production**
- *Problem*: Couldn't test integration logic on live customer data
- *Solution*:
  - Created sandbox environments mirroring production
  - Developed automated test suite (Python pytest):
    - Unit tests for transformation functions
    - Integration tests with sample data
    - Reconciliation scripts comparing record counts and totals
  - Ran parallel processing for 2 weeks: old system + new system, compared outputs
  - Only switched to new system after 99.8% match rate

**Phase 3: Monitoring & Error Handling**
- "Built comprehensive monitoring dashboard showing:
  - Sync status by data source (green/yellow/red)
  - Records processed last 24 hours
  - Error rate and failure patterns
  - Data freshness indicators
  - API usage vs. rate limits"

- "Set up automated alerts:
  - Slack notification if sync fails 3x in row
  - Email to data team if error rate >1%
  - PagerDuty for critical failures (e.g., Salesforce API down)"

**Result:**

*Immediate Impact:*
- "Reduced manual data entry by 18 hours per week across sales team"
- "Improved data accuracy from 76% to 97% (measured via audit sampling)"
- "Sales reps could see complete customer context during calls—online orders, retail purchases, support history—all in one place"

*Business Decisions Enabled:*
- "Discovered that customers who purchased both online and in retail had 3.1x higher LTV—led to new omnichannel loyalty program"
- "Marketing could now properly attribute retail sales to digital campaigns (previously impossible)—revealed $230K in retail revenue driven by Instagram ads"
- "Identified top 50 'whale' customers generating 28% of revenue—customer success team built VIP program around them"

*Long-term Value:*
- "Integration framework handled adding 2 more data sources later (Target's retail portal, Klaviyo for email)"
- "Became foundation for customer 360 view used across entire company"
- "Reduced time to onboard new data source from 6 weeks to 2 weeks due to modular design"

**Why This Matters for Daasity:**
"This experience directly prepares me for Daasity's environment. I understand the complexity of unifying disparate data sources—especially the unique challenges of retail syndication data and marketplace platforms like Amazon. The integration approach I built mirrors Daasity's architecture: pre-built connectors for standard sources, custom solutions for unique cases, and robust data quality monitoring. I know that when a Daasity client says 'our Amazon data doesn't match Shopify,' I can diagnose whether it's a data quality issue, timing lag, or business logic problem—and build the solution."

---

## 4. Tell me about a time you uncovered an important insight through data analysis

### STAR Answer (Based on Daasity's Wellness Case Study Framework)

**Situation:**
"At [Company], I was supporting a beauty subscription brand selling skincare products—similar to Daasity's wellness supplement client. The CMO was concerned because they were spending heavily on influencer marketing ($40K/month), but subscription retention was declining from 72% to 58% over 4 months. Leadership assumed they needed to spend more on acquisition to make up for churn."

**Task:**
"I was asked to analyze what was driving churn and whether increased marketing spend was the right solution."

**Action:**

**Phase 1: Initial Hypothesis & Data Gathering**
- "I started with the conventional wisdom: 'We're attracting the wrong customers through influencer marketing'"
- Pulled data from:
  - Shopify (subscription orders, cancellations)
  - Customer support tickets
  - Email engagement (Klaviyo)
  - Product ratings and reviews
  - Shipping fulfillment logs

**Phase 2: Segmentation & Cohort Analysis**
- "I segmented churned customers by:
  - Acquisition channel (Instagram, TikTok, Google, referral)
  - Product mix (single vs. bundle subscribers)
  - Subscription tier (basic, premium, luxury)
  - Order frequency

**Phase 3: The Discovery Process** *(Mirroring Daasity's wellness case study methodology)*

*Initial Findings (Expected):*
- "Influencer-acquired customers did churn slightly faster (62% vs. 58% overall)"
- "Customers contacting support frequently seemed to churn more"

*But Then I Noticed Something Unusual:*
- "I created a timeline analysis of churn patterns and discovered:
  - **68% of cancellations happened between orders 2-3** (exactly like Daasity's case study!)
  - Churned customers had *decreased* engagement 30 days before canceling:
    - Email open rates dropped from 42% to 11%
    - Product usage (tracked via app) fell 67%
    - Support tickets dropped to zero (not increased!)
  - Average time from first order to cancellation: 47 days"

**The "Aha" Moment - The Unexpected Insight:**

*What Everyone Assumed:*
"Leadership thought bad influencer marketing was bringing in wrong customers"

*What the Data Actually Showed:*
"The problem wasn't acquisition—it was a post-purchase engagement gap. Customers were excited at first order, but then went silent. I discovered:"

1. **Product Mismatch at Order 2**:
   - 73% of churned customers received wrong product recommendation in their 2nd box
   - The quiz they took at signup asked about "skin concerns," but the product selection algorithm ignored 2 of the 5 concerns
   - Example: Customer wants "anti-aging + hydration" → gets anti-aging serum but no moisturizer → disappointed → disengages

2. **The Silent Churn Pattern**:
   - Created behavioral segments:
   
   **Engaged Subscribers (40% of base):**
   - Month 1: 100% active
   - Month 3: 89% active
   - Month 6: 81% active
   
   **"Silent Churners" (60% of base):**
   - Month 1: 100% active
   - Month 3: 43% active (massive drop!)
   - Month 6: 22% active

3. **The Shipping Delay Amplifier**:
   - Discovered that "silent churners" experienced average 9-day shipping delay on 2nd order
   - Similar to Daasity's 12-day delay finding
   - This killed trust early in the relationship

4. **Cross-Sell Opportunity Missed**:
   - Customers who purchased 2+ product types (cleanser + serum, or serum + moisturizer) had 2.8x higher retention
   - But only 18% of customers ever bought multiple product types
   - The subscription model didn't encourage exploration

**Phase 4: Validation & Deeper Analysis**
- "I validated findings by:
  - Running regression analysis: product match quality score correlated -0.68 with churn (strong!)
  - Interviewed 15 churned customers: 12 mentioned 'product wasn't right for me'
  - A/B tested quiz algorithm with 200 customers: new version had 34% better satisfaction scores"

**My Recommendations** *(Mirroring Daasity's actionable framework)*:

**1. Immediate Fix: Improve Product Matching Algorithm**
- Rebuilt quiz logic to weight all 5 skin concerns equally
- Added follow-up email after order 1: "How was the product? Let's adjust your profile"
- Expected impact: Reduce mismatches from 73% to <30%

**2. Engagement Campaign: Bridge the Order 2-3 Gap**
- Created "30-Day Skin Journey" email series:
  - Day 10: Education on how to use products
  - Day 20: "How's your skin feeling?" check-in
  - Day 25: Exclusive tip from dermatologist
  - Day 35: Preview of next month's product
- Target: Keep customers engaged during danger window

**3. Solve Shipping Delays**
- Worked with operations to identify bottleneck: order 2 products weren't pre-stocked
- Solution: Predictive inventory based on order 1 preferences
- Reduced delay from 9 days to 4 days

**4. Enable Product Exploration**
- Added "Swap" feature: customers could swap one product before shipping
- Created "Discovery Bundle" discount: 15% off when adding 2nd product type
- Gamified with "Try 3 product types, earn free full-size product"

**5. Predictive Churn Model**
- Built health scoring algorithm tracking:
  - Email engagement
  - App usage
  - Product rating (if provided)
  - Time since last interaction
- Triggered automated "We miss you" outreach at 14 days no engagement

**Result:**

*Three Months Later:*
- "Overall subscription retention recovered from 58% to 76%"
- "Product match satisfaction increased from 61% to 87%"
- "Silent churner segment decreased from 60% of base to 31%"
- "Average shipping time for order 2 reduced from 9 days to 3.8 days"
- "Cross-sell adoption (customers with 2+ product types) increased from 18% to 41%"

*Business Impact:*
- "Avoided $65K/month in unnecessary influencer marketing spend (they were ready to double it)"
- "Increased customer lifetime value by 38%"
- "Saved equivalent of acquiring 890 new customers/month through retention improvement"
- "Annual revenue impact: ~$470K from higher retention + expanded product mix"

*Strategic Shift:*
- "CMO changed strategy from 'acquire more customers' to 'delight existing customers'"
- "Marketing budget reallocated: 60% acquisition → 40% acquisition / 60% retention"
- "The churn analysis framework became standard for monitoring all product lines"

**Why This Matters for Daasity:**
"This analysis follows the exact methodology from Daasity's wellness supplement case study: cohort analysis revealing the order 2-3 churn danger zone, discovering silent churners vs. engaged customers, identifying operational issues like shipping delays, and creating multi-faceted solutions. I understand that Daasity clients need analysts who can find the 'hidden story' in the data—not just report what's obvious. The ability to connect behavioral patterns, operational issues, and business outcomes is exactly what drives ROI for consumer brands."

---

## 5. Tell me about working with sales/customer success teams to support their data needs

### STAR Answer (Tailored for Daasity Client Success Model)

**Situation:**
"At [Company], I worked with a customer success team managing 200+ subscription brand clients—a structure similar to how Daasity's customer success team serves consumer brands. The CS team was struggling because they had data scattered across multiple systems and no consistent way to identify which clients needed attention."

**Understanding Their Needs:**
"I started by shadowing 3 customer success managers for a week to understand their daily workflow. I discovered:
- They spent 2 hours every morning manually pulling data from Salesforce, usage logs, support tickets, and billing
- They couldn't identify which clients were at risk until they'd already complained or churned
- Each CSM had their own Excel spreadsheet with different metrics
- No way to prioritize their outreach—they'd just contact whoever responded to their last email"

**Task:**
"My role was to build a data solution that would help CS proactively manage accounts and increase client retention."

**Action:**

**Phase 1: Collaborative Solution Design**
- "I held working sessions with CS team to understand: 'If you could see 3 things about a client, what would they be?'"
- Emerged with priority needs:
  1. **Client Health Score**: Is this client happy and getting value?
  2. **Usage Trends**: Are they using the platform more or less over time?
  3. **Prioritized Task List**: Who should I contact today?

**Phase 2: Built Client Health Dashboard**

*Created Three-Tier Client Segmentation:*

**Green (Healthy) - 65% of clients:**
- High platform usage (>20 logins/month)
- Low support tickets
- Contract renewal >90 days away
- Action: Quarterly check-in only

**Yellow (Watch) - 25% of clients:**
- Declining usage (down >30% from baseline)
- Multiple support tickets
- No recent feature adoption
- Action: Monthly proactive outreach

**Red (At-Risk) - 10% of clients:**
- <5 logins in last 30 days
- Support ticket closed unresolved
- Contract renewal in <60 days
- Action: Immediate intervention required

*Automated Daily "Top 10 Clients to Contact" List:*
- Sent to each CSM at 8 AM with context:
  - "Client X: Usage dropped 65% last week, ticket #4521 unresolved, contract expires in 45 days"
  - "Client Y: Power user, renewal in 30 days, strong upsell candidate"

**Phase 3: Built Usage Analytics for Client Conversations**

*Created Client-Specific "Value Realization" Reports:*
- How much time/money saved using platform
- Features they're underutilizing
- Comparison to similar companies
- Example: "You're only using 4 of 12 features—companies like yours see 40% more value when they adopt inventory analytics"

**Challenges Overcome:**

**Challenge 1: CSMs Resisted "Data-Driven" Approach**
- *Problem*: Veteran CSMs said "I know my clients better than a dashboard"
- *Solution*:
  - Ran pilot with 2 CSMs who were open to trying it
  - After 60 days, their clients had 15% higher satisfaction scores and 22% lower churn risk
  - Data convinced the skeptics—full rollout followed

**Challenge 2: Data Quality Issues**
- *Problem*: 40% of usage data was unreliable due to logging bugs
- *Solution*:
  - Worked with engineering to fix tracking
  - In interim, combined usage data with email engagement + support tickets as proxy
  - Added "Data confidence" indicator: high/medium/low

**Challenge 3: Information Overload**
- *Problem*: First version had 30 metrics—CSMs said "too much, can't process"
- *Solution*:
  - Simplified to 5 core metrics based on their feedback
  - Added "expand for details" for power users
  - Focus on actionable insights, not data dumps

**Phase 4: Training & Adoption**
- "Ran 1-hour training sessions for each CSM pod"
- "Created quick-reference guide: 'What to say when dashboard shows X'"
- "Weekly office hours for first month to address questions"
- "Built Slack integration: daily alert of at-risk clients posted to #customer-success channel"

**Result:**

*Team Productivity:*
- "Reduced morning data prep time from 2 hours to 15 minutes per CSM"
- "CSMs could manage 25% more clients effectively (from 40 to 50 accounts each)"
- "Proactive outreach increased from 30% of conversations to 75%"

*Business Impact:*
- "Client churn decreased from 18% to 11% over 6 months"
- "Net Revenue Retention improved from 95% to 108% (expansion revenue from upsells)"
- "Client satisfaction scores increased from 7.2 to 8.6 (out of 10)"
- "Identified $340K in expansion revenue opportunities through underutilized feature analysis"

*Relationship Impact:*
- "CS team now comes to me with data questions proactively"
- "I became embedded in their weekly team meetings as analytics partner"
- "Built trust—they saw I was solving their problems, not forcing tools on them"
- "One CSM told me: 'This dashboard helped me save 3 clients I would have lost—that's $120K annual revenue'"

*Long-Term Value:*
- "The health scoring model was adopted by sales team for lead scoring"
- "Framework expanded to support marketing team's campaign performance tracking"
- "Client health score became KPI tracked in executive dashboards"

**Why This Matters for Daasity:**
"This experience directly prepares me for working with Daasity's customer success team and clients. I understand that data analysts at Daasity wear two hats: (1) Internal partner helping CS team serve clients better, and (2) Client-facing advisor helping brands interpret their data. The collaborative approach I used—listening first, iterating based on feedback, focusing on actionable insights—is exactly what's needed when working with consumer brands who may not be data experts but need to make data-driven decisions quickly."

---

## 6. Handling Conflicting Priorities (Daasity Context)

### STAR Answer

**Situation:**
"During my previous role, I was supporting multiple client deliverables simultaneously. In the same week, I had: (1) A major client—a $30M DTC brand—needed urgent churn analysis for their board presentation in 3 days, (2) Another client needed campaign attribution analysis to decide on a $150K Q4 marketing budget allocation by end of week, and (3) My scheduled project to build a custom inventory forecasting model for a third client had a deadline in 5 days that their operations team was depending on to make Q1 purchasing decisions."

**The Challenge:**
"All three were genuinely urgent with real business impact. The board presentation would influence investor confidence, the marketing budget decision had a hard deadline (campaigns needed to launch Monday), and the inventory model affected $500K in purchase orders. I couldn't deliver all three at full quality simultaneously."

**Action:**

**Step 1: Assess & Clarify Urgency**
- "I immediately scheduled 15-minute calls with each client to understand:
  - What's the true deadline vs. requested deadline?
  - What's the minimum viable deliverable?
  - What's the business impact if we miss it?
  - Can anyone else help or are they blocked on me?"

*Findings:*
- **Board presentation client**: Meeting was firm, but only needed 5 key churn metrics, not the full 30-slide deck initially requested
- **Marketing attribution client**: Budget decision could flex 2 days if I provided preliminary analysis in 24 hours
- **Inventory forecasting client**: Model could be phased—basic version by deadline, advanced scenario planning the following week

**Step 2: Prioritize Based on Framework**
"I ranked based on:
1. Revenue/business impact
2. True deadline flexibility
3. Dependencies—who else is blocked by my work?"

*My Prioritization:*
1. **Marketing attribution** (#1—$150K decision, hard deadline, affects Q4 revenue)
2. **Board presentation** (#2—investor relations, but slightly flexible on scope)
3. **Inventory model** (#3—could deliver in phases)

**Step 3: Negotiate & Communicate Transparently**
- Called each client with my assessment:
  - **Board presentation client**: "I can deliver the 5 critical churn metrics your board cares about by deadline, but the detailed segmentation analysis will come 2 days after the meeting. Would that work?"
    - Client: "Perfect—I actually only have 10 minutes to present anyway"
  
  - **Marketing attribution client**: "I'll prioritize your analysis and get you preliminary findings by tomorrow morning so you can start planning. Final detailed report with confidence intervals will come in 48 hours."
    - Client: "That works—I need the directional answer tomorrow, details can come after"
  
  - **Inventory forecasting client**: "I'll deliver the core forecasting model on schedule, but the advanced scenario planning features (best-case/worst-case simulations) will come the following week. The core model will still let you make purchasing decisions."
    - Client: "Okay, as long as we have baseline forecast by Friday"

**Step 4: Execute with Updates**
- **Day 1 (Wednesday)**: Worked late to finish preliminary marketing attribution—delivered by 9 AM Thursday
- **Day 2 (Thursday)**: Built core 5 metrics for board presentation—delivered by EOD
- **Day 3 (Friday)**: Finished core inventory forecasting model—delivered on time
- **Throughout**: Sent daily updates to all three clients on progress

*When I Hit a Snag:*
- Discovered data quality issue in attribution model that would delay it 4 hours
- Immediately notified client: "Found an issue with Google Analytics data—I can either deliver in