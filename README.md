# 🛒 Shopify Dropshipping Business Automation

An **AI-powered n8n workflow** that turns Telegram into a full Shopify store management interface. Send natural language commands in English or Bangla — the AI agent handles the rest.

![Workflow Preview](Shopify_Dropshipping_Businees_Automation.png)

---

## ✨ Features

- 📦 **Product Management** — View, create, and update products
- 🧾 **Order Management** — Fetch, update, and delete orders
- 🤖 **AI-Powered** — Powered by Google Gemini via n8n LangChain agent
- 💬 **Telegram Interface** — Chat-based control from anywhere
- 🧠 **Conversation Memory** — Remembers context across messages (50-message window)
- 🌐 **Multilingual** — Understands English, Bangla, and Banglish commands
- 🔒 **Safety-First** — Confirms before any destructive write action

---

## 🧱 Workflow Architecture

```
Telegram Trigger
      │
      ▼
  AI Agent (LangChain)
  ├── 🧠 Google Gemini (LLM)
  ├── 💾 Simple Memory (Buffer Window)
  └── 🛠 Shopify Tools:
       ├── Get Many Products
       ├── Get Many Orders
       ├── Create a Product
       ├── Update an Order
       ├── Delete an Order
       └── Update a Product
      │
      ▼
Telegram — Send Response
```

---

## 🛠 Tech Stack

| Component | Tool |
|-----------|------|
| Automation Platform | [n8n](https://n8n.io) |
| AI Model | Google Gemini (PaLM API) |
| Chat Interface | Telegram Bot |
| E-commerce | Shopify Admin API |
| Memory | n8n LangChain Buffer Window |

---

## ⚙️ Setup Instructions

### 1. Prerequisites

- n8n instance (self-hosted or cloud)
- Telegram Bot Token (via [@BotFather](https://t.me/BotFather))
- Google Gemini API Key
- Shopify Access Token (with required scopes)

### 2. Required Shopify API Scopes

```
read_products, write_products
read_orders, write_orders
read_inventory, write_inventory
read_customers, write_customers
read_analytics, read_reports
read_discounts, write_discounts
read_shipping, write_shipping
read_content, write_content
read_themes, write_themes
```

### 3. Import the Workflow

1. Open your n8n instance
2. Go to **Workflows → Import**
3. Upload `Shopify_Dropshipping_Businees_Automation.json`

### 4. Configure Credentials

| Credential | Where to Get |
|------------|-------------|
| `Telegram account` | [BotFather](https://t.me/BotFather) → `/newbot` |
| `Google Gemini (PaLM) API account` | [Google AI Studio](https://aistudio.google.com/) |
| `Shopify Access Token account` | Shopify Admin → Apps → Private Apps |

### 5. Activate

Toggle the workflow to **Active** in n8n.

---

## 💬 Example Commands

| Command | Action |
|---------|--------|
| `Show all products` | Lists all Shopify products |
| `product gula dekhao` | Lists all products (Banglish) |
| `Get all pending orders` | Fetches unfulfilled orders |
| `Create product: Blue T-Shirt` | Creates a new product |
| `Update order #1234` | Updates an order |
| `Delete order 5678` | Deletes order (with confirmation) |
| `আজকে কত সেল হয়েছে?` | Asks about today's sales (Bangla) |

---

## 🔒 Safety Rules

The AI agent enforces the following before any write operation:

- ✅ Intent is clearly understood
- ✅ All required data is provided
- ✅ Explicit user confirmation received

Example confirmation prompt:
```
⚠️ Confirm deleting order #1234? Reply YES to proceed.
```

---

## 📁 File Structure

```
├── Shopify_Dropshipping_Businees_Automation.json   # n8n workflow export
├── Shopify_Dropshipping_Businees_Automation.png    # Workflow screenshot
└── README.md
```

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you'd like to change.

---

## 📄 License

MIT License — feel free to use and adapt for your own projects.

---

## 🙋 Support

If you found this useful, consider giving this repo a ⭐ on GitHub!
