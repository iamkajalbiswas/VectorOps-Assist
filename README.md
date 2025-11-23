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

Support workflows typically fall into two categories:

### **❌ Rule-based chatbots**
Cheap and fast, but easily break when customers ask anything unexpected.

### **❌ Pure LLM agents**
Intelligent but:
- slow  
- expensive  
- unpredictable  
- unsafe for critical flows like refunds or billing  

Teams must choose between **cost** and **intelligence**.  
VectorOps Assist eliminates this trade-off.

---

# 🟢 Solution: Hybrid Intelligence

VectorOps Assist introduces a **two-tier architecture**:

### **Tier 1 — Deterministic Rule Engine**
Handles:
- cancellations  
- order status  
- simple billing issues  
- refund requests  
- FAQ responses  

Instant, predictable, cost-free.

### **Tier 2 — Generative AI Agent (Gemini 2.0 Flash)**
Handles:
- deep reasoning  
- multi-step actions  
- CRM & database lookups  
- refund eligibility  
- ticket creation  
- long-term memory  

LLM never fabricates logic — all critical decisions run through **Python tools**.

This hybrid design reduces LLM usage by **up to 90%**.

---

# 🏗️ System Architecture

### **1. Workbench UI (React)**
Notebook-style interface:
- live Python execution  
- tool call visualization  
- log inspector  
- rule engine editor  
- memory viewer  

Built with **React + Tailwind**.

---

### **2. Agent Core (Python Simulation)**

#### **Tier 1: Rule Engine**
- lightweight keyword/regex intent detection  
- template-based replies  
- micro memory sliding window  
- ultra-fast routing  

#### **Tier 2: VectorOps Agent**
Powered by:
- ReAct reasoning loop  
- TTL-based memory manager  
- Function-calling interface  
- Dynamic tool discovery (MCP-like)  

#### **Tools Included**
- `get_order_status(order_id)`  
- `check_refund(order_id)`  
- `file_complaint_ticket(...)`  
- `query_customer_db(sql_query)`  

---

### **3. Mock Company Backend**

Includes simulated:
- order DB  
- ticketing system  
- refund policies  
- CRM  

Gives the agent real production-like behavior.

---

### **4. Deployment Pipeline**

Automatically generates:
- `server.py` (FastAPI wrapper)  
- `Dockerfile`  

Deployable to:
- Cloud Run  
- ECS  
- Any container-based infra  

---

# 🛠️ Setup & Installation

### **Requirements**
- Node.js 18+  
- Gemini API Key  
- (Optional) Python 3.11  

---

### **1. Clone Repo**
```bash
git clone https://github.com/iamkajalbiswas/VectorOps-Assist
cd VectorOps-Assist
```
**2. Install Dependencies**
```bash
npm install
```
**3. Add API Key**

Create .env :

```env
API_KEY=your_gemini_api_key
```
**4. Start Workbench**
```bash
npm start
```

Open browser:
👉 http://localhost:8080

## 🧪 Usage Guide

### **1. Initialize Notebook**
This step loads all core components:
- imports  
- backend simulation  
- rule engine  
- agent core  

---

### **2. Test Tier 1**
Run simple test prompts to see **instant deterministic replies**.

---

### **3. Test Tier 2**
The agent will:
- analyze intent  
- decide if a tool is needed  
- execute the tool  
- compose the final answer  

---

### **4. Evaluation**
Compare Tier 1 and Tier 2 outputs **side-by-side** to understand hybrid behavior.

---

### **5. Export for Deployment**
Running the export cell generates:
- `server.py`  
- `Dockerfile`  

These files can be deployed directly to container environments.

---

## 📊 Features

- Hybrid Tier-1/Tier-2 intelligence  
- ReAct reasoning loop  
- Deterministic function-calling safety  
- Full support workbench UI  
- Memory system with TTL and compression  
- Container-ready deployment  
- Clean logging & observability  

---

## 🌟 Why VectorOps Assist?

Support teams need:
- speed  
- accuracy  
- transparency  
- reliability  
- low cost  

VectorOps intelligently splits workloads between rules and AI to deliver all of these benefits simultaneously.

---

## 🗺️ Roadmap

- Real MCP plugin support  
- Multi-agent collaboration  
- Analytics dashboard  
- Kubernetes deployment templates  
- Automation marketplace  
- Enhanced reasoning visualization  

---

## 🤝 Contributing

Contributions are welcome!  
Submit PRs to improve tools, UI, workflows, or core agent logic.

---

## 📄 License

MIT License — see `LICENSE` for full details.


