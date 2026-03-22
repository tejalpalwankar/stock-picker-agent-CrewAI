````md
# 📈 AI Stock Picker Agent (CrewAI)
**Multi-Agent Financial Intelligence System for Automated Investment Decisions**

---

## 📌 Overview

This project implements a **multi-agent financial analysis system** that autonomously:

- Identifies **trending companies** from real-world news  
- Performs **deep financial research**  
- Selects the **best investment opportunity**  
- Sends a **real-time push notification** with the decision  

The system uses a **hierarchical agent architecture with memory**, simulating how real investment teams collaborate and make decisions.

---

## 🧠 Architecture

```mermaid
flowchart TD
    A[User Input: Sector] --> B[Manager Agent]

    B --> C[Trending Company Finder]
    C --> D[Trending Companies List]

    D --> E[Financial Researcher]
    E --> F[Research Reports]

    F --> G[Stock Picker]
    G --> H[Best Investment Decision]

    G --> I[Push Notification Tool]
    I --> J[User Notification]

    subgraph Memory Layer
        M1[Long-Term Memory]
        M2[Short-Term Memory (RAG)]
        M3[Entity Memory]
    end

    C --> M2
    E --> M2
    G --> M1
    G --> M3
````

---

## ⚙️ How It Works

1. **Trending Company Finder**

   * Scans latest news to identify 2–3 trending companies

2. **Financial Researcher**

   * Performs detailed analysis:

     * Market position
     * Future outlook
     * Investment potential

3. **Stock Picker**

   * Evaluates all research
   * Selects the best investment
   * Provides justification

4. **Push Notification Tool**

   * Sends final decision to the user in real-time

---

## 🧩 Key Features

* Multi-agent orchestration using CrewAI
* Hierarchical task delegation via a manager agent
* Memory-enabled reasoning across sessions
* Structured outputs using Pydantic
* Real-time notification via external API
* Modular YAML-based agent and task configuration

---

## 🛠️ Tech Stack

* Python
* CrewAI
* OpenAI GPT-4o / GPT-4o-mini
* Serper API (web search)
* Pushover API (notifications)
* Pydantic
* RAG-based memory system

---

## 📂 Project Structure

```bash
stock-picker-agent/
│
├── src/stock_picker/
│   ├── crew.py              # Multi-agent orchestration
│   ├── main.py              # Entry point
│   ├── tools/
│   │   └── push_tool.py     # Notification system
│   └── config/
│       ├── agents.yaml      # Agent definitions
│       └── tasks.yaml       # Task pipeline
│
├── output/                  # Generated outputs
├── memory/                  # Persistent memory storage
├── README.md
```

---

## ▶️ Setup & Run

### 1. Install dependencies

```bash
pip install uv
crewai install
```

### 2. Configure environment variables

Create a `.env` file:

```env
OPENAI_API_KEY=your_key
SERPER_API_KEY=your_key
PUSHOVER_USER=your_user
PUSHOVER_TOKEN=your_token
```

### 3. Run the system

```bash
crewai run
```

---

## 📊 Example Use Case

**Input**

```
Sector: Technology
```

**Output**

* List of trending companies
* Detailed research reports
* Final investment decision
* Push notification with summary

---

## 🔮 Future Improvements

* Portfolio tracking and performance monitoring
* Risk scoring and ranking models
* Real-time market data integration
* Web dashboard for visualization
* Multi-sector comparative analysis

---

## ⚠️ Note

This project is based on a CrewAI template and has been extended with:

* Hierarchical agent orchestration
* Memory systems
* External tool integration
* Production-style architecture

---

## ⭐ Summary

This project demonstrates:

* Multi-agent system design
* LLM orchestration with real-world tools
* Memory-driven decision systems
* Scalable and modular AI architecture

