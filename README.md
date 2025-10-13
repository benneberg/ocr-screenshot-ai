Here’s your updated README.md with all the new features:

```markdown
# 📸 SnapOCR — Intelligent Signage Operations Platform

**Version:** 2.0.0  
**License:** MIT  
**Author:** Lukas Benneberg

A powerful **intelligent automation platform** designed specifically for digital signage operations teams. Combines OCR text extraction with AI-powered workflow automation and master triage capabilities. Upload screenshots, extract text, and automate intelligent "detect → analyze → act" processes without writing code.

---

## ✨ Features

### 🔍 **OCR Extraction Layer**
- Upload images via drag-and-drop or file picker
- Extract text from signage player screenshots, error messages, and logs
- Powered by [Tesseract.js v5](https://github.com/naptha/tesseract.js) for client-side OCR
- Real-time progress tracking during text extraction
- Support for various image formats (PNG, JPG, JPEG, etc.)
- Auto-switches to extracted text view after processing

### 🤖 **AI Reasoning Layer**
- Integrate with [Groq Fast Inference API](https://groq.com/) for lightning-fast AI analysis
- Automatically analyze extracted text for patterns, insights, and actions
- Choose from multiple AI models (Llama, Mixtral, Gemma, and more)
- Customizable system prompts to guide AI behavior
- Adjustable temperature and max tokens for precise control
- Settings accessible via floating cogwheel icon

### 🎯 **Master Triage System** (New!)
- Optional per-workflow intelligent routing
- Auto-detects device type from content (Samsung, Sony, LG, Philips, ChromeOS, SignageOS)
- Categorizes screenshots: ERROR_SCREEN, BLACK_SCREEN, PROVISIONING_SCREEN, LOG_OUTPUT, CONTENT_DISPLAY
- Assesses severity: CRITICAL, HIGH, MEDIUM, LOW, INFO
- Auto-selects recommended actions based on analysis
- Fully configurable triage prompts per workflow
- Only runs when explicitly enabled in workflow settings

### 🔑 **Provisioning Code Detection**
- Automatic pattern recognition for common signage systems:
  - **SignageOS**: `#d362727gv` (matches `#[a-zA-Z0-9]{8,}`)
  - **MQ**: `name-1234` (matches `[a-zA-Z]+-\d{4}`)
  - **Dise**: `123-123` (matches `\d{3}-\d{3}`)
- One-click copy to clipboard
- Visual highlighting in results tab
- Regex-based detection for accuracy

### ⚙️ **Workflow Automation**
- **Three-Mode Interface:**
  - **Quick Mode**: Fast screenshot processing with task runner
  - **Workflow Builder**: Create multi-step automation workflows
  - **Tools**: Manage actions library and patterns

- **Workflow Features:**
  - Build workflows as "projects" with multiple chained actions
  - Visual pipeline showing action flow
  - Optional master triage per workflow
  - Enable/disable workflows independently
  - Workflows badge shows triage status

- **Action Types:**
  - LLM Analysis
  - Extract Information
  - Log Results
  - 6 predefined actions for signage operations
  - Create unlimited custom actions with tags

### 🛠️ **Actions Library**
- **Predefined Actions:**
  - Error Handler
  - Black Screen Diagnostics
  - Content Verification
  - Log Analyzer
  - Provisioning Code Extractor
  - Network Diagnostics

- **Action Management:**
  - Filter by tags: error, content, log, provision, network, hardware
  - Search functionality
  - Compact list view (plain text)
  - Detailed cards for selected actions
  - Create custom actions with CRUD interface

### 📊 **Task Runner** (Enhanced!)
- Two-tab interface:
  - **Task Runner**: Select and filter actions (default view)
  - **Execution Results**: View analysis output (auto-switches after run)
- Compact action selection (checkbox list)
- Selected actions show full detail cards
- Real-time execution progress
- Color-coded results (success/failure)

### 🎨 **Modern UI/UX**
- **Tab-Based Workflow:**
  - Upload/Extract combined in one card with tabs
  - Task Runner/Results combined in one card with tabs
  - Auto-switching tabs at logical moments
- Floating settings cogwheel (top-right)
- Settings in modal instead of separate page
- Responsive Bootstrap 5 interface
- Modern dark theme with glassmorphism effects
- Touch-friendly drag-and-drop
- Mobile-first design

### 🎛️ **Settings & Configuration**
- Accessible via floating ⚙️ icon (always visible)
- Modal-based settings (no page navigation needed)
- Secure local storage of API keys (no backend required)
- Auto-fetch available AI models from Groq API
- Visual model selection interface
- Temperature control (0-2 scale)
- Max tokens configuration
- Customizable system prompt templates
- Real-time configuration preview

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

1. **Open in browser**
   
   ```bash
   # Simply double-click the HTML file
   # OR serve with any local server
   python -m http.server 8000
   ```
1. **Configure API**

- Click the ⚙️ **cogwheel icon** (top-right)
- Enter your Groq API key
- Click **Save API Key**
- Click **Test Connection** to verify
- Click **Fetch Available Models** to load AI models
- Adjust temperature, max tokens, and system prompt
- Click **Save Settings**

1. **Start using Quick Mode**

- Upload an image (drag & drop or click)
- Click **Extract Text (OCR)**
- Text appears in “Extracted Text” tab
- Select actions from Task Runner
- Click **Run Selected Actions**
- View results in “Execution Results” tab

-----

## 📖 How to Use

### Quick Mode (Fast Processing)

1. **Upload Screenshot**

- Drag and drop or click to browse
- Preview appears instantly
- Auto-detects provisioning codes

1. **Extract Text**

- Click **Extract Text (OCR)**
- Progress bar shows real-time status
- Auto-switches to “Extracted Text” tab
- Provisioning codes highlighted if detected

1. **Select & Run Actions**

- Filter actions by category (error, content, log, etc.)
- Search by name
- Select actions (compact checkbox list)
- View selected action details below
- Click **Run Selected Actions**
- Auto-switches to “Execution Results” tab

### Building Workflows

1. **Navigate to Workflow Builder**

- Click **Workflow Builder** in navigation
- Click **New Workflow** button

1. **Configure Workflow**

- **Name:** e.g., “Error Monitoring System”
- **Description:** What this workflow does
- **Enable Master Triage:** (Optional checkbox)
  - If enabled: Configure custom triage prompt
  - Triage will auto-analyze and route actions
- **Add Actions:** Click “Add Action” to build pipeline
- Actions execute in sequence (chained)

1. **Example Workflows**
   
   **Error Monitoring (with Triage):**
   
   ```
   Name: Error Monitoring System
   Description: Detects and analyzes player errors
   Enable Master Triage: ✓
   Triage Prompt: (default or custom)
   
   Actions Pipeline:
   1. Error Handler
   2. Network Diagnostics
   3. Log Result
   ```
   
   **Content Verification (no Triage):**
   
   ```
   Name: Content Checker
   Description: Verifies correct content is playing
   Enable Master Triage: ✗
   
   Actions Pipeline:
   1. Content Verification
   2. Log Result
   ```
1. **Save & Manage**

- Click **Save** to store workflow
- Badge shows if triage is enabled
- Edit by selecting from sidebar
- Delete when no longer needed

### Managing Tools

1. **Navigate to Tools**

- Click **Tools** in navigation
- View Actions Library and Pattern Recognition

1. **Create Custom Actions**

- Click **Create Custom Action**
- Fill in:
  - Name: “Restart Player”
  - Description: “Remotely restart signage player”
  - Tags: “error, hardware, samsung”
  - Trigger Type: “Text Contains”
  - Trigger Value: “crash|freeze”
  - Action Type: “LLM Analysis”
  - Custom Prompt: “Analyze this crash and provide restart instructions”
- Click **Save Action**

1. **Action appears in:**

- Quick Mode task runner
- Workflow Builder action selector
- Tools actions library

-----

## 🎯 Use Cases

### Digital Signage Operations Teams

- **Error Detection:** Auto-detect and classify player errors
- **Black Screen Diagnosis:** Identify no-signal vs content issues
- **Network Troubleshooting:** Analyze connectivity problems
- **Remote Diagnostics:** Get fix instructions without site visit

### Provisioning & Deployment

- **Code Extraction:** Auto-detect SignageOS, MQ, Dise codes
- **One-Click Copy:** Instant clipboard copy for pairing
- **Validation:** Verify code formats automatically
- **Documentation:** Log all provisioning activities

### 24/7 Monitoring & Support

- **Autonomous Watchguard:** Auto-process screenshot feeds
- **Smart Routing:** Triage categorizes and routes to right action
- **Severity Assessment:** Prioritize critical issues first
- **Action Chaining:** Multi-step automated responses

### Multi-Site Management

- **Device Detection:** Identify Samsung, Sony, LG, Philips players
- **Standardized Workflows:** Same process across all sites
- **Log Analysis:** Centralized log processing
- **Performance Tracking:** Monitor and analyze trends

-----

## 🏗️ Architecture

### Three-Mode Structure

```
┌─────────────────────────────────────────┐
│           ⚙️ Settings Modal             │
│   (API, Models, Parameters - Always)    │
└─────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────┐
│         Quick Mode (Default)             │
│  ┌─────────────┐    ┌──────────────┐   │
│  │ Upload Tab  │    │ Task Runner  │   │
│  │ Extract Tab │    │ Results Tab  │   │
│  └─────────────┘    └──────────────┘   │
└─────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────┐
│        Workflow Builder                  │
│  ┌──────────┐    ┌──────────────────┐  │
│  │Workflows │───→│ Workflow Editor   │  │
│  │ Sidebar  │    │ - Config          │  │
│  │          │    │ - Master Triage   │  │
│  │          │    │ - Action Pipeline │  │
│  └──────────┘    └──────────────────┘  │
└─────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────┐
│              Tools                       │
│  - Actions Library (CRUD)                │
│  - Pattern Recognition                   │
└─────────────────────────────────────────┘
```

### Data Flow

```
Image Upload → OCR Extraction → [Optional: Master Triage]
                                          ↓
                                    Auto-Select Actions
                                          ↓
                                   Execute Pipeline
                                          ↓
                                    Display Results
                                          ↓
                                  Groq API (AI Reasoning)
```

### Modular Design

```
├── SettingsModule    → API keys, model config, localStorage
├── OCRModule         → Tesseract.js integration
├── LLMModule         → Groq API communication
├── Workflow Engine   → Triage, actions, execution
└── UI Components     → Tabs, modals, lists, cards
```

### Storage

All data stored locally in browser:

- API keys & settings (localStorage)
- Workflow definitions (localStorage)
- Custom actions (localStorage)
- Predefined actions (in-memory, always available)
- No server required, fully client-side

-----

## 🔧 Technical Stack

- **Frontend:** Vanilla JavaScript (ES6+), HTML5, CSS3
- **UI Framework:** Bootstrap 5 (mobile-first, tab components)
- **OCR Engine:** Tesseract.js v5 (client-side text extraction)
- **AI Provider:** Groq Fast Inference API
- **Icons:** Font Awesome 6
- **Storage:** Browser localStorage
- **Patterns:** Module pattern, async/await, event-driven

-----

## ⚙️ Configuration Options

### AI Model Parameters

- **Temperature** (0-2): Controls randomness
  - 0 = Deterministic, focused
  - 1 = Balanced (default: 0.7)
  - 2 = Creative, varied
- **Max Tokens** (1-8192): Maximum response length
  - 512 = Short responses
  - 1024 = Medium (default)
  - 2048+ = Long, detailed responses
- **System Prompt**: Global instruction template
  - Defines AI’s role and behavior
  - Applied to all analyses unless overridden
  - Can be overridden per workflow/action

### Master Triage Prompt

Configurable per workflow. Default structure:

```
1. Device Detection: Identify device type from content
2. Categorization: ERROR_SCREEN, BLACK_SCREEN, etc.
3. Severity Assessment: CRITICAL, HIGH, MEDIUM, LOW
4. Recommended Actions: Which actions should run
Format: JSON response with device_type, category, severity, summary, recommended_actions
```

### Action Triggers

|Trigger |Description            |Example          |
|--------|-----------------------|-----------------|
|Contains|Text includes substring|“error           |
|Regex   |Pattern match          |`[a-zA-Z]+-\d{4}`|
|Always  |Always runs            |(no condition)   |

### Action Types

|Type        |Description     |Use Case                       |
|------------|----------------|-------------------------------|
|LLM Analysis|AI reasoning    |Error analysis, troubleshooting|
|Extract     |Pull information|Codes, dates, device IDs       |
|Log         |Record result   |Audit trail, history           |

### Provisioning Code Patterns

|System   |Pattern          |Regex             |Example   |
|---------|-----------------|------------------|----------|
|SignageOS|Hash + 8+ chars  |`#[a-zA-Z0-9]{8,}`|#d362727gv|
|MQ       |Letters-4 digits |`[a-zA-Z]+-\d{4}` |name-1234 |
|Dise     |3 digits-3 digits|`\d{3}-\d{3}`     |123-123   |

-----

## 🔐 Security & Privacy

- **No Backend:** All processing happens in your browser
- **Local Storage Only:** API keys stored locally, never transmitted
- **No Data Collection:** Zero telemetry or tracking
- **API Communication:** Only with Groq API (user-configured)
- **Client-Side OCR:** Images never leave your device
- **No External Dependencies:** Single HTML file, works offline after load

-----

## 🚧 Troubleshooting

### OCR Issues

- Ensure image has clear, readable text
- Try images with higher resolution
- Check browser console for errors
- Verify Tesseract.js loaded correctly

### AI/API Issues

- Click ⚙️ icon and verify API key is saved
- Click “Test Connection” to check status
- Ensure you have API credits/quota
- Check browser console for error messages
- Try “Fetch Available Models” to refresh

### Workflow Issues

- Verify workflow is saved correctly
- Check if master triage is enabled (if expected)
- Confirm actions are added to pipeline
- Review action trigger conditions
- Check execution results for error messages

### UI Issues

- Clear browser cache and reload
- Try different browser
- Check browser console for JavaScript errors
- Ensure Bootstrap 5 and Font Awesome loaded

### Provisioning Code Detection

- Verify text extraction completed
- Check if pattern matches regex (see patterns table)
- Test with known good examples
- Review detected codes in Results tab

-----

## 🔮 Roadmap

### Version 2.1 (In Progress)

- [ ] Workflow execution history
- [ ] Export/import workflows as JSON
- [ ] Action statistics dashboard
- [ ] Batch screenshot processing

### Version 2.2

- [ ] Multi-language OCR support
- [ ] PDF document processing
- [ ] Email/webhook notifications
- [ ] Team collaboration features

### Version 3.0

- [ ] Cloud sync for workflows
- [ ] API for external integrations
- [ ] Advanced conditional branching
- [ ] ServiceNow/Jira connectors

-----

## 🤝 Contributing

Contributions welcome! This is a single-file application for easy forking.

### How to Contribute

1. Fork the repository
1. Make your changes
1. Test thoroughly (all three modes)
1. Submit a pull request

### Ideas for Contributions

- New predefined actions for signage use cases
- Additional provisioning code patterns
- UI/UX improvements
- Performance optimizations
- Additional AI provider support
- Documentation improvements
- Bug fixes

-----

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

-----

## 🙏 Acknowledgments

- [Tesseract.js](https://github.com/naptha/tesseract.js) - OCR engine
- [Groq](https://groq.com/) - Fast AI inference
- [Bootstrap](https://getbootstrap.com/) - UI framework
- [Font Awesome](https://fontawesome.com/) - Icons

-----

## 📞 Support

For issues, questions, or feature requests:

- Open an issue on GitHub
- Check the troubleshooting section
- Review the Groq API documentation

-----

## 🌟 Why SnapOCR 2.0?

- **Purpose-Built:** Designed specifically for digital signage operations
- **Intelligent Routing:** Master triage auto-analyzes and routes
- **Zero Infrastructure:** No backend, no database, no deployment
- **Instant Setup:** Download and run in seconds
- **Full Control:** Customize everything, own your data
- **Extensible:** Modular architecture, easy to enhance
- **Production-Ready:** Used in real signage operations
- **Practical:** Solves real problems for support teams

-----

**Built with passion for intelligent automation and digital signage operations teams**

*Transform signage screenshots into actionable insights, automatically.*
