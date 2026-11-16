# 🚀 BillMiner Interactive Architecture Deck & Portfolio

An interactive **Desktop (6-slide)** and **Mobile (14-card)** presentation deck + engineering portfolio showcasing **BillMiner**: an XML-to-LLM operations platform built beside **Tally Prime**, powered by **open-weight models (Gemma 4 & Gemma 2B LoRA)**, **autonomous AI agents (Rao, Nightly Cron Learner, Claude Audit Routine)**, **dual-reader OCR**, and **Cloudflare Workers + D1 (~25 ms/line)**.

> **Theme:** *XML in, intelligence out.* Tally stays the system of record. Everything smart happens beside it using open-weight models, deterministic arithmetic checks, and edge lookups — and every result posts back to Tally as paisa-exact XML.

---

## 📌 Live Links

| Surface | URL |
| :--- | :--- |
| **Interactive Presentation Deck** | [https://billbuddy-deck.vercel.app](https://billbuddy-deck.vercel.app) |
| **Engineering Portfolio Page** | [https://avinashbengaluru.github.io/portfolio/portfolio.html](https://avinashbengaluru.github.io/portfolio/portfolio.html) |
| **Mobile 14-Card Deck** | [https://avinashbengaluru.github.io/portfolio/mobile.html](https://avinashbengaluru.github.io/portfolio/mobile.html) |

---

## 🧠 Key Highlights Covered in This Repo

1. **Open-Weight LLM Cost Reduction (`Gemma 4` + `Gemma 2B LoRA`):**
   - Replaced expensive commercial LLM calls on high-volume invoice matching with **Gemma 4** in production and built a **Gemma 2B LoRA** fine-tuning pipeline for top-5 candidate ranking.
   - Offloaded known item/alias lookups to **Cloudflare Workers + D1 (~25 ms/line)** at $0 token cost, and built a real-photo storefront pipeline at **~$0.007/image**.
2. **Autonomous AI Agents with Deterministic Guardrails:**
   - **Rao ("Retrieval Augmented Outvoicing"):** In-screen invoicing assistant that turns pasted/photographed orders into live bill lines with inline variant pickers or instant GST-inclusive price quotes.
   - **Nightly Self-Learning Loop:** Cloudflare cron diffs raw scans against posted Tally vouchers to learn supplier aliases, followed by a scheduled **Claude agent** that repairs catalogue cards via audited, reversible endpoints.
   - **Multi-Source Research Agent:** Combines manufacturer catalogues, **Brave Search + LLM verification**, and a mobile staff micro-question UI (which resolved ~22% of catalogue gaps).
3. **Dual-Reader Purchase Bill Scanner (`92%` / `291 of 317` Real Bills):**
   - Runs custom **Google Vision OCR + rule-based table layout reader** in parallel with **LlamaParse ("OCRia-1")**; arithmetic checks against the bill's printed taxable total decide the winner (**12/12** match in regression testing).
4. **Non-Disruptive Tally XML & Paisa-Exact GST:**
   - Custom TDL reports export ≤500 KB queued jobs with isolated date variables so billing clerks are never disturbed; outbound XML matches Tally's per-line half-up paisa GST rounding and reconstructed **GSTR-1** returns.

---

## 🛠️ Building the Desktop Deck

After editing any slide source (`intro-tally.html`, `why-billbuddy.html`, `architecture.html`, `tally-data-sync.html`, `ai-integration.html`, `improvements.html`), rebuild `deck.html` and `index.html`:

```bash
python build_deck.py
```
