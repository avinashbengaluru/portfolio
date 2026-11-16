# Hi there, I'm Avinash Immaneni 👋

### 🤖 AI Agent & Data Systems Engineer · Open-Weight LLM Pipelines · Senior Data Scientist

Building **production AI agent systems**, **open-weight LLM & LoRA inference pipelines**, **real-time edge data architectures**, and **enterprise credit risk & governance models**.

I built **BillMiner** — an XML-to-LLM operations and **automated book keeping system** that turns **Tally Prime (a desktop Legacy ERP and book keeping system** that only speaks `XML over HTTP`) into an autonomous, AI-assisted distribution workflow without changing how bookkeepers and accountants work.

> **Core Engineering Theme:** *XML in, intelligence out.* Spend model compute only on ambiguity — route known lookups to ~25 ms edge databases, replace expensive closed APIs with **open-weight models (Gemma 4 & Gemma 2B LoRA)**, and bound every AI agent with arithmetic verification and reversible audit logs.

---

## 🚀 1. Open-Weight LLMs & Radical AI Cost Reduction

* **Production Migration from Frontier APIs to Gemma 4:** Prototyped invoice line matching and variant resolution on commercial frontier APIs, then migrated production inference to open-weight **Gemma 4** — eliminating per-document API cost spikes and rate limits while accelerating iteration speed.
* **Gemma 2B LoRA Candidate Judge (Fine-Tuning):** Engineered the training dataset and LoRA fine-tuning pipeline for a compact **Gemma 2B** model specialized in choosing the exact SKU among top-5 rule-based candidates at a fraction of standard LLM latency and cost.
* **Zero-Token Edge Offloading (~25 ms/line):** Moved high-frequency order matching and alias lookups to **Cloudflare Workers + D1 (SQLite) + KV**, resolving the majority of lines in **~25 ms at $0 model cost** and invoking LLMs strictly on novel or ambiguous strings.
* **Sub-Cent Storefront Asset Pipeline (~$0.007/image):** Built a deterministic, non-generative image standardization pipeline producing clean house-style product pages from real photos for **~$0.007 per image** (prioritizing the 85 pages that drive 70% of sales).

---

## 🧠 2. Production AI Agents & Self-Learning Loops (BillMiner)

### A. 🤖 "Rao" — Retrieval Augmented Outvoicing Agent
In-workspace AI invoicing chat agent built directly into the billing screen. Clerks paste or photograph a customer's messy order; **Rao** maps lines straight onto the live invoice, displays the customer's original words above each matched Tally item with an inline variant picker, or drafts plain-text GST-inclusive price replies without touching the active bill.

### B. 🔄 Nightly Self-Learning & Audited Catalogue-Repair Agents
* **Nightly Cloudflare Cron Learner:** Every evening, an automated job diffs raw scanned invoice text against what clerks finally posted in Tally, learning new supplier aliases and pack-size rules (guarded against text fragments, with 1-click undo).
* **Scheduled Claude Audit Routine:** An autonomous cloud agent reviews each posted bill and repairs catalogue cards through **audited, state-logged endpoints** where every edit records its exact before-and-after state.

### C. 📄 Dual-Reader Purchase Bill Scanner (92% End-to-End Accuracy)
* Runs **two readers in parallel** on multi-page supplier bills:
  1. Custom **Google Vision OCR + rule-based table layout engine** (handles tilted tables, `1.234,56` formatting, swapped qty/rate columns, and wrapped item names).
  2. **LlamaParse ("OCRia-1")**.
* **Arithmetic Decides the Winner:** A reader's lines must sum to the bill's printed taxable total. Coupled with remembered per-supplier notes (re-checked by math) and **Gemma 4** matching, **291 of 317 real supplier bills (92%)** process end-to-end (with **12/12** matching posted totals and line counts in regression testing).

### D. ⚡ Edge Seller Detect (~25 ms/line) & "Nothing Is Lost" Catalogue Engine
* **Seller Detect:** Maps WhatsApp messages (**81% top-1, 98% top-3**), Gmail enquiries (**75% top-1, 89% top-3**), and handwritten order photos to exact Tally items in **~25 ms/line** using per-item "defining words."
* **13,000-Item Catalogue Reconstruction:** Reorganized ~13,000 clerk-typed Tally item names (~9,600 sold; **3,256 never-billed dead names audited**) into **Product Families → Variants** under a strict *move-never-delete* rule, combining manufacturer catalogues, **Brave Search + LLM web research**, and a mobile staff micro-question queue (which resolved **~22% of catalogue gaps**).

---

## 🔗 3. Legacy ERP & Paisa-Exact Tax Engineering

* **Non-Disruptive Custom TDL / XML Queue:** Pulls compact XML exports (**≤500 KB per queued job**) from Tally Prime over HTTP (`:9000`) using isolated date-range variables that never disturb live billing clerks.
* **Paisa-Exact GST & GSTR-1 Reconstruction:** Calculates GST per line rounded half-up to the paisa before summing — matching Tally's internal tax engine and rebuilt **GSTR-1** returns to the exact paisa so vouchers are never rejected.

---

## 💻 Technical Stack

| Domain | Technologies & Models |
| :--- | :--- |
| **Open-Weight & Cloud AI** | **Gemma 4** (Production Matching), **Gemma 2B LoRA** (Fine-Tuning), **Claude Agents** (Scheduled Cloud Routines), **Google Cloud Vision**, **LlamaParse ("OCRia-1")**, **Brave Search API** |
| **Edge & Data Layer** | **Cloudflare Workers** (Edge APIs & Nightly Cron), **Cloudflare D1 (SQLite)**, **Cloudflare KV**, **Cloud Firestore**, **Firebase Storage** |
| **Legacy ERP & Book Keeping** | **Tally Prime Legacy ERP** (XML over HTTP `:9000`, Custom **TDL** Reports), Bidirectional XML Voucher Sync Agent, Paisa-Exact GST & GSTR-1 Engine |
| **Web & Enterprise Data** | **Next.js**, **React**, **TypeScript**, **Tailwind CSS**, **shadcn/ui**, **Python**, **PySpark**, **SQL (T-SQL, PostgreSQL, Snowflake)**, **AWS SageMaker** |

---

## 🔗 Links & Live Demos

* **BillMiner Interactive Deck:** [billbuddy-deck.vercel.app](https://billbuddy-deck.vercel.app)
* **Main Portfolio:** [avinashbengaluru.github.io/portfolio/portfolio.html](https://avinashbengaluru.github.io/portfolio/portfolio.html)
* **AI Product Case Studies:** [github.com/avinashbengaluru/ai-product-case-studies](https://github.com/avinashbengaluru/ai-product-case-studies)
* **LinkedIn:** [linkedin.com/in/avinash-immaneni-912763150](https://www.linkedin.com/in/avinash-immaneni-912763150/)
