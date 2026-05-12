# STEM AI Agent

## About
AI agent that becomes specialized for solving a class of problems based on user request. 

<img src = "STEM Agent.png" width = "700">

## Workflow
- User writes desired agent description
- **Agent Builder** takes tools needed from tools database and builds agents system prompt
- System prompt is being passed to **STEM Agent** and **evaluation task** is being created
- **STEM Agent** is created from **Planner** and **Orchestrator** agents
- **Planner** creates step-by-step task execution plan
- **Orchestrator** follows the plan in steps and communicates between available tools
- **STEM Agent** solves the task and passes solution to **Evaluation Agent**
- **Evaluation agent** decides if agent needs to be rebuilt or its ready for execution
- **Rebuild phase** restarts from **Agent Builder**
- **Execution phase** starts from **User task prompt**


## Quick Start
- **Agent description** and **user task prompt** need to be set up before workflow execution
- First **Edit Fields** node parameter "agent description" is description of wanted agent (eg. AI agent that will search the internet for latest trends.)
- **User task prompt** node "task" parameter is specific task for custom agent (eg. Research the latest EV trends.)
- Task solution will be displayed in **Final Output** node
- If AI agent can't be realistically created based on agent description with currently implemented tools, error message will be displayed in **Error: Agent can't be built** node

## Requirements
- n8n workflow automation tool
- OpenAI API key with write permission

## Installation
- In n8n select import workflow from JSON
- In **Message a model** and **AI Agent** nodes set up OpenAI API credentials
