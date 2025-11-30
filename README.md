## Who is this for?

This workflow is for Product Managers, Indie Hackers, and Customer Success teams who collect feature requests but struggle to notify specific users when those features actually ship. It helps you turn old feedback into customer loyalty and potential upsells.

## What it does

This workflow creates a "Semantic Memory" of user requests. Instead of relying on exact keyword tags, it uses Vector Embeddings to understand the *meaning* of a request.

For example, if a user asks for "Night theme," and months later you release "Dark Mode," this workflow understands they are the same thing, finds that user, and drafts a personal email to them.

## How it works

1.  **Listen:** Receives new requests via **Tally Forms**, vectorizes the text using **Nomic Embed Text** (via Ollama or OpenAI), and stores them in **Supabase**.
2.  **Watch:** Monitors your Changelog (**RSS**) or waits for a manual trigger when you ship a new feature.
3.  **Match:** Performs a Vector Similarity Search in Supabase to find users who requested semantically similar features in the past.
4.  **Notify:** An **AI Agent** drafts a hyper-personalized email connecting the user's specific past request to the new feature, saving it as a **Gmail Draft** (for safety).

## Requirements

*   **Supabase Project:** You need a project with the `vector` extension enabled.
*   **AI Model:** This template is pre-configured for **Ollama (Local)** to keep it free, but works perfectly with OpenAI.
*   **Tally Forms & Gmail:** For input and output.

## Setup steps

1.  **Database Setup (Crucial):** Copy the SQL script provided in the workflow's **Red Sticky Note** and run it in your Supabase SQL Editor. This creates the necessary tables and the vector search function.
2.  **Credentials:** Connect your Supabase, Tally, and Gmail accounts.
3.  **URL Config:** Update the `HTTP Request` node with your specific Supabase Project URL.

## How to customize

*   **Change Input:** Swap the Tally node for Typeform, Intercom, or Google Sheets.
*   **Change AI:** The template includes notes on how to swap the local Ollama nodes for OpenAI nodes if you prefer cloud hosting.
*   **Change Output:** Swap Gmail for Slack, SendGrid, or HubSpot to notify your sales team instead of the user directly.

---
[Start using n8n](https://n8n.partnerlinks.io/spkrs32edelt) | [My other n8n projects here](https://n8n.io/creators/ehsan-z/)
