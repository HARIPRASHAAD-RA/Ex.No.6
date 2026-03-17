# Ex.No.6 Development of Python Code Compatible with Multiple AI Tools

# Date:14-03-2026
# Register no. 212223040060
# Aim: Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights with Multiple AI Tools

# AI Tools Required:
CHATGPT CLAUDE GEMINI

# Explanation:
Experiment the persona pattern as a programmer for any specific applications related with your interesting area. 
Generate the outoput using more than one AI tool and based on the code generation analyse and discussing that. 

## Algorithm Overview

### Step-by-Step Algorithm for Multi-AI Tool Integration

1.  **Set Up API Integrations**
    * Install the required libraries and configure authentication credentials for each AI platform: ChatGPT, Claude, and Gemini.
    * Utilize `requests` or dedicated SDKs for seamless API connectivity.
2.  **Input Stock Query**
    * Capture user-provided data including stock symbols, recent price actions, and key financial metrics.
3.  **Format Prompts**
    * Three distinct prompt structures will be employed:
        * **Straightforward Prompt** – Requesting a direct stock trend forecast.
        * **Tabular Format** – Organizing financial data into a structured table.
        * **Missing Word Prompt** – Supplying an incomplete financial statement for completion.
4.  **Submit Prompts to Each AI Tool**
    * Dispatch the formatted prompts to the ChatGPT, Claude, and Gemini APIs simultaneously.
5.  **Receive and Parse Responses**
    * Retrieve the generated outputs, including market predictions and specific investment guidance.
6.  **Comparison of Outputs**
    * Evaluate the results based on criteria such as precision, clarity, technical depth, and overall user experience.
7.  **Generate Actionable Insights**
    * Identify which specific AI model excels at processing each unique query type.
8.  **Create Final Report**
    * Consolidate all findings and performance metrics into a detailed evaluation document.

---

## Prompt Types

### 1. Straightforward Prompt
→ A direct query requesting a prediction regarding a specific stock's trend along with supporting reasoning.

### 2. Tabular Format
→ Historical price movements and trading volumes presented in a structured table for data-driven analysis.

### 3. Missing Word Prompt
→ A "fill-in-the-blank" style prompt featuring an incomplete financial sentence for the AI to finalize.

---

## Example Queries & Responses

### 1. Straightforward Prompt

**Prompt:**
“Analyze Apple Inc. (AAPL) stock based on its recent price movement and suggest if it’s a good time to buy, sell, or hold.”

| AI Tool | Response |
| :--- | :--- |
| **ChatGPT** | AAPL shows a steady uptrend; suggests a short-term hold; fundamentals remain robust. |
| **Claude** | Recommends a hold; anticipates moderate growth; suggests monitoring upcoming quarterly reports. |
| **Gemini** | Detects strong upward momentum; recommends buying if the RSI stays under 70. |

### 2. Tabular Format Prompt

**Prompt:**

| Indicator | Value |
| :--- | :--- |
| Price Change (1M) | +5% |
| Volume Trend | Increasing |
| RSI | 62 |
| PE Ratio | 28 |

**Query:**
“Based on this data, what is the likely market action for the next week?”

| AI Tool | Response |
| :--- | :--- |
| **ChatGPT** | Bullish outlook for the short term; price likely to test higher resistance zones. |
| **Claude** | Forecasts a minor price correction before the upward trend continues. |
| **Gemini** | Neutral to bullish sentiment; clear evidence of sustained buying pressure. |

### 3. Missing Word Prompt

**Prompt:**
“The AAPL stock is expected to ______ in the upcoming week.”

| AI Tool | Response |
| :--- | :--- |
| **ChatGPT** | Rise |
| **Claude** | Consolidate |
| **Gemini** | Increase gradually |


## Python Code Example for Multi-AI Framework Integration

```
import openai
import anthropic
import google.generativeai as genai

# Configuration of API Credentials
OPENAI_KEY = "your_openai_api_key"
CLAUDE_KEY = "your_anthropic_api_key"
GEMINI_KEY = "your_google_gemini_api_key"

# 1. ChatGPT Integration (Using OpenAI Library)
def fetch_chatgpt_analysis(query):
    client = openai.OpenAI(api_key=OPENAI_KEY)
    response = client.chat.completions.create(
        model="gpt-4",
        messages=[{"role": "user", "content": query}],
        max_tokens=200
    )
    return response.choices[0].message.content.strip()

# 2. Claude Integration (Using Anthropic Library)
def fetch_claude_analysis(query):
    client = anthropic.Anthropic(api_key=CLAUDE_KEY)
    response = client.messages.create(
        model="claude-3-opus-20240229",
        max_tokens=200,
        messages=[{"role": "user", "content": query}]
    )
    return response.content[0].text

# 3. Gemini Integration (Using Google Generative AI Library)
def fetch_gemini_analysis(query):
    genai.configure(api_key=GEMINI_KEY)
    model = genai.GenerativeModel('gemini-pro')
    response = model.generate_content(query)
    return response.text

# Define Market Analysis Query
market_query = "Provide a technical analysis for Apple Inc. (AAPL) based on current volatility and suggest a Buy/Sell/Hold stance."

# Execute requests across all platforms
gpt_result = fetch_chatgpt_analysis(market_query)
claude_result = fetch_claude_analysis(market_query)
gemini_result = fetch_gemini_analysis(market_query)

# Display Formatted Results
print(f"--- ChatGPT Analysis ---\n{gpt_result}\n")
print(f"--- Claude Analysis ---\n{claude_result}\n")
print(f"--- Gemini Analysis ---\n{gemini_result}")
```
# Conclusion:
This project provides an automated solution for comparing stock market predictions and insights across multiple AI tools. By integrating ChatGPT, Claude, and Gemini, the system helps identify which AI delivers more accurate, clear, and practical market recommendations for investors.

# Result: The corresponding Prompt is executed successfully.
