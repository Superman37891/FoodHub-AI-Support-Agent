FoodHub AI Customer Support Agent 🤖🍕
An intelligent, secure, and production-ready customer support chatbot built with Python, LangChain, OpenAI (GPT-4o-mini), and SQLite. The agent connects directly to an order management database to provide real-time order tracking, delivery ETAs, and transaction lookups while enforcing robust safety and security guardrails.

🏗️ Architecture & Core Components
SQL Agent (LangChain create_sql_agent):

Directly interfaces with the relational SQLite database (customer_orders.db).

Dynamically generates and executes SQL queries to retrieve live order statuses, item lists, and payment details.

ReAct Orchestration & Tools:

Order Query Tool: Executes SQL operations for data retrieval.

Answer Tool: Passes raw tool outputs through an LLM post-processing step to rewrite responses into a polite, professional, and customer-friendly tone without altering facts.

Dual-Layered Guardrails:

Input Guardrail: Evaluates user prompts before execution to classify intent, routing queries into categories like valid process, emotional escalation, chat exit, or adversarial/jailbreak attacks (blocking prompt injections, PII scraping, and unauthorized modifications).

Output Guardrail: Validates final responses to ensure no data leaks, unauthorized schema modifications, or unsafe text reach the user.

🛠️ Tech Stack
Language: Python 3.11+

Orchestration & Frameworks: LangChain, LangGraph, OpenAI API

Database: SQLite, SQLDatabase Toolkit

Environment & Tools: Jupyter Notebook / Google Colab

🧪 Test Scenarios & Safety Evaluation
The system was rigorously tested against adversarial and edge-case queries:
