# 📈 Declarative CAC40 Multi-Strategy Stock Advisor

This repository contains a fully file-based, zero-code **Antigravity CLI Plugin** that defines six elite financial advisor subagents: **Multi-Strategy Portfolio Coordinator**, **Dividend Growth**, **Growth**, **Value**, **Swing Trading**, and **CAC40 Swing Briefer**.

These advisors are declared natively as **Antigravity Subagents** inside a custom plugin structure. This design completely decouples the advisors' trading strategies, rules, and mathematical scorecards from any specific runner code—making them instantly discoverable and executable by both the **Antigravity Chat Assistant** and the **Antigravity CLI**.

---

## 📂 Project Architecture

The workspace and global configuration follow this standardized layout:

```text
stock-advisor/
├── README.md                          # This quick-start guide
└── _agents/plugins/stock-advisors/     # Git-tracked plugin source directory
    ├── plugin.json                    # Plugin manifest and metadata
    └── agents/                        # Declarative subagent templates (Markdown with YAML frontmatter)
        ├── multi-strategy-briefer.md  # Root Coordinator & Synthesis Agent
        ├── cac40-swing-briefer.md     # Swing Trading Coordinator & Briefing Agent
        ├── dividend-growth.md         # Dividend Growth Investing (DGI) Specialist
        ├── growth.md                  # Hyper-growth & Market Disruption Analyst
        ├── value.md                   # Graham & Munger Deep-Value / Margin of Safety Expert
        └── swing-trading.md           # Technical Swing Trading & Risk Blueprint Planner
```

- **Global Config Path** (for Antigravity CLI & global discovery):
  `~/.gemini/config/plugins/stock-advisors/`
- **Workspace Config Path** (for repository scoping):
  `/home/npintaux/Code/stock-advisor/_agents/plugins/stock-advisors/`

---

## 🤖 The Six Advisor Profiles

### 1. 🏆 Multi-Strategy Portfolio Coordinator (`multi-strategy-briefer.md`)
*   **Philosophy**: Oversees the entire screening pipeline. Conducts broad CAC40 pre-screening, coordinates parallel delegation to specialized subagents, and synthesizes the results into a unified flagship dashboard.

### 2. ⚡ CAC40 Swing Briefer (`cac40-swing-briefer.md`)
*   **Philosophy**: Coordinates technical swing setups across all 40 component stocks, delegating ticker-by-ticker chart analyses and consolidating them into a daily market briefing.

### 3. 💸 Dividend Growth Advisor (`dividend-growth.md`)
*   **Philosophy**: Focuses on "compounding machines"—recession-resistant, dividend-paying businesses with durable competitive advantages (e.g., Vinci, AXA, Air Liquide).
*   **Core Metrics**: Payout ratios ($< 60\%$ Earnings, $< 65\%$ FCF), Net Debt/EBITDA $< 2.5\text{x}$, and Chowder Scores $> 12\%$.

### 4. 🚀 Growth Stock Advisor (`growth.md`)
*   **Philosophy**: Focuses on identifying tomorrow's market leaders with massive Total Addressable Markets (TAM) and high reinvestment rates (e.g., Safran, Schneider Electric).
*   **Core Metrics**: Revenue Growth $> 20\%$, Gross Margins $> 50\%$, and attractive PEG ratios.

### 5. ⚖️ Value Stock Advisor (`value.md`)
*   **Philosophy**: Classic deep-value investing under Graham and Munger principles. Identifies fundamentally sound businesses trading at a deep discount (e.g., Renault, Carrefour).
*   **Core Metrics**: Low multiples (P/E $< 15\text{x}$, P/B $< 1.5\text{x}$), negative net automotive debt, and high shareholder yield.

### 6. 📊 Swing Trading Advisor (`swing-trading.md`)
*   **Philosophy**: Technical momentum and price-action specialist. Captures short-term price swings over days or weeks with mechanical risk controls (e.g., STMicroelectronics).
*   **Core Metrics**: Price relative to 20 EMA and 200 SMA, MACD breakouts, and strict $1:2$ Risk-to-Reward ratio models.

---

## ⚡ How to Trigger and Use the Subagents

Because these advisors are registered as native Antigravity subagents, you can invoke them seamlessly from any Antigravity-compatible interface:

### 💬 Option A: Trigger via the Antigravity Chat Assistant
In your chat session with Antigravity, simply ask the assistant to delegate stock analysis tasks to the specialized subagents:
> *"Can you have the `dividend-growth-advisor` analyze Apple (AAPL) and give me a full scorecard?"*
>
> *"Spawn the `swing-trading-advisor` to draw up a clear trade blueprint and position sizing for NVIDIA (NVDA)."*

### 💻 Option B: Trigger via the Antigravity CLI
If you are running the Antigravity CLI tool in your terminal, you can direct it to run specific stock analysis scripts or prompts while targeting these registered subagents:

```bash
# General usage to chat with a subagent via the CLI
antigravity chat --agent dividend-growth-advisor "Analyze Microsoft (MSFT) dividend safety"

# Trigger the multi-strategy screener
antigravity chat "Run the multi-strategy portfolio screening on the CAC40 index."
```

---

## 🚀 Git Initialization & Pushing to GitHub

To save this codebase under version control and share it with your colleagues on GitHub, execute the following commands in your local terminal inside `/home/npintaux/Code/stock-advisor`:

### Step 1: Initialize Git Local Repository
```bash
git init
```

### Step 2: Add Files & Create Your First Commit
Create a `.gitignore` to prevent tracking virtual environments and system logs, then stage and commit:
```bash
# Ignore virtual environments and system files
echo "test_venv/" >> .gitignore
echo "*.log" >> .gitignore
echo ".system_generated/" >> .gitignore

# Stage all files
git add .

# Create the initial commit
git commit -m "feat: initial commit of stock-advisor multi-agent plugin"
```

### Step 3: Link Your Local Repository to GitHub
1. Go to your GitHub account in your web browser.
2. Click the **"+"** icon in the top right -> **New repository**.
3. Name your repository: `stock-advisor-agents` (you can leave description and README blank since we already have them).
4. Click **Create repository**.
5. Copy the remote URL (e.g., `git@github.com:your-username/stock-advisor-agents.git` or `https://github.com/your-username/stock-advisor-agents.git`).

### Step 4: Rename Branch & Push to GitHub
Paste the URL in the commands below to link and push your files:
```bash
# Rename default branch to main
git branch -M main

# Add the remote link (replace with your actual copied URL)
git remote add origin https://github.com/your-username/stock-advisor-agents.git

# Push to your main branch
git push -u origin main
```
Your colleagues can now easily download or clone this workspace to get started!
