# 🧳 LangGraph Travel Planner Agent

A modular travel planning agent built using **LangGraph**, with real-time **IRCTC train fare integration**, mock hotel listings (upgradeable to Booking.com), and dynamic transport cost estimators. Designed for **agentic orchestration**, easy API extension, and deployment-readiness.

---

## 🚀 Features

| Module        | Description                                                                 |
|---------------|-----------------------------------------------------------------------------|
| 🏨 Hotels      | City-based hotel lookup with clickable booking links (mock, API upgradeable) |
| 🚆 Train Fare  | Real-time IRCTC fare via RapidAPI                                           |
| ✈️🚌🚗 Transport | Static cost estimators for flight, bus, and self-drive                      |
| 🔗 Links       | Embedded IRCTC, RedBus, MakeMyTrip, Booking.com URLs                        |
| 💬 Output      | Markdown-formatted reply with hotel/transport costs and booking suggestions |
| 🔧 Agent Flow  | LangGraph flow with sequential hotel → transport → formatter nodes          |

---

## 🛠️ Setup Instructions

1. **Clone the repo**

    ```bash
    git clone https://github.com/YOUR_USERNAME/langgraph-travel-agent.git
    cd langgraph-travel-agent
    ```

2. **Install dependencies**

    Recommended: Python 3.11+

    ```bash
    pip install langgraph requests
    ```

3. **Set your IRCTC RapidAPI key**

    Replace in `get_train_cost()` function:

    ```python
    "X-RapidAPI-Key": "your-rapidapi-key"
    ```

---

## 🧪 Run the Agent

```python
from agent import agent

sample_input = {
    "from_city": "Delhi",
    "to_city": "Jaipur",
    "distance_km": 270,
    "budget": 5000,
    "travel_date": "2025-08-15",
    "transport_mode": "train"
}

reply = agent.invoke(sample_input)
print(reply["formatted_reply"])
