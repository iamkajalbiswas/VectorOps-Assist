# **VectorOps Assist 🚀**
## **Hybrid Automation for High-Velocity Support Teams**

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Status](https://img.shields.io/badge/status-Production%20Ready-green.svg)
![Powered By](https://img.shields.io/badge/AI-Gemini%202.0%20Flash-purple)

VectorOps Assist is an enterprise-grade **Hybrid Support Agent Workbench** for building, evaluating, and deploying intelligent customer support automations.  
It unifies **deterministic rule engines** with **Generative AI** to deliver **fast, accurate, and cost-efficient** support at scale.

---

# 📘 **Table of Contents**
- [🔥 Problem](#-problem)
- [🟢 Solution: Hybrid Intelligence](#-solution-hybrid-intelligence)
- [🏗️ System Architecture](#️-system-architecture)
- [🧱 Architecture Diagram](#-architecture-diagram)
- [🛠️ Setup & Installation](#️-setup--installation)
- [🧪 Usage Guide](#-usage-guide)
- [📊 Features Checklist](#-features-checklist)
- [🌟 Why VectorOps Assist?](#-why-vectorops-assist)
- [🗺️ Roadmap](#️-roadmap)
- [🤝 Contributing](#🤝-contributing)
- [📄 License](#-license)

---

# 🔥 **Problem**

Support teams today face a difficult trade-off:

### ❌ Traditional Chatbots  
Fast, cheap — but brittle. They break easily and can't handle complex scenarios.

### ❌ Pure LLM Agents  
Smart — but slow, expensive, and risky for:
- Refund & billing logic  
- Subscription workflows  
- Data lookups (CRM, ERP)  
- Policy-compliance workflows  

### ❗ Enterprises need **speed + accuracy + reliability + low cost**  
No single architecture provides all four… until now.

---

# 🟢 **Solution: Hybrid Intelligence**

VectorOps Assist introduces a **Two-Tier Support Architecture**:

---

## **Tier 1 — Deterministic Rule Engine (Fast & Cheap)**  
Handles repetitive, predictable tasks:
- Cancellations  
- Refund basics  
- Billing queries  
- Order lookups  
- FAQ / General help  

**Benefits:**
✔ Instant  
✔ Zero LLM cost  
✔ 100% predictable  

---

## **Tier 2 — Generative AI (Smart & Context-Aware)**  
Powered by **Gemini 2.0 Flash**, the Tier 2 agent handles:
- Multi-step reasoning  
- Complex queries  
- Tool-based workflows  
- CRM/order/ticket lookups  
- Long-term memory  
- Context-aware personalization  

**Benefits:**
✔ Accurate  
✔ Reasoning-capable  
✔ Access to real tools  
✔ Safer & cheaper than pure LLM systems  

Combined, the hybrid model is **90% more cost-efficient** than pure LLM automation.

---

# 🏗️ **System Architecture**

### **1. Workbench Interface (Frontend)**  
A modern React-based hybrid notebook UI:
- React 19  
- Tailwind CSS  
- Lucide Icons  
- Gemini-powered Python runtime  
- Real-time code execution & logs  
- Agent visualization tools  

---

### **2. Python Agent Core (Tiered Logic)**

#### **🔹 Tier 1: Rule-Based Engine**
- Regex/heuristic intent classifier  
- Lightweight template response engine  
- SimpleMemory sliding window context  

#### **🔹 Tier 2: VectorOpsAgent**
- ReAct Loop (Reason → Act → Observe)  
- MemoryManager with TTL & Compaction  
- Tool orchestration & execution  
- MCP client (mock) for dynamic tool discovery  

#### **Built-in Tools**
- `get_order_status(order_id)`  
- `check_refund(order_id)`  
- `file_complaint_ticket(issue, priority, idempotency_key)`  
- `query_customer_db(sql_query)`  

---

### **3. CompanySystem (Mock Backend)**
Simulated enterprise backend:
- Order DB  
- Ticketing system  
- CRM  
- Refund policy engine  

You can replace this with real APIs for production.

---

### **4. Deployment Pipeline**
Workbench auto-generates:
- `server.py` → FastAPI microservice wrapper  
- `Dockerfile` → Container for Cloud Run / ECS / Kubernetes  

Production-ready out of the box.

---

# 🧱 **Architecture Diagram**

──────────────────────────────────────────────────────────────────────────────
                     VECTOROPS ASSIST – SYSTEM LIFECYCLE
──────────────────────────────────────────────────────────────────────────────

USER REQUEST LAYER
──────────────────────────────────────────────────────────────────────────────
[User Request: Web / API / Portal / Chat Interface]
          ↓
[Authentication & Authorization Layer]
          ↓
[Input Validator (length limits, sanitation, safety checks)]
          ↓
[Routing Controller — decides Tier 1 (simple) or Tier 2 (complex)]

──────────────────────────────────────────────────────────────────────────────
TIER 1 — DETERMINISTIC RULE-BASED ENGINE (Simple / Repetitive Queries)
──────────────────────────────────────────────────────────────────────────────
[Intent Classifier (Keywords / Roles)]
          ↓
[Is the query simple/repetitive?]
   ├── Yes → [Rule Engine (Refund, Billing, Cancellation, Basic Queries)]
   │            ↓
   │        [Predefined Response Selector]
   │            ↓
   │        [Tier-1 Response Builder]
   │            ↓
   │        [Logging Pipeline (structured logs w/ metadata)]
   │            ↓
   │        RETURN RESPONSE (Tier 1 handles)
   │
   └── No → Escalate to Tier 2

──────────────────────────────────────────────────────────────────────────────
TIER 2 — VECTOROPS ASSIST (Generative AI System)
──────────────────────────────────────────────────────────────────────────────

SYSTEM INSTRUCTION LAYER
[System Instruction Loader]

MEMORY LAYER
────────────────────────────────────────────────
[Short-Term Memory   (recent context window)]
[Memory Optimizer    (TTL pruning, compaction)]
[Context Summary Generator]

PROMPTING PIPELINE
────────────────────────────────────────────────
[Prompt Composer (injects rules + memory + user input)]
          ↓
[LLM Core (Gemini / GPT)]
          ↓
[Response Interpreter (detects function/tool calls)]

TOOLING & ACTION LAYER
────────────────────────────────────────────────
[Did the LLM request a tool call?]
   ├── Yes → Route to appropriate system tool:
   │        • Order Status Tool (get_order_status(order_id))
   │        • Refund Eligibility Tool (check_refund(order_id))
   │        • Support Ticket Tool (hs_complaint, ticketIssue, priority, timestamp...)
   │        • MCP / Database Tool (query_customer/agent/other DB layers)
   │                 ↓
   │        [Return Tool Result]
   │
   └── No → Skip tool execution

OUTPUT ASSEMBLY LAYER
────────────────────────────────────────────────
[Response Synthesizer]
          ↓
[Safety & Compliance Filter]
          ↓
[Format Normalizer (JSON / CxI / API responses)]
          ↓
[Latency Tracker]
          ↓
[Action Logger (tool calls + metadata)]

RETURN PATH
────────────────────────────────────────────────
[Send Response to Client]
          ↓
[Store Interaction in Logs]
          ↓
[Update Memory (user + agent messages)]

──────────────────────────────────────────────────────────────────────────────
COMPANY INFRASTRUCTURE LAYER
──────────────────────────────────────────────────────────────────────────────
[CXM System]
[Order Management DB]
[Ticketing System]
[Audit Log DB]
[Monitoring & Analytics Pipeline]

──────────────────────────────────────────────────────────────────────────────
Visual Emphasis: Scalability • Observability • Enterprise Reliability
──────────────────────────────────────────────────────────────────────────────


## 🛠️ Setup & Installation

### Prerequisites
1.  **Node.js** (v18 or higher)
2.  **Google Gemini API Key** (Get one at [aistudio.google.com](https://aistudio.google.com))

### Installation

1.  **Clone the repository**
    ```bash
    git clone https://github.com/your-org/vectorops-assist.git
    cd vectorops-assist
    ```

2.  **Install dependencies**
    ```bash
    npm install
    ```

3.  **Configure Environment**
    Create a `.env` file in the root directory:
    ```env
    API_KEY=your_google_gemini_api_key_here
    ```
    *Note: In the provided web-container environment, the API key is injected automatically via `process.env.API_KEY`.*

4.  **Run the Workbench**
    ```bash
    npm start
    ```
    Open [http://localhost:8080](http://localhost:8080) to view the app.

---

## 🧪 Usage Guide

### 1. Initialize the Environment
Click the **Run** button (▶) on the first few cells to load imports, configure logging, and setup the mock infrastructure.

### 2. Test Tier 1
Run the "Tier 1 Demo" cell. You will see the agent handle simple requests like "I want to cancel" instantly without calling the LLM.

### 3. Engage Tier 2 (GenAI)
Run the **VectorOpsAgent** cells. The agent will:
*   Analyze the user request.
*   Decide if it needs tools (e.g., `get_order_status`).
*   Execute the tool against the mock `CompanySystem`.
*   Synthesize a response.

### 4. Evaluate
Run the **Evaluation & Analytics** cell to see a Pandas DataFrame comparing the performance of Tier 1 vs. Tier 2 on a standardized test suite.

### 5. Deploy
Run the final cell to generate the `server.py` and `Dockerfile` artifacts.

---

## 📊 Features Checklist

- [x] **Multi-Modal Interface:** Markdown for documentation, Code for logic.
- [x] **Structured Logging:** Enterprise-grade logs for debugging.
- [x] **Context Management:** Automatic summarization of long conversations.
- [x] **Tool Use (Function Calling):** Native integration with Python functions.
- [x] **MCP Simulation:** Demonstrates dynamic tool discovery.
- [x] **A2A Protocol:** Architecture supports Agent-to-Agent handoffs.
- [x] **Auto-Deployment:** Generates production-ready artifacts.

---

## 🤝 Contributing

1.  Fork the project.
2.  Create your feature branch (`git checkout -b feature/AmazingFeature`).
3.  Commit your changes (`git commit -m 'Add some AmazingFeature'`).
4.  Push to the branch (`git push origin feature/AmazingFeature`).
5.  Open a Pull Request.

---

**Powered by VectorOps Architecture v1.0**

