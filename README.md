# 🤖 API Integration Research Agent

An autonomous multi-agent research and verification engine that audits API surfaces, authentication schemas, and access gating across 100 software platforms.

---

## ⚡ Quick Start

### 1. Install Dependencies

```bash
# Clone repository & enter directory
git clone https://github.com/gauri-dhanakshirur/Composio-Online-Assessment.git
cd Composio-Online-Assessment

# Install Python dependencies
pip install -r requirements.txt

# Install Node.js dependencies & Playwright Chromium
npm install
npx playwright install chromium
```

### 2. Configure Environment (Optional)

To run live API extraction and web searches, set your API keys in `.env`:

```bash
cp .env.example .env
```

Edit `.env`:
```env
OPENAI_API_KEY=sk-...
COMPOSIO_API_KEY=...
```
*(If no API keys are provided, the agent automatically runs using pre-computed offline data).*

---

## 🚀 How to Run the Research Agent

### Option 1: Run the Full Multi-Agent Pipeline
Runs the orchestrator agent across all 100 platforms (Discovery → Schema Extraction → Verification → Evaluation):

```bash
python3 agent.py
```
*(or via npm script: `npm run agent`)*

#### Live vs Offline Options:
```bash
# Force live extraction via GPT-4o & Composio SDK
python3 agent.py --live

# Run verification phase only (Pass 2)
python3 agent.py --verify-only
```

### Option 2: Run Headless Browser Verification (Pass 2 Only)
Probes developer portals using Playwright Chromium to test self-serve vs. enterprise gate signals:

```bash
npm run verify
```

---

## 📊 View Executive Dashboard

Open `index.html` in your web browser to view interactive Chart.js analytics, root cause cards, and the searchable 100-app research matrix:

```bash
open index.html
```

---

## 📁 Key Files Overview

- **`agent.py`**: Autonomous research agent orchestrator & sub-agents (`DiscoverySubAgent`, `SchemaExtractorAgent`, `HeadlessVerifierAgent`, `EvaluatorAgent`).
- **`playwright_verifier.ts`**: Headless browser assertion engine for Pass 2 verification.
- **`index.html`**: Standalone dark-mode executive dashboard with real-time search & filters.
- **`pass1_output.json`**: Raw document extraction findings for 100 platforms.
- **`pass2_output.json`**: Verified findings with two-pass accuracy delta.
