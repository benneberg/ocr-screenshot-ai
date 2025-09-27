# Short Reasoning Journey (Idea → Prototype → Product)

## How I Went from Idea to Working App

### Start Idea → OCR Tool
The first thought was simple:  
> “I want to extract text from screenshots of error messages on digital signage screens.”

**Solution:** Use OCR (Optical Character Recognition) with **Tesseract.js** to turn images → plain text.

---

### Enhancement → Add AI Explanation
Extracted text is often cryptic (e.g., provisioning keys, system logs).  
> “What if AI could explain what this text means and suggest next steps?”

**Solution:** Added **Groq API** integration for fast AI inference.

---

### UX Improvement → Settings Page
Needed a way to:  
- Store API key (**localStorage**)  
- Choose models, temperature, max tokens  
- Add a system prompt  

**Solution:** Added ⚙️ **Settings panel** with a modern mobile-first design.

---

### AI Guidance → Model Selection Tips
Non-expert users often don’t know which model to pick.  
**Solution:** Added short explanations near the model list to guide users  
*(e.g., `instant = quick`, `instruct = reasoning`)*.

---

### Productivity Boost → Custom Actions (CTAs)
> “We could speed up workflows if users can create buttons with their own prompts.”

**Solution:** Added **CRUD actions** (create, edit, delete, reorder) stored in **localStorage**.

---

### Scalability → Projects
To avoid clutter, actions can be grouped into **projects** (e.g., “Tizen debugging” vs. “Provisioning keys”).

---

### Power User Feature → Workflows (Chained CTAs)
> “What if I could run multiple prompts in sequence and prototype tools?”

**Solution:** Added **workflows**: multi-step prompts executed sequentially, passing outputs between steps.

---

### Final Product
A **mobile-first single-page web app** where you can:  
- Upload screenshots  
- Extract text (OCR)  
- Use AI to classify, explain, and suggest fixes  
- Create custom buttons or workflows for repeat tasks  
- Prototype AI tools without coding, just by editing prompts
