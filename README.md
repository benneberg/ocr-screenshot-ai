# 📸 SnapOCR — Intelligent OCR Workflow Automation

**Version:** 1.0.0  
**License:** MIT  
**Author:** Lukas Benneberg

A powerful **mobile-first web application** that combines OCR text extraction with AI-powered workflow automation. Upload images, extract text, and automate intelligent "read → understand → act" processes without writing code.

---

## ✨ Features

### 🔍 **OCR Extraction Layer**
- Upload images via drag-and-drop or file picker
- Extract text from screenshots, documents, error messages, and logs
- Powered by [Tesseract.js v5](https://github.com/naptha/tesseract.js) for client-side OCR
- Real-time progress tracking during text extraction
- Support for various image formats (PNG, JPG, JPEG, etc.)

### 🤖 **AI Reasoning Layer**
- Integrate with [Groq Fast Inference API](https://groq.com/) for lightning-fast AI analysis
- Automatically analyze extracted text for patterns, insights, and actions
- Choose from multiple AI models (Llama, Mixtral, Gemma)
- Customizable system prompts to guide AI behavior
- Adjustable temperature and max tokens for precise control

### ⚙️ **Workflow Automation**
- Create visual IF/THEN automation rules without coding
- **Condition Types:**
  - Text Contains
  - Text Does Not Contain
  - Text Equals
  - Text is Empty
- **Action Types:**
  - Summarize Text
  - Classify Content
  - Extract Key Information
  - Suggest Actions
  - Log Results
- Enable/disable workflows on the fly
- Chain multiple workflows together
- Custom prompts per workflow for specialized behavior

### 🎛️ **Settings & Configuration**
- Secure local storage of API keys (no backend required)
- Auto-fetch available AI models from Groq API
- Visual model selection interface
- Temperature control (0-2 scale)
- Max tokens configuration
- Customizable system prompt templates
- Real-time configuration preview

### 📱 **Mobile-First Design**
- Responsive Bootstrap 5 interface
- Modern dark theme with glassmorphism effects
- Touch-friendly drag-and-drop
- Collapsible navigation
- Works seamlessly on desktop, tablet, and mobile

---

## 🚀 Quick Start

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- [Groq API key](https://console.groq.com/) (free tier available)

### Installation

1. **Download the HTML file**
   ```bash
   # Save the SnapOCR HTML file to your computer
   ```

2. **Open in browser**
   ```bash
   # Simply double-click the HTML file
   # OR serve with any local server
   python -m http.server 8000
   ```

3. **Configure API**
   - Click ⚙️ **Settings** in the navigation
   - Enter your Groq API key
   - Click **Save API Key**
   - Click **Test Connection** to verify
   - Click **Fetch Available Models** to load AI models

4. **Start using**
   - Go to 🏠 **Home**
   - Upload an image with text
   - Click **Extract Text (OCR)**
   - Click **Analyze with AI**

---

## 📖 How to Use

### Basic Workflow

1. **Upload Image**
   - Drag and drop an image onto the upload zone
   - Or click to browse and select a file
   - Preview appears with a clear button

2. **Extract Text**
   - Click **Extract Text (OCR)**
   - Watch the progress bar as Tesseract processes
   - Extracted text displays in the text panel

3. **AI Analysis**
   - Click **Analyze with AI** to get intelligent insights
   - View results in the analysis panel
   - Any active workflows automatically execute

### Creating Workflows

1. **Navigate to Workflows**
   - Click 🔄 **Workflows** in the navigation
   - Fill in the workflow creation form

2. **Configure Workflow**
   - **Name:** Give your workflow a descriptive name
   - **Condition:** Choose when the workflow should trigger
   - **Condition Value:** Specify the text to match (if applicable)
   - **Action:** Select what the AI should do
   - **Custom Prompt:** (Optional) Override default AI instructions

3. **Example Workflows**
   
   **Error Detection:**
   ```
   Name: System Error Handler
   Condition: Text Contains
   Value: "error"
   Action: Suggest Actions
   Prompt: Analyze this error and suggest troubleshooting steps
   ```

   **Provisioning Code Extractor:**
   ```
   Name: Code Extractor
   Condition: Text Contains
   Value: "code"
   Action: Extract Key Info
   Prompt: Extract any provisioning codes or keys from this text
   ```

   **Log Classifier:**
   ```
   Name: Log Type Classifier
   Condition: Text is Not Empty
   Action: Classify Content
   Prompt: Classify this log: console, device, software, or system
   ```

4. **Manage Workflows**
   - Toggle workflows on/off with the pause button
   - Delete workflows with the trash button
   - View execution logs in the test section

---

## 🎯 Use Cases

### Digital Signage Support Teams
- Extract error codes from device screenshots
- Get AI-generated explanations in plain language
- Receive troubleshooting steps automatically
- Classify error types (hardware, network, software)

### Provisioning & Configuration
- Detect provisioning keys from screenshots
- Validate code formats automatically
- Extract configuration parameters
- Document setup processes

### Log Analysis
- Extract logs from screenshots or photos
- Automatically summarize long log outputs
- Identify critical errors or warnings
- Classify log types and sources

### Document Processing
- Extract text from scanned documents
- Summarize key points automatically
- Identify document types
- Extract structured data (dates, names, numbers)

### Quality Assurance
- Screenshot error messages during testing
- Automatically log and categorize bugs
- Generate bug report summaries
- Track error patterns

---

## 🏗️ Architecture

### Modular Design

The application follows a clean, modular architecture with six core modules:

```
├── settings.js      → API keys, preferences, localStorage
├── ocr.js          → Tesseract.js integration, image processing
├── llm.js          → Groq API communication, AI reasoning
├── workflow.js     → Condition evaluation, action execution
├── ui.js           → DOM manipulation, visual updates
└── main.js         → Application bootstrap, event handlers
```

### Data Flow

```
Image Upload → OCR Extraction → Text Analysis → Workflow Execution → Results Display
                                        ↓
                                  Groq API (AI Reasoning)
```

### Storage

All data is stored locally in the browser:
- API keys (localStorage)
- Workflow definitions (localStorage)
- User preferences (localStorage)
- No server required, fully client-side

---

## 🔧 Technical Stack

- **Frontend:** Vanilla JavaScript (ES6+), HTML5, CSS3
- **UI Framework:** Bootstrap 5 (mobile-first responsive design)
- **OCR Engine:** Tesseract.js v5 (client-side text extraction)
- **AI Provider:** Groq Fast Inference API
- **Icons:** Font Awesome 6
- **Storage:** Browser localStorage

---

## ⚙️ Configuration Options

### AI Model Parameters

- **Temperature** (0-2): Controls randomness
  - 0 = Deterministic, focused
  - 1 = Balanced
  - 2 = Creative, varied

- **Max Tokens** (1-8192): Maximum response length
  - 512 = Short responses
  - 1024 = Medium (default)
  - 2048+ = Long, detailed responses

- **System Prompt**: Global instruction template
  - Defines AI's role and behavior
  - Applied to all analyses unless overridden
  - Customizable per workflow

### Workflow Conditions

| Condition | Description | Example |
|-----------|-------------|---------|
| Contains | Text includes substring | "error", "warning" |
| Not Contains | Text excludes substring | "success" |
| Equals | Exact text match | "404 Not Found" |
| Empty | No text extracted | (no value needed) |

### Workflow Actions

| Action | Description | Use Case |
|--------|-------------|----------|
| Summarize | Condense text | Long documents, logs |
| Classify | Categorize content | Error types, log levels |
| Extract | Pull key information | Codes, dates, names |
| Suggest | Recommend next steps | Troubleshooting, fixes |
| Log | Record result | Audit trail, history |

---

## 🔐 Security & Privacy

- **No Backend:** All processing happens in your browser
- **Local Storage Only:** API keys stored locally, never transmitted
- **No Data Collection:** Zero telemetry or tracking
- **API Communication:** Only with Groq API (user-configured)
- **Client-Side OCR:** Images never leave your device

---

## 🚧 Troubleshooting

### OCR Not Working
- Ensure image has clear, readable text
- Try images with higher resolution
- Check browser console for errors
- Verify Tesseract.js loaded correctly

### AI Analysis Fails
- Verify API key is saved in Settings
- Click "Test Connection" to check API status
- Ensure you have API credits/quota
- Check browser console for error messages

### Workflows Not Executing
- Confirm workflow is enabled (not paused)
- Verify condition matches extracted text
- Check workflow execution log for errors
- Ensure API key is configured

### Performance Issues
- Large images may take longer to process
- Reduce max tokens if responses are slow
- Consider using faster AI models
- Clear browser cache if sluggish

---

## 🔮 Future Enhancements

### Planned Features
- [ ] Multi-language OCR support (beyond English)
- [ ] PDF document processing
- [ ] Batch processing (multiple images)
- [ ] Export/import workflow templates
- [ ] Webhook integrations (Slack, Discord, Jira)
- [ ] IndexedDB for persistent history
- [ ] Cloud sync for workflows
- [ ] Team collaboration features
- [ ] Custom JavaScript actions per workflow
- [ ] Advanced chaining with conditional branching

### Integration Ideas
- ServiceNow ticket creation
- Jira issue logging
- Email notifications
- Database logging
- External API calls
- Custom dashboard views

---

## 📚 AI Terms Glossary

- **OCR:** Optical Character Recognition - extracts text from images
- **LLM:** Large Language Model - AI that understands and generates text
- **Prompt:** Instructions given to the AI
- **Temperature:** Controls randomness (0=focused, 2=creative)
- **Tokens:** Word-pieces used by LLMs (limits response length)
- **Workflow:** Automated sequence of conditions and actions
- **Inference:** The process of AI generating a response
- **System Prompt:** Global instructions that guide AI behavior

---

## 🤝 Contributing

Contributions are welcome! This is a single-file application, making it easy to fork and modify.

### How to Contribute
1. Fork the repository
2. Make your changes
3. Test thoroughly
4. Submit a pull request

### Ideas for Contributions
- New workflow templates
- UI/UX improvements
- Performance optimizations
- Additional AI providers
- Documentation improvements
- Bug fixes

---

## 📄 License

This project is licensed under the **MIT License**.

```
MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 🙏 Acknowledgments

- [Tesseract.js](https://github.com/naptha/tesseract.js) - OCR engine
- [Groq](https://groq.com/) - Fast AI inference
- [Bootstrap](https://getbootstrap.com/) - UI framework
- [Font Awesome](https://fontawesome.com/) - Icons

---

## 📞 Support

For issues, questions, or feature requests:
- Open an issue on GitHub
- Check the troubleshooting section
- Review the Groq API documentation

---

## 🌟 Why SnapOCR?

- **Zero Infrastructure:** No backend, no database, no deployment
- **Instant Setup:** Download and run in seconds
- **Full Control:** Customize everything, own your data
- **Extensible:** Modular architecture for easy enhancements
- **Educational:** Learn OCR, AI, and automation concepts
- **Practical:** Solve real-world problems immediately

---

**Built with passion for intelligent automation, and because I needed this tool**

*Transform screenshots into insights, automatically.*
