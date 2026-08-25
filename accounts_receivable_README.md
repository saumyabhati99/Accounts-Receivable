# Accounts Receivable Automation

An n8n workflow that monitors invoice data in Google Sheets, identifies overdue unpaid invoices, uses Google Gemini to generate a payment reminder, and creates a Gmail draft for review before anything is sent.

## The Problem

Following up on overdue invoices is repetitive and easy to handle inconsistently. Accounts receivable teams need a reliable way to identify invoices that require attention and prepare professional reminders without manually checking every record. This workflow automates the repetitive work while keeping the final email under human control.

## How It Works

1. **Starts manually** — the workflow is triggered by clicking “Execute workflow,” making it easy to test or run on demand.
2. **Reads invoice data** — Google Sheets provides the customer and invoice information used by the workflow.
3. **Filters overdue invoices** — records are kept when the invoice status is `Unpaid` and the invoice is more than 3 days overdue.
4. **Generates the reminder with AI** — Google Gemini acts as an Accounts Receivable specialist and writes a payment reminder using the customer name, invoice ID, amount, due date, and days overdue.
5. **Adjusts the tone automatically** — reminders become more direct based on how many days the invoice is overdue: Friendly, Firm, Urgent, or Final Notice.
6. **Creates a Gmail draft** — the generated message is saved as a Gmail draft and addressed to the customer's email instead of being sent automatically.

## Tools Used

n8n · Google Sheets · Google Gemini · Gmail

## AI Email Rules

The generated reminder starts with the customer's name, includes the Invoice ID and Amount, stays under 100 words, and ends with the Accounts Receivable Team sign-off.

## Why This Matters

This workflow demonstrates a practical approach to AI-powered business automation: combine structured business data, deterministic filtering, and AI-generated communication while preserving human oversight. Instead of automatically sending sensitive payment emails, the system prepares a ready-to-review Gmail draft.

## Workflow Architecture

**Manual Trigger → Google Sheets → Filter → Google Gemini → Gmail Draft**

scheduled invoice monitoring, approval workflows, escalation rules, reporting, or additional notification channels. for later growth.
