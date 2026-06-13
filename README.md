# BCG GenAI Job Simulation: Production-Ready Financial Chatbot

This repository contains the prototype for an AI-powered financial chatbot built for the **BCG GenAI Job Simulation** on [Forage](https://www.theforage.com/virtual-experience/gabev3vXhuACr48eb/bcg/gen-ai-anlo/developing-an-ai-powered-financial-chatbot). 

The application seamlessly merges the data processing capabilities of **Pandas** with a **Natural Language Understanding (NLU)** text-matching engine to let users query financial statements conversationally.

---

## 🚀 Key Features

* **Dynamic Data Integration:** Automatically loads financial datasets (`Extracted_data.csv`) and dynamically processes metrics like Year-over-Year (YoY) growth rates.
* **Fuzzy Semantic Matching:** Powered by string-similarity algorithms, allowing the bot to understand natural, casual human phrasing (e.g., matching *"show me the revenue"* to `total revenue`).
* **Typo Tolerance:** Features automatic error checking to handle minor misspelling or formatting slips gracefully without throwing exceptions.
* **Zero External Dependencies:** Built entirely with Python's native standard libraries alongside Pandas, ensuring rapid local deployment.

---

## 🛠️ How It Works (The Core Logic)

1. **The Data Pipeline:** When started, the script searches for `Extracted_data.csv`. It calculates percentages for growth trends and organizes these numbers into an optimized retrieval dataset.
2. **Intent Matching:** The text loop takes user prompt strings, cleans up extra spaces, strips capitalizations, and tests them against target corporate KPIs.
3. **Fuzzy Fallback Matrix:** If a conversational phrase doesn't align explicitly, the mathematical similarity ratio steps in to route the question to the closest matching concept.

---

## 📂 Supported User Intent Categories

You can converse with the chatbot regarding any of these main financial concepts:
1. **Total Revenue** (e.g., *"Can you show me the total revenue please?"*)
2. **Net Income Change** (e.g., *"What is the net income change over last year?"*)
3. **Net Profit Margin** (e.g., *"What does the profit margin look like?"*)
4. **Operating Expenses** (e.g., *"What are our total expenses?"*)
5. **Debt to Equity Ratio** (e.g., *"Is our debt leverage healthy?"*)

---

## 💻 Sample Interaction Console Trace

```text
==========================================================
Welcome to the Production-Ready AI Financial Chatbot!
==========================================================
Ask me anything about Revenue, Income, Margins, Expenses, or Debt.
I understand natural phrasing! Type 'exit' to quit.

You: check revenue numbers please
Chatbot: The average Year-over-Year Revenue Growth calculated from your data is 14.20%.

You: how about profit margins?
Chatbot: The calculated net profit margin stands at 15.4% based on recent statement data.

You: exit
Chatbot: Goodbye! Have a great day analyzing data.