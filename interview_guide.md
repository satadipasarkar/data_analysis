# Daasity Data Analyst - Interview Preparation Guide

## About Daasity

**Daasity** is an omnichannel analytics platform built specifically for consumer brands.

### Core Service
They provide enterprise-level analytics without requiring data engineering expertise. The platform unifies data from eCommerce, retail sales, marketing, and inventory into a single view.

### Key Features
- Connects 300+ data sources across digital and physical retail channels
- Processes sales data across 30+ countries
- Integrates with major platforms like Shopify, NetSuite, Amazon, and retail syndicated data providers (Nielsen, Spins)
- Offers real-time analytics for sales, marketing, inventory, and promotions

### Target Market
Consumer brands selling across multiple channels (online and offline), particularly in industries like:
- Cosmetics
- Wellness
- Food & beverage
- Apparel
- Home goods

### Value Proposition
They help brands make data-driven decisions by unifying scattered data, enabling them to:
- Optimize pricing
- Reduce return rates
- Improve customer lifetime value
- Manage inventory
- Maximize marketing ROI
- All without hiring a full data engineering team

### Notable Clients
- Manscaped
- Poppi
- Thrive Causemetics
- SC Johnson

---

## Core Responsibilities as Data Analyst

### 1. Client-Facing Analytics
- Help consumer brands interpret their unified data and extract actionable insights
- Build custom reports and dashboards tailored to specific client needs
- Identify trends in sales, marketing performance, inventory, and customer behavior across channels
- Translate complex data into clear recommendations for clients' business decisions

### 2. Platform Development & Optimization
- Work on improving the analytics platform's data models and reporting capabilities
- Develop pre-built analytics templates for different industries (cosmetics, wellness, food & beverage, etc.)
- Create standardized metrics and KPIs relevant to consumer brands
- Quality assurance on data integrations and transformations

### 3. Industry Expertise
- Become an expert in retail and eCommerce analytics metrics
- Understand nuances across different sales channels (Shopify, Amazon, retail distributors)
- Analyze syndicated data from Nielsen, Spins, and other retail data providers
- Stay current on industry trends and benchmarks

### 4. Problem-Solving
Help clients identify issues like:
- Why return rates are high
- Which products drive repeat purchases
- Optimal pricing strategies
- Where marketing dollars are most effective

Conduct:
- Cohort analyses
- Customer lifetime value calculations
- Attribution modeling
- Support client success by uncovering growth opportunities in their data

### 5. Collaboration
- Work with data engineers on pipeline improvements
- Partner with customer success teams to ensure clients get value from the platform
- Potentially assist with sales demos showing analytical capabilities

**Ideal Candidate**: Someone who enjoys both technical data work and business strategy, with a focus on helping brands grow through data-driven insights.

---

## Case Study: Helping a Wellness Supplement Brand Reduce Churn

### The Client
A growing wellness supplement company selling vitamin subscriptions through Shopify, Amazon, and recently expanded into Whole Foods.

### The Problem
The CMO notices their subscription retention rate has dropped from 65% to 48% over the past 6 months. They're spending more on customer acquisition but can't figure out why people are canceling.

### How a Daasity Data Analyst Would Help

#### Step 1: Initial Discovery Call
The analyst starts by asking questions:
- When did churn start increasing?
- Any recent changes to products, pricing, or shipping?
- Which channels show the highest churn?

#### Step 2: Data Deep Dive
The analyst pulls unified data from all their channels and discovers:
- **Churn timing**: 68% of cancellations happen between orders 2-3
- **Product mix**: Customers who only buy their flagship multivitamin churn 2x faster than those who've purchased 2+ products
- **Channel insight**: Amazon subscribers have 40% higher retention than Shopify subscribers
- **Hidden pattern**: Customers who cancel had a 12-day average shipping delay on their second order

#### Step 3: The "Aha" Moment
The analyst creates a cohort analysis showing:

**Single-product customers (60% of base):**
- Month 1: 100% active
- Month 3: 52% active
- Month 6: 31% active

**Multi-product customers (40% of base):**
- Month 1: 100% active
- Month 3: 81% active
- Month 6: 73% active

#### Step 4: Actionable Recommendations
The analyst presents a strategy:

1. **Immediate fix**: Investigate the fulfillment delay causing 12-day shipping times (likely killing trust early)

2. **Cross-sell campaign**: Launch a "Complete Your Routine" email after first purchase
   - Target: Single-product customers 10 days after first order
   - Offer: 20% off complementary products
   - Expected impact: If just 25% convert to multi-product, could reduce overall churn by 8-10%

3. **Learn from Amazon**: Amazon subscribers stay longer - why?
   - Analysis shows: Amazon's "Subscribe & Save" discount is 15% vs. their Shopify 10%
   - Recommendation: Test matching the 15% discount on Shopify

4. **Retention milestone**: Create a "90-day club" reward
   - Customers who hit order 4 rarely churn (88% retention rate)
   - Offer: Special gift or exclusive product at 90 days to bridge the dangerous order 2-3 gap

#### Step 5: Measuring Success
The analyst sets up a monitoring dashboard tracking:
- Weekly churn rate by cohort
- Cross-sell campaign conversion rates
- Average shipping times
- Subscription retention curves

### Three Months Later
- Shipping issues resolved (down to 4-day average)
- Cross-sell campaign achieving 31% conversion rate
- Overall subscription retention recovered to 61%
- Customer lifetime value increased by 24%

### The ROI
The brand was spending $180k/month on acquisition. By reducing churn by 13 percentage points, they effectively "saved" the equivalent of acquiring 520 fewer customers per month (~$63k/month), while also increasing revenue from existing customers.

**This is exactly the type of high-impact work a data analyst at Daasity would do** - combining technical analysis with business strategy to solve real problems that directly impact revenue.

---

## How a Data Analyst Implements ETL at Daasity

### The Reality at Daasity

**Important Context**: Given that Daasity's value proposition is **"Enterprise Level Analytics, No Data Engineering"**, the company likely has:
- Pre-built connectors for 300+ data sources
- A team of data engineers handling the core ETL infrastructure
- Standardized data models already in place

However, a data analyst would still work on ETL in specific scenarios:

### Scenario 1: Custom Client Integration
**The Situation**: A major client (e.g., a $50M beauty brand) uses a proprietary inventory management system that's not in Daasity's 300+ connectors.

**Data Analyst Role**: Build custom connector and transformation logic for this unique data source.

### Scenario 2: Data Quality & Enrichment Pipeline
**The Situation**: Client's Shopify data is messy - product names inconsistent, missing categories, duplicates.

**Data Analyst Role**: Create data cleaning and enrichment transformations to standardize the data.

### Scenario 3: Building Aggregation Tables for Performance
**The Situation**: Clients need daily KPI dashboards, but querying raw transaction data is too slow.

**Data Analyst Role**: Design and build pre-aggregated tables and materialized views for fast dashboard performance.

### Scenario 4: Real-World ETL Monitoring Dashboard
**The Situation**: Analyst needs to monitor all ETL jobs and ensure data quality.

**Data Analyst Role**: Build monitoring dashboards to track pipeline health and data quality metrics.

---

## Key Takeaways for Data Analysts at Daasity

1. **Less infrastructure, more business logic**: You're not building Airflow DAGs from scratch, but you ARE creating the transformation logic that makes data useful

2. **Custom solutions**: When clients have unique data sources, you build the connectors

3. **Data quality guardian**: You ensure transformations maintain data integrity

4. **Performance optimization**: You create aggregate tables and materialized views for fast dashboards

5. **Documentation**: You document data lineage and transformation rules so clients understand their metrics

**The ETL work is more about smart transformations and data modeling than managing infrastructure.**