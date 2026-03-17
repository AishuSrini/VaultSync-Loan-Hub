# VaultSync-Loan-Hub
A zero-code, AI-first loan origination platform using SharePoint Premium and multi-agent Copilot architecture.
# 🏦 **VaultSync: Master Agent Loan Origination Hub 🤖🔗**

The **VaultSync Loan Origination Hub** project is an **enterprise-grade implementation of master agent orchestration using Microsoft Copilot Studio and SharePoint**. It leverages various **services such as SharePoint Premium, specialized SharePoint agents, and Power Automate to create an interactive orchestrator** that helps users automate commercial loan underwriting. The system extracts text from loan files, securely passes data via **agent-to-agent communication, and generates decision packages exponentially faster using advanced, multi-language AI models**.
<img width="2816" height="1536" alt="Gemini_Generated_Image_irred6irred6irre" src="https://github.com/user-attachments/assets/36a59346-a579-451f-95c7-10ac49726939" />

# 🌟 **Features**

 **⚙️ Master Agent Orchestration:** Implements a Master Orchestrator pattern to create a robust Question Answering (QA) system that intelligently routes user intents to specialized child agents based on retrieved data.

**🤖 Agent-to-Agent Communication:** Splits AI responsibilities into specific domains (KYC, Credit, Collateral) where the master orchestrator seamlessly synthesizes outputs from multiple SharePoint agents to optimize the compliance process and improve retrieval accuracy.

**📄 SharePoint Premium Autofill:** Extracts raw text from commercial loan documents in PDF format and maps it to structured columns for easy retrieval.

**🛡️ Enterprise-Grade Security:** Uses strict SharePoint grounding and Microsoft 365 RBAC to generate highly secure responses. This ensures AI models only access authorized, compliant banking policies without leaking data across silos.

**⚡ Exponentially Faster Processing:** Transforms multi-day manual underwriting and document reviews into an automated process that takes seconds.

**🌍 Multi-Language Support:** Dynamically understands and translates user queries across different languages (e.g., switching from English to Spanish mid-workflow) while retaining complex conversational memory.

**🧠 Optimized System Prompts:** Utilizes advanced prompt engineering to strictly bound each SharePoint agent, preventing AI hallucinations and enforcing strict regulatory compliance.

**🔗 Power Automate Chain:** Utilizes Power Automate to implement a workflow that retrieves relevant synthesized data from the orchestrator and generates accurate decision packages.

**🗨️ Interactive Teams Interface:** Provides an interactive Adaptive Card interface in Microsoft Teams for managers to interact with the system in real-time and approve or reject loan packages securely.
# **🛠️ Installation**
# **Clone the repository:**
```
git clone https://github.com/your-username/VaultSync-Loan-Hub.git

cd VaultSync-Loan-Hub
```

# **🛠️ Configuration & Deployment**
Because this is a zero-code Microsoft 365 solution, deployment involves configuring the tenant environments rather than running Python scripts.

📸 Image Suggestion: Upload a screenshot of your SharePoint Document Library showing the Premium Autofill columns (Applicant Name, Loan Amount).

**1. SharePoint Environment Configuration:**

Configure your SharePoint Communication Site (VaultSync Loan Origination Hub) and create your strictly isolated document library folders.
```
LIBRARY_FOLDERS = [
  '1_KYC_Rules', 
  '2_Credit_Policy', 
  '3_Property_Zoning', 
  '4_Active_Applications'
]
```
# **SharePoint Premium:** Configure the 4_Active_Applications folder with Autofill columns to extract Applicant Name, Loan Amount, and Risk Tier upon document upload.

# **2. SharePoint Agent Configuration:**

Create three specialized Declarative Agents directly in the SharePoint UI.

Grounding: Restrict each agent's knowledge base only to its corresponding folder (e.g., The KYC Agent is grounded strictly to 1_KYC_Rules).

**Prompt Instructions:**

```
KYC_AGENT_PROMPT = "You are a strict compliance officer. You only evaluate applicants against the KYC rules provided in your sources. Do not answer credit questions."
```
# **3. Master Orchestrator Configuration (Copilot Studio):**

📸 Image Suggestion: Upload a screenshot of Copilot Studio showing the "Actions" tab with your three SharePoint Agents added.

# **Create a Copilot named Master Loan Orchestrator.**

Actions: Add your three Declarative Agents as callable actions.

Routing Prompt: 
```text
ORCHESTRATOR_PROMPT = "You are the Master Loan Orchestrator. Never answer loan questions directly. Analyze the user intent and route KYC questions to the KYC Agent, credit to the Credit Agent. Synthesize their responses."
```

### **4. Power Automate & Teams Configuration:**
> 📸 **Image Suggestion:** *Upload a screenshot of your Power Automate flow showing the "When Copilot triggers a flow" step connecting to the Teams Adaptive Card.*

Configure your Power Automate flow to trigger from Copilot, populate a Word document, and post to Microsoft Teams:
```text
TRIGGER = 'Run from Copilot'
TEAMS_CHANNEL = 'Underwriting_Review_Channel'
APPROVAL_TYPE = 'Approve/Reject - First to Respond'
```
🖥️ # **Usage**
**1. Prepare the Loan Documents:** Place the PDF files of your commercial loan applications in the 4_Active_Applications folder. By default, SharePoint Premium will extract the required metadata automatically.

**2. Run the Application:** Start the interaction by opening the Copilot chat pane on your SharePoint Hub:


Click the Copilot icon in the top right corner of your SharePoint site.
**3. Interact with the Orchestrator:** The orchestrator will load the loan files, route intents, and set up the agent chain. You can then type questions to interact with the bot. For example:


**User:** What Risk Tier does a $500,000 loan fall into for Acme Corp?
**Assistant:** [Bot Response Based strictly on the 2_Credit_Policy folder]
**4. Execute the Business Workflow:** To trigger the approval flow, use a prompt like "Generate a loan decision package" or test the multi-language feature by typing: "Genera un paquete de decisión de préstamo."

🤖# **Demo:**
**Watch a Demo Video:**
[https://youtu.be/nA5VaHmSwnk] (Insert your YouTube link here)

🧠 # **How it Works**
📸 Image Suggestion: Upload a GIF or screenshot of the Teams Adaptive Card with the Approve/Reject buttons.

**Data Extraction:** Uses SharePoint Premium Autofill to extract metadata from the uploaded loan documents.

**Master Agent Routing:** Copilot Studio is used to analyze user intents and securely route queries via agent-to-agent handoffs to the specific SharePoint agents.

**Retrieval Augmentation & Security:** The orchestrator utilizes Strict SharePoint Grounding to efficiently retrieve the most relevant sections of the bank's policies based on user queries. This security-first approach allows the AI to search through highly regulated documents accurately without hallucinating.

**Power Automate Integration:** Power Automate is used to connect the AI responses with business workflows, enabling the system to take the synthesized data from the user queries. The automation flow then uses this retrieved data to generate a Word document and an Adaptive Card much faster than manual entry.

⛓️ **Copilot Studio orchestrates** the process, ensuring the correct data is retrieved and fed into the right declarative agent using optimized prompts.

📝 **The Adaptive Card** (provided to Microsoft Teams) ensures that the final decision is coherent, compliant, and securely handled by a human manager.

🛠 **Example Questions**
What is the KYC status for Acme Corp?

Based on I-2 zoning, is an environmental audit required?

What Risk Tier does a $500,000 loan fall into?

Todo se ve perfecto. Por favor genera el paquete de decisión de préstamo.

👥 # **Contributing**
Contributions to this project are welcome! To contribute, please follow these steps:

Fork the repository.

Create a new branch.

Make your changes.

Push your changes to your fork.

Submit a pull request.

📜 # **License**
This project is released under the MIT License.
