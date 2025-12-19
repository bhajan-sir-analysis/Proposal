BrightData Job Lead Scraping & Verification System

Technical Proposal (Detailed)

1. Project Understanding

This project aims to build a reliable, scalable job-lead discovery and verification system that integrates directly with your existing AI-powered job application platform.

The system will:

Discover jobs from multiple job boards

Normalize job data into a fixed schema

Enrich company information

Find and verify HR / career-related emails

Sync clean, verified data into your application via API

This proposal strictly follows the workflow shared in your document.

2. Overall Architecture

Data Sources

Bright Data APIs (LinkedIn, Indeed, Glassdoor, Wellfound, Foundit, Remote job boards)

OpenWebNinja JSearch API (optional / fallback, if preferred)

Processing Layers

Job discovery & normalization

Company & website enrichment

Email discovery & verification

Data validation & filtering

API sync to your job platform

3. Phase 1 – Job Discovery & Normalization
Job Boards Supported

LinkedIn

Indeed

Glassdoor

Wellfound

Foundit

Remote-only job boards

Other job boards as required

Output Schema (Row Job Data)

{

  "sr_no": "internal_unique_id",
  
  "source": "linkedin / indeed / glassdoor",
  
  "job_id": "",
  
  "job_title": "",
  
  "job_location": "",
  
  "job_description_html": "",
  
  "job_description_text": "",
  
  "job_industry": "",
  
  "job_url": "",
  
  "job_apply_url": "",
  
  "job_posted_date": "",
  
  "job_expire_date": "",
  
  "employment_type": "",
  
  "salary_info": ""
}


Jobs are filtered based on:

Job titles (UX, UI, Product Design roles)

Keywords (Senior / Remote / Designer variations)

Location (India, USA, Europe, APAC)

Work preference (Remote / Hybrid / Onsite)

Posted date (Last 24h, 3 days, 7 days, 30 days)

4. Phase 2 – Company & Contact Enrichment

For each job:

Website Discovery

If company website is missing:

Website is discovered via search & metadata matching

Verified domain is attached to job record

Email Discovery Priority Logic

HR / Career page email (highest priority)

Official company email

Founder / decision-maker email (only if required)

If HR or career email is verified, no further emails are collected.

5. Phase 3 – Email Verification

All discovered emails are verified

Disposable / risky emails are excluded

Already verified emails from APIs are skipped

Only verified emails are sent to the app

This reduces bounce risk and keeps outreach clean.

6. Data Transfer to Your Application

Two data streams are supported:

Raw Job Rows
→ Used for AI processing, ranking, or enrichment

Verified Job Records
→ Ready for outreach or application workflows

Data is synced using your provided endpoint APIs.

7. Pricing Model (Clear & Transparent)
One-Time Setup

End-to-end workflow design

Bright Data configuration

Email discovery & verification logic

API sync & documentation

₹900 (one-time)

Managed Scraping (Single Batch Jobs)
Volume (single task)	Fee
1,000 jobs	₹600
5,000 jobs	₹2,500
10,000 jobs	₹4,500

Single batch means one continuous job run
(not split into multiple smaller tasks)

Usage Costs (Important)

Bright Data / OpenWebNinja usage is paid directly by client

Billing stays fully under your account

Complete transparency on consumption

8. Ownership & Transparency

Client owns all API keys

Client owns all scraped & verified data

No data is reused or resold

Full documentation provided for scaling or modifying rules

9. Notes on Email & Website Availability

Some domains or email servers may:

Block incoming connections

Temporarily fail validation

Use strict security rules

In such cases:

Alternate verified emails are attempted

Records are flagged clearly

No unverified data is pushed blindly

10. Next Steps

Confirm:

Job boards to prioritize

Target countries

Initial batch size

Share:

API endpoint details

Preferred schedule (daily / weekly)

Workflow setup begins immediately after confirmation

Closing

This system is designed for long-term scalability, not just scraping.
It aligns perfectly with AI-driven job discovery and outreach platforms.
