# **VectorOps Assist 🚀**
### **Hybrid Automation for High-Velocity Support Teams**

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Status](https://img.shields.io/badge/status-Production%20Ready-green.svg)
![Powered By](https://img.shields.io/badge/AI-Gemini%202.0%20Flash-purple)

VectorOps Assist is a hybrid AI support framework built to help teams handle customer queries faster, cheaper, and more reliably.  
Instead of relying only on rule-based chatbots or expensive LLMs, VectorOps combines the best of both: **deterministic rules for simple tasks** and **smart GenAI reasoning for complex cases**.  
It’s designed for engineers who want full control, transparency, and production-ready behavior right out of the box.

---

# 🔥 Problem

Most support workflows fall into two buckets:

### **❌ Rule-based chatbots**
They're cheap and fast… until a customer asks something even slightly unexpected. Then they break.

### **❌ Pure LLM agents**
They’re brilliant, but:
- slow  
- expensive  
- unpredictable  
- unsafe for tasks like refunds, billing, or order lookups  

Support teams end up choosing between **cost** and **intelligence**.  
VectorOps Assist removes that trade-off.

---

# 🟢 Solution: Hybrid Intelligence

VectorOps Assist introduces a **two-tier architecture** that splits the work intelligently:

### **Tier 1 — Deterministic Rule Engine**
Handles the repetitive stuff like:
- “I want to cancel”
- “Where’s my order?”
- “I need a refund”
- Basic billing issues

It replies instantly, costs nothing, and always does what it’s supposed to do.

### **Tier 2 — Generative AI Agent (Powered by Gemini 2.0 Flash)**
This is where the “smart” work happens:
- multi-step reasoning  
- tool / function calling  
- CRM & order data lookups  
- refund eligibility checks  
- ticket creation  
- long-term memory  

The LLM never makes up policies — all critical logic is executed through **Python tools**, keeping everything deterministic and safe.

Together, this hybrid design cuts LLM usage by **up to 90%** while improving answer quality and reliability.

---

# 🏗️ System Architecture

### **1. Workbench UI (React)**
A notebook-style interface that lets you:
- write Python logic  
- test the agent in real time  
- inspect logs  
- observe tool calls  
- tweak rules or memory  

Everything runs inside a clean React + Tailwind setup.

---

### **2. Agent Core (Python Simulation)**

#### **Tier 1: Rule Engine**
- simple keyword/regex intent detection  
- matching template responses  
- fast routing logic  
- small sliding-window memory  

#### **Tier 2: VectorOps Agent**
Built with modern agent techniques:
- ReAct loop  
- Memory manager with TTL + compaction  
- Function calling schema  
- Tool orchestrator  
- MCP-style dynamic tool discovery  

#### **Available Tools**
- `get_order_status(order_id)`  
- `check_refund(order_id)`  
- `file_complaint_ticket(...)`  
- `query_customer_db(sql_query)`  

---

### **3. Mock CompanySystem Backend**
To simulate real support infra, the project includes a fake:
- order database  
- ticketing system  
- refund rules engine  
- CRM lookup  

This gives the agent realistic data to work with.

---

### **4. Deployment Pipeline**
The notebook can auto-generate:
- `server.py` → FastAPI wrapper  
- `Dockerfile` → Deploy to Cloud Run / ECS / containers  

So the same logic you test locally can go straight to production.

---

# 🧱 Architecture Diagram (Text Version)

User Request
↓
Routing Controller (decides Tier 1 or Tier 2)
↓

Tier 1: Rule Engine ──→ Instant Reply → Logs → Return
│
└── if complex → Tier 2

Tier 2: VectorOps Agent
↓
Memory Manager → Prompt Builder → Gemini 2.0 Flash
↓
Does LLM request a Tool?
├── Yes → Execute Python Tool → Return Result → LLM Final Response
└── No → Generate Final Response

Final Response → Logs → Memory Update → Client


---

# 🛠️ Setup & Installation

### **Requirements**
- Node.js 18+  
- Gemini API Key  
- (Optional) Python 3.11 for deployment export  

### **1. Clone the Repo**
```bash
git clone https://github.com/iamkajalbiswas/VectorOps-Assist
cd VectorOps-Assist


### **2. Install Dependencies**
npm install

### **3. Add Your API Key**

**Create .env:**

API_KEY=your_gemini_api_key

### **4. Start the Workbench**
npm start


### **Open:**
👉 http://localhost:8080

8080

### **🧪 Usage Guide**
1. Initialize

Run the first cells to load:

imports

logging

mock backend

rule engine

2. Try Tier 1

Quick demo to see instant rule-based responses.

3. Test Tier 2

Run the VectorOps Agent cells:

the agent analyzes the message

decides if it needs a tool

calls the Python tool

returns a final polished response

4. Compare Results

The evaluation cell shows side-by-side outputs for both tiers.

5. Export for Deployment

Generates:

server.py

Dockerfile

Push both to your backend infrastructure.

### **📊 Features**

Hybrid Tier-1/Tier-2 AI system

Fast deterministic routing

Deep reasoning through ReAct

Function-calling for safe business logic

Context-aware memory and summarization

React workbench for experimentation

Auto-generated deployment artifacts

Clear, structured logs

### **🌟 Why VectorOps Assist?**

Because real support teams need:

speed + accuracy

predictability + flexibility

AI intelligence + enterprise safety

VectorOps hits that balance by splitting responsibilities intelligently between rules and GenAI.

### **🗺️ Roadmap**

MCP plugins (real)

Multi-agent handoff

Built-in analytics dashboard

Deployment templates for Kubernetes

Plugin marketplace for support automation

Better UI for agent reasoning visualization

### **🤝 Contributing**

Pull requests are welcome.
If you'd like to add new tools, upgrade the UI, or improve the agent logic, feel free to open an issue or submit a PR.

📄 License

MIT License — see LICENSE for details.
