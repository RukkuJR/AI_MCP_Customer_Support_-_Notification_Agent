# 🤖 N8N AI-Powered Customer Support Automation

An intelligent email processing and notification system that automatically classifies incoming emails, prioritizes customer support requests, and distributes notifications across multiple platforms (Slack, Telegram) while maintaining proper email management workflows.

## 🎯 Project Overview

This automation system transforms traditional email management into an AI-driven, multi-channel notification system that ensures no high-priority customer support request goes unnoticed. The workflow intelligently processes Gmail messages, categorizes them using AI, and routes them through appropriate channels based on priority levels.

## 🏗️ Architecture & Workflow

<img width="1328" height="598" alt="server" src="https://github.com/user-attachments/assets/a8238db7-ee03-411c-bba8-6edb9aeaf335" />

### Core Components

1. **Gmail Trigger** - Monitors incoming emails in real-time  
2. **AI Text Classifier** - Powered by Google Gemini for intelligent email categorization  
3. **MCP Server Integration** - Flexible, reusable communication protocols  
4. **Multi-Platform Notifications** - Slack, Telegram, and Gmail responses  
5. **Memory Management** - Persistent data storage for context and history  

### Workflow Process

```
Gmail → AI Classification → Priority Routing → Multi-Channel Notifications
   ↓           ↓                ↓                    ↓
Email      Categories:      High Priority      Slack + Telegram
Trigger    • High Priority   Handling          + Gmail Actions
           • Promotion       
           • Finance/Billing  
           • Customer Support
           • Personal
```

## 🧠 AI Agent Details

### **Primary AI Agent: Google Gemini Chat Model**

**Role**: Email Classification and Content Analysis  

- **Function**: Analyzes email content, sender information, and context to determine appropriate category and priority level  

- **Categories Handled**:  
  - **High Priority**: Urgent customer issues, system outages, critical business matters  
  - **Customer Support**: General inquiries, feature requests, bug reports  
  - **Finance/Billing**: Payment issues, invoice queries, subscription matters  
  - **Promotion**: Marketing emails, newsletters, promotional content  
  - **Personal**: Non-business related communications  

## 🔄 MCP (Model Context Protocol) Implementation

### What is MCP in This Context?

MCP serves as the backbone communication protocol that enables seamless integration between different services and AI models in our automation pipeline. It provides a standardized way for our AI agents to interact with various tools and services.

### MCP Architecture Benefits

GMAIL MCP SERVER
<img width="1157" height="392" alt="gmail_mcp_server" src="https://github.com/user-attachments/assets/f4c8de39-10b7-4423-a6dd-19d2bfcadf06" />

TELEGRAM MCP SERVER

<img width="540" height="512" alt="telegram_mcp_server" src="https://github.com/user-attachments/assets/077a3581-292a-4e8c-bcf1-27e0e12ad591" />

SLACK MCP SERVER

<img width="672" height="427" alt="slack mcp server" src="https://github.com/user-attachments/assets/e63ea4eb-54bc-47fe-8f99-ba697ef2f134" />

#### **1. Scalability**

```
Single MCP Server → Multiple Service Endpoints
     ↓
Gmail MCP ← → Telegram MCP ← → Slack MCP
     ↓              ↓              ↓
  Tool Layer    Tool Layer    Tool Layer
```

- **Horizontal Scaling**: Add new communication channels without modifying core logic  
- **Service Isolation**: Each MCP component operates independently  
- **Load Distribution**: Parallel processing across multiple MCP instances  

#### **2. Flexibility & Reusability**

**Modular Design**:  
- **Gmail MCP**: Handles email operations (read, label, reply, mark as read/unread)  
- **Telegram MCP**: Manages bot messaging and chat interactions  
- **Slack MCP**: Controls workspace notifications and channel management  
- **Memory MCP**: Persistent storage for context and workflow history  

#### **3. Why MCP for This Project**

**Traditional Approach Problems**:  
- Hardcoded integrations between services  
- Difficult to maintain and update  
- Limited reusability across projects  
- Complex error handling and retry mechanisms  

**MCP Solutions**:  
- **Standardized Communication**: All services speak the same "language"  
- **Error Resilience**: Built-in retry and fallback mechanisms  
- **Context Preservation**: Maintains conversation and workflow state  
- **Easy Extension**: Add new services by implementing MCP interface  

## 📋 Current Features

### AI Agent Central Controller Prompt

<img width="661" height="617" alt="Central Agent Prompt" src="https://github.com/user-attachments/assets/26b323a7-8763-4548-9f6f-1759522bc63b" />


### Email Processing

- ✅ Real-time Gmail monitoring  
- ✅ AI-powered email classification (5 categories)  
- ✅ Automatic labeling system  
- ✅ Smart reply generation for high-priority emails  
- ✅ Read/unread status management  

### Notification System

- ✅ Slack channel notifications with formatted messages  
- ✅ Telegram bot messaging with summarized content  
- ✅ Context-aware message formatting  
- ✅ Priority-based notification routing  

### Workflow Management

- ✅ Automated high-priority email escalation  
- ✅ Memory storage for conversation context  
- ✅ Error handling and retry mechanisms  
- ✅ Workflow execution logging  

### Prerequisites

- n8n instance (cloud or self-hosted)  
- Gmail API access and credentials  
- Slack workspace and bot token  
- Telegram bot token and chat ID  
- Google Cloud Platform account (for Gemini API)

### Output

<img width="1382" height="733" alt="gmail_auto_label_and_reply" src="https://github.com/user-attachments/assets/343c3741-8e3f-4ab7-97a9-81e68e617072" />
<img width="1642" height="852" alt="telegram_chat" src="https://github.com/user-attachments/assets/392dfaaf-132b-45a9-8d25-c559382fdbe9" />
<img width="1880" height="602" alt="slack_chat_message" src="https://github.com/user-attachments/assets/71ad158c-6ade-407c-ab99-7db03932f8b3" />







