# Monday AI Agent - Advanced Board Management with n8n

![n8n](https://img.shields.io/badge/n8n-Workflow-orange)
![Anthropic](https://img.shields.io/badge/AI-Claude_Sonnet-purple)

A sophisticated n8n workflow that creates an AI-powered assistant for Monday.com board management using natural language commands. This project leverages the Model Context Protocol (MCP) and Anthropic Claude AI to provide an intuitive interface for managing your Monday.com boards.

## 🌟 Features

- **Natural Language Interface**: Control your Monday.com boards using simple, conversational commands
- **Powerful AI Backend**: Utilizes Anthropic Claude Sonnet for understanding user intent and executing appropriate actions
- **Comprehensive Board Management**: 
  - Update task statuses, owners, due dates, emails, and notes
  - Create and delete items
  - Post updates to tasks
  - Query items by status
- **Secure Environment Configuration**: All sensitive information stored in environment variables
- **Enhanced User Experience**: Get immediate confirmation and feedback after each action

## 🔧 Technical Stack

- **n8n**: Workflow automation platform
- **Monday.com API**: For board/item management
- **Model Context Protocol (MCP)**: For AI-to-API integration
- **Anthropic Claude**: Advanced AI model for natural language understanding

## 📋 Prerequisites

- n8n instance (self-hosted or cloud)
- Monday.com account with API access
- Anthropic API key

## 🚀 Setup & Installation

1. **Clone this repository**
   ```bash
   git clone https://github.com/yourusername/monday-ai-agent.git
   cd monday-ai-agent
   ```

2. **Configure environment**
   - Copy `.env.example` to `.env`
   - Fill in your credentials and configuration:
     ```
     ANTHROPIC_API_KEY=your_anthropic_api_key
     MONDAY_BEARER_TOKEN=your_monday_bearer_token
     MONDAY_MCP_ENDPOINT=https://mcp.monday.com/sse
     MONDAY_BOARD_ID=your_board_id
     MONDAY_TASK_FINAL_ID=your_final_task_id
     WEBHOOK_ID=your_webhook_id
     FLOW_ID=your_flow_id
     INSTANCE_ID=your_instance_id
     EXAMPLE_EMAIL=your_example_email
     ```

3. **Import workflow to n8n**
   - Open your n8n instance
   - Go to Workflows → Import from File
   - Select the `n8n-mcp-monday.com.json` file
   - Configure the credentials using your `.env` values

4. **Activate the workflow**
   - Toggle the "Active" switch in the n8n interface

## 🖥️ Usage

The workflow is triggered when a chat message is received. Users can interact with the agent using natural language commands such as:

- "Update the status of task 'final' to 'Done'"
- "Change the due date of task 'Website redesign' to next Friday"
- "What tasks are currently in 'In Progress' status?"
- "Create a new task called 'Review marketing materials' due on October 15"

The AI agent will:
1. Process the command using Claude AI
2. Fetch necessary metadata from Monday.com
3. Execute the appropriate API calls
4. Provide confirmation when the action is complete

## 🔒 Security Notes

- Never commit your `.env` file to version control
- The `.gitignore` file is configured to prevent this
- API keys and tokens should be kept confidential

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.