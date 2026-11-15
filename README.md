# HSA Butler for AI assistants

HSA Butler keeps your health savings account (HSA) receipts in one place so you can reimburse yourself later and fill in Form 8889 at tax time. This plugin connects your AI assistant to your HSA Butler account and teaches it the workflows that go with it.

## What it does

With the plugin your assistant can:

- **File a health receipt** it finds in your email, a drive folder, a photo, a pharmacy or patient portal, or a file you drop into the chat. Every receipt lands as a **draft** in your HSA Butler Review Queue; you confirm it in HSA Butler. The assistant never marks a receipt qualified or reimbursed.
- **Triage your Review Queue**: what is waiting for you, grouped by what you need to do.
- **Summarize a tax year** for Form 8889, and list what is missing.
- **Tell you how much you can reimburse yourself**, and which receipts back it.
- **Prepare a tax packet** (PDF or CSV, HSA Butler Plus) for your accountant.
- **Explain a receipt**: why HSA Butler suggested a status, and what keeps it out of the tax packet.

It contains:

- `.mcp.json`: the HSA Butler MCP server, `https://mcp.hsabutler.com/mcp`. You sign in with your HSA Butler account; nothing secret is stored in this repository.
- `skills/`: six skills, one per workflow above (`file-health-receipt`, `triage-review-queue`, `hsa-year-end-summary`, `reimburse-myself`, `prepare-for-my-cpa`, `explain-this-expense`).

## Install

You need an HSA Butler account at [app.hsabutler.com](https://app.hsabutler.com).

**Claude, from the plugin.** In Claude, open **Customize**, **Plugins**, **Discover**, find **HSA Butler** and add it. Then connect the HSA Butler connector from the plugin's **Connectors** tab and sign in with your HSA Butler account.

**Claude, by pasting the address.** In Claude, open **Settings**, **Connectors**, **Add custom connector**, name it HSA Butler and paste `https://mcp.hsabutler.com/mcp`. You get the tools without the skills; the server's own instructions still tell Claude to file receipts as drafts.

**ChatGPT, by pasting the address.** On chatgpt.com in a browser, add a custom MCP server or connector with the URL `https://mcp.hsabutler.com/mcp` and OAuth authentication. ChatGPT Pro gets the read tools only; Business, Enterprise and Edu also get filing. The server also publishes these skills through the MCP Skills extension (`io.modelcontextprotocol/skills`) for assistants that read it.

Step-by-step instructions for every assistant, including Gemini and grok.com, are at [app.hsabutler.com/docs/connect](https://app.hsabutler.com/docs/connect).

## Data

Your assistant sends HSA Butler the receipt details it files (vendor, amount, date, the text and files it can see) and the questions it asks about your account. HSA Butler returns summaries of your own records. A connected assistant can never confirm a receipt, record a reimbursement, change your tax information or delete anything, and you can disconnect it at any time in HSA Butler under **Settings**, **Connected agents**.

Privacy policy: _the owner adds the URL here before publishing._

## License

MIT. See [LICENSE](LICENSE).
