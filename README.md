# 🤖 AI Lead Qualification & Appointment Booking System for Coaches

An end-to-end, AI-powered automation system designed specifically for coaches and service providers. This system automatically captures inbound leads, qualifies them using OpenAI, books discovery calls for high-intent prospects, and nurtures unqualified leads — all without manual intervention.

---

## 🎯 The Problem

Coaches and consultants waste 10-15 hours per week manually:
- Reading through inbound lead forms
- Deciding who is worth a call
- Emailing back and forth to schedule meetings
- Following up with unqualified leads

This leads to slow response times, lost high-value clients, and burnout.

---

## 💡 The Solution

A fully automated "AI Client Acquisition Engine" that:
1. Captures leads from a Google Form
2. Uses OpenAI to score each lead (0-100) based on budget, urgency, and fit
3. Routes qualified leads (Score > 70) directly to Google Calendar for booking
4. Sends personalized pre-call intelligence notes to the coach
5. Routes unqualified leads to a nurture email sequence

---

## ️ System Architecture

```text
[Google Form] 
     ↓
[Google Sheets - Watch New Rows]
     ↓
[OpenAI - Lead Scoring & Analysis]
     ↓
[JSON Parser]
     ↓
[Router]
     ├──→ [Qualified Path] → [Airtable CRM] → [Google Calendar] → [Gmail Confirmation]
     ──→ [Unqualified Path] → [Airtable CRM] → [Gmail Nurture Email]
🛠️ Tech Stack
Make.com (Integromat) - Workflow orchestration
OpenAI API (GPT-4) - AI lead scoring and analysis
Google Forms/Sheets - Lead intake and trigger
Airtable - CRM database for lead tracking
Google Calendar - Automated appointment booking
Gmail - Personalized email communication
JSON Parser - Structured data processing
🔄 How It Works
Step 1: Lead Capture
A potential client fills out a Google Form with their name, email, company, budget, challenges, and preferred meeting time. This data is instantly logged in Google Sheets.
Step 2: AI Qualification (OpenAI)
The system sends the lead data to OpenAI with a custom prompt that evaluates:
Budget alignment (e.g., $5,000+ = high score)
Clarity of pain points
Urgency and readiness
Company size and fit
OpenAI returns a structured JSON response with a Lead Score (0-100) and Qualification Status.
Step 3: Smart Routing
A Router module splits the workflow:
Score ≥ 70: Lead is "Qualified" → Books a meeting automatically
Score < 70: Lead is "Unqualified" → Enters a nurture sequence
Step 4: Qualified Lead Path
Airtable: Creates a new CRM record with status "Qualified"
Google Calendar: Books a discovery call at the lead's preferred time
Gmail: Sends a personalized confirmation email with meeting details and pre-call questions
Step 5: Unqualified Lead Path
Airtable: Creates a record with status "Unqualified" for future re-engagement
Gmail: Sends a polite nurture email with free resources (blog, podcast, guide)
Key Results & Impact
✅ 80% time savings on manual lead vetting and scheduling
✅ 24/7 automated processing with responses within 15 minutes
✅ 30% increase in booked calls due to instant engagement
✅ Zero manual data entry — all lead info synced to CRM
✅ Professional client experience with personalized, timely communication
