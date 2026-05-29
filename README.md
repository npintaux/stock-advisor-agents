# 📈 Declarative CAC40 Multi-Strategy Stock Advisor

This repository contains a fully file-based, zero-code **Antigravity CLI Plugin** that defines five elite financial advisor subagents: **Multi-Strategy Portfolio Coordinator**, **Dividend Growth**, **Growth**, **Value**, and **Swing Trading**.

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

## 🤖 The Five Advisor Profiles

### 1. 🏆 Multi-Strategy Portfolio Coordinator (`multi-strategy-briefer.md`)
*   **Philosophy**: Oversees the entire screening pipeline. Conducts broad CAC40 pre-screening, coordinates parallel delegation to specialized subagents, and synthesizes the results into a unified flagship dashboard.

### 2. 💸 Dividend Growth Advisor (`dividend-growth.md`)
*   **Philosophy**: Focuses on "compounding machines"—recession-resistant, dividend-paying businesses with durable competitive advantages (e.g., Vinci, AXA, Air Liquide).
*   **Core Metrics**: Payout ratios ($< 60\%$ Earnings, $< 65\%$ FCF), Net Debt/EBITDA $< 2.5\text{x}$, and Chowder Scores $> 12\%$.

### 3. 🚀 Growth Stock Advisor (`growth.md`)
*   **Philosophy**: Focuses on identifying tomorrow's market leaders with massive Total Addressable Markets (TAM) and high reinvestment rates (e.g., Safran, Schneider Electric).
*   **Core Metrics**: Revenue Growth $> 20\%$, Gross Margins $> 50\%$, and attractive PEG ratios.

### 4. ⚖️ Value Stock Advisor (`value.md`)
*   **Philosophy**: Classic deep-value investing under Graham and Munger principles. Identifies fundamentally sound businesses trading at a deep discount (e.g., Renault, Carrefour).
*   **Core Metrics**: Low multiples (P/E $< 15\text{x}$, P/B $< 1.5\text{x}$), negative net automotive debt, and high shareholder yield.

### 5. 📊 Swing Trading Advisor (`swing-trading.md`)
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

## 🚀 Installation & Setup

To install this plugin locally in your **Antigravity CLI** environment (or share it with your colleagues so they can run it), follow these simple steps to register the agents globally:

### Option A: Install via Git Clone (Recommended)

Colleagues can clone your GitHub repository directly into their global Antigravity configuration directory:

```bash
# 1. Create the global configuration directory if it doesn't exist
mkdir -p ~/.gemini/config/plugins

# 2. Clone the repository directly as the "stock-advisors" plugin
git clone https://github.com/npintaux/stock-advisor-agents.git ~/.gemini/config/plugins/stock-advisors
```

### Option B: Local Installation from this Workspace

If you already have this repository cloned locally on your machine, you can install the plugin simply by copying or symlinking the plugin folder to your global config directory:

```bash
# 1. Ensure the global configuration directory exists
mkdir -p ~/.gemini/config/plugins

# 2. Copy the plugin subdirectory to the global config folder
cp -r _agents/plugins/stock-advisors ~/.gemini/config/plugins/
```

---

## 🔍 Verifying the Installation

To verify that the subagents are successfully registered and discoverable by the Antigravity CLI:

1. Open your terminal.
2. Ask your Antigravity assistant or run the CLI list command to verify the loaded plugins:
   ```bash
   antigravity chat "What plugins do you have loaded?"
   ```
   The assistant will list `stock-advisors` with its 5 active agent profiles:
   *   `multi-strategy-briefer`
   *   `dividend-growth-advisor`
   *   `growth-advisor`
   *   `value-advisor`
   *   `swing-trading-advisor`
