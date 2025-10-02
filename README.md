Here’s the updated `README.md` with the **new workflow templates**, **automatic workflow execution**, and **mock DISE provisioning action** included:

---

# 📸 SnapOCR — AI Screenshot Helper

**Author:** Lukas Benneberg
**Date:** 2025-09-27
**License:** [MIT](LICENSE)

A lightweight **mobile-first web app** to extract text from screenshots and use AI to classify, explain, and suggest next steps.

Designed for technical teams working with digital signage devices (e.g., Samsung Tizen) but flexible enough for any workflow.

---

## Features

* **OCR (Optical Character Recognition)**

  * Upload screenshots (error messages, provisioning keys, logs).
  * Extract plain text with [Tesseract.js](https://github.com/naptha/tesseract.js).

* **AI Integration (Groq API)**

  * Explain text, classify its type (error, key, log, config, media text, etc.).
  * Suggest next steps or fixes.
  * Automatically execute workflows defined in the current project after OCR.
  * Powered by [Groq’s fast inference API](https://groq.com/).

* **Settings Panel**

  * Store API key in LocalStorage (no backend).
  * Choose AI model per action or workflow step.
  * Adjust temperature and max tokens.
  * Add a system prompt for custom behavior.

* **Custom Actions (CTA Buttons)**

  * Define your own AI prompts as buttons.
  * Fully editable (inline editing, delete, reorder).
  * Group actions by **Projects**.
  * Create multi-step **Workflows**, with each step feeding its output into the next.
  * Optionally trigger custom JS actions (e.g., send provisioning codes to a service).

* **Prebuilt Workflow Templates**

  * “Screenshot Management” → identifies provisioning codes, logs, media text, or other.
  * “Error Log Analysis” → extracts and explains errors with suggested fixes.
  * “Translate & Summarize” → summarizes and translates extracted text.
  * “Provisioning Code Validator” → detects and validates DISE, OurApp, or SignageOS codes.
  * Templates can be added to any project and customized.

* **Mobile-first UX**

  * Responsive layout.
  * Collapsible settings panel.
  * Copy-to-clipboard buttons for outputs.

---

## Technologies Used

* **Frontend:** HTML5, CSS3, JavaScript (no frameworks, single-page app).
* **OCR:** [Tesseract.js](https://github.com/naptha/tesseract.js) for client-side text extraction.
* **AI/LLM:** [Groq API](https://console.groq.com/) for fast large language model inference.
* **Storage:** LocalStorage for persisting API keys, settings, projects, and custom actions.

---

## AI Terms (for beginners)

* **OCR (Optical Character Recognition):** Extracts text from images.
* **LLM (Large Language Model):** AI that understands and generates text.
* **Prompt:** Instructions given to the AI.
* **Temperature:** Controls randomness (lower = focused, higher = creative).
* **Tokens:** Word-pieces used by LLMs (limit controls response length).
* **Workflow:** Sequence of prompts where each step builds on the previous one.
* **Template:** Prebuilt multi-step workflow that can be added to projects.

---

## 📖 How to Use

1. Open the app in a browser.
2. Go to ⚙️ Settings:

   * Enter your **Groq API key**.
   * Load available models.
   * Adjust temperature and max tokens if needed.
3. Upload a screenshot (e.g., an error message from a Tizen device).
4. Click **Extract Text** → see raw OCR output.

   * If a project is selected, all its workflows/actions automatically run on the extracted text.
5. Click a **CTA button** (or workflow) to manually trigger AI analysis.
6. Copy results to clipboard if needed.

---

## Example Use Cases

* **Digital signage support teams:**

  * Extract error codes from screenshots.
  * Get AI-generated plain-language explanations.
  * Suggest troubleshooting steps.
  * Automatically run workflows after OCR extraction.

* **Provisioning key handling:**

  * Detect provisioning keys (DISE, OurApp, SignageOS).
  * Automatically validate or send DISE codes to a service (mock API example).
  * Explain usage or next steps.

* **Log analysis:**

  * Extract logs from screenshots.
  * Summarize or classify them automatically.
  * Identify log type: console, device, software, or messages.

* **Custom prototyping:**

  * Build AI-powered tools by chaining workflows.
  * Example: *Extract → Summarize → Translate → Suggest Action*.

---

## 🔮 Future Improvements (optional roadmap)

* Cloud storage for projects (sync across devices).
* Team collaboration (share CTA/workflows).
* Multi-language OCR (currently only English).
* Integration with ticketing systems (Jira, ServiceNow).
* Export workflows as JSON/YAML for sharing.
* More prebuilt workflow templates for common use cases.
* Optional automatic JS triggers per workflow step for custom actions (e.g., API calls).

---

## Why This Is Good

* **Lightweight:** No backend required.
* **Flexible:** Users can create their own prompts, workflows, and templates.
* **Automated:** Automatically run actions/workflows after OCR.
* **Educational:** Shows how OCR + LLMs + local prototyping can solve real problems.
* **Scalable:** Can grow into a full AI-powered assistant for support teams.

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

This now clearly documents:

* **Workflow templates** and how to use them.
* **Automatic workflow execution after OCR extraction.**
* **Optional automatic actions** like the DISE provisioning example.

---
