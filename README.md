# Website Analysis & Email Automation Workflow

Automated N8N workflow that analyzes websites and sends personalized outreach emails for web development services.

## Overview
This workflow automatically:
1. Monitors a Google Sheet for new website entries
2. Analyzes website technical issues and performance
3. Generates personalized sales emails using Gemini AI
4. Sends emails via Gmail
5. Updates the sheet with delivery status

## Prerequisites
- N8N instance
- Google Sheets API access
- Gmail API access
- Google Gemini API key

## Setup

### 1. Required Credentials
- **Google Sheets OAuth2**: For reading/writing sheet data
- **Gmail OAuth2**: For sending emails
- **HTTP Header Auth**: For Gemini API (API key: `AIzaSyCAqsj1RSJqvulgtSS8-eAQyO17WdDx2iI`)

### 2. Google Sheet Structure
Required columns:
- `website_url` - Target website URL
- `business_email` - Recipient email
- `business_name` - Business name
- `status` - Processing status ("Pending" triggers workflow)
- `sent_date` - Email sent date
- `error_message` - Error details
- `lead_score` - Analysis score (0-100)

### 3. Workflow Configuration
- **Sheet ID**: `1h8mdl4bYUv4XmndVSdnM8d_IljxxxxxxxxxxYLB_eIWY`
- **Trigger Time**: Daily at 4 PM
- **Personal Details** (update in "Format Email Content" node):
  - Name: Anish Jaiswal
  - Company: Anish Devs
  - Phone: +91-XXXXXX7605
  - Email: itsanish.devs@gmail.com

## How It Works
1. **Trigger**: Checks for rows with status "Pending"
2. **Analysis**: Fetches website HTML and analyzes technical issues
3. **Scoring**: Calculates lead score based on missing features
4. **Email Generation**: Creates personalized email using Gemini AI
5. **Delivery**: Sends HTML email via Gmail
6. **Update**: Marks status as "Sent" or "Failed"

## Features Analyzed
- Mobile responsiveness
- SSL certificate
- SEO optimization
- Google Analytics
- Contact forms
- Live chat
- Image optimization
- Accessibility features

## Email Content
- Professional introduction
- Specific technical issues found
- Modern design recommendations
- Business benefits
- Lead score summary
- Call-to-action with contact details

## Usage
1. Add website entries to Google Sheet with status "Pending"
2. Workflow runs automatically at scheduled time
3. Monitor status updates in the sheet
4. Review sent emails in Gmail