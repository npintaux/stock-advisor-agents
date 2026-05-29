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

To install this plugin locally in your **AGY CLI** environment so it is correctly recognized, loaded, and enabled, run the official installer command by pointing it to the absolute path of the plugin directory:

```bash
agy plugins install /home/npintaux/Code/stock-advisor/_agents/plugins/stock-advisors
```

> [!NOTE]
> You can also use the singular `agy plugin install` command:
> ```bash
> agy plugin install /home/npintaux/Code/stock-advisor/_agents/plugins/stock-advisors
> ```

This command automatically registers and initializes the plugin and its subagents inside your global Antigravity environment, ensuring they are ready to be used.

---

## 🔍 Verifying the Installation

To verify that the plugin is successfully loaded and its subagents are discoverable by the AGY CLI:

1. Open your terminal.
2. Run the plugin list command to verify it is loaded with both `installed` and `agents` components:
   ```bash
   agy plugin list
   ```
3. Run a prompt querying your AGY assistant about the loaded plugins:
   ```bash
   agy --prompt "What plugins do you have loaded?"
   ```
   The assistant will output that **Stock Advisors** is loaded as a specialized domain-specific plugin.

4. You can now invoke any of the 5 specialized advisor subagents dynamically in your CLI session using their standard names (e.g., `dividend-growth-advisor`) without having to manually define them first!
