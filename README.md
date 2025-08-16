# PitchScribe ✍️

<div align="center">

_AI-powered tool to generate professional, VC-grade investment memos in seconds._

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8+-blue.svg" alt="Python Version">
  <img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License">
  <img src="https://img.shields.io/badge/Built%20with-LangChain-purple.svg" alt="LangChain">
  <img src="https://img.shields.io/badge/Powered%20by-OpenAI-black.svg" alt="OpenAI">
</p>

---

**PitchScribe** helps investors, founders, and analysts quickly create structured, venture-capital-grade investment memos using Large Language Models (LLMs). The tool prompts you for startup details, generates a polished and insightful memo, saves it locally, and can even deliver it directly to your inbox.

## 🚀 Features

-   🤖 **AI-Powered Memo Generation**: Leverages cutting-edge LLMs to create comprehensive and structured investment memos.
-   💬 **Custom Prompts & Follow-ups**: Easily input company details or ask follow-up questions to generate deeper insights.
-   🧠 **Conversation Memory**: Retains context throughout your session using LangChain’s powerful memory module.
-   💾 **Flexible Export Options**: Save your generated memos as clean `.txt` files for easy access and sharing.
-   📧 **Email Integration**: Send memos directly from the command line using a secure SMTP connection.
-   ⚙️ **Easy Setup**: Get up and running in minutes with minimal configuration.

---

## 🛠️ Getting Started

Follow these steps to set up and run PitchScribe on your local machine.

### 📦 Prerequisites

Before you begin, ensure you have the following:

-   **Python 3.8+**
-   An **OpenAI API Key**. You can get one from the [OpenAI Platform](https://platform.openai.com/).
-   The following Python libraries:
    -   `openai`
    -   `langchain`
    -   `smtplib`
    -   `ssl`
    -   `datetime`

### ⚙️ Installation & Configuration

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/pitchscribe.git](https://github.com/yourusername/pitchscribe.git)
    cd pitchscribe
    ```

2.  **Install dependencies:**
    It's recommended to use a virtual environment.
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    pip install -r requirements.txt
    ```

3.  **Add your OpenAI API Key:**
    Open the script and find the following line to add your key.
    ```python
    # WARNING: It's recommended to use environment variables for production.
    os.environ["OPENAI_API_KEY"] = "your_api_key_here"
    ```
    > **⚠️ Important**: Do not commit your API key to a public repository.

4.  **Configure your email (Optional):**
    If you want to use the email feature, configure your SMTP server details inside the `sendEmail` function.
    ```python
    smtp_server = "smtp.gmail.com"  # Example for Gmail
    port = 587  # For starttls
    ```
    > **Note**: Yahoo is not supported. For Gmail, you may need to enable "Less secure app access" or generate an "App Password" for your account.

---

## ▶️ How to Use

Run the script directly from your command line:

```bash
python pitchscribe.py
The application will prompt you for:

Company/startup details to analyze.

Sender & receiver email addresses (if you choose to send the memo).

A filename to save the memo locally.

The script will then:

Generate a comprehensive investment memo.

Save it as a .txt file in the project directory.

Optionally, send the memo to the specified recipient via email.

👉 You can also ask additional questions about the company after the initial memo is generated. PitchScribe will use the conversation history to provide context-aware insights in real-time.

📝 How It Works
LangChain: Manages the core LLM pipeline, from prompting to response generation.

LLMChain + PromptTemplate: Handle the creation of dynamic, structured prompts based on user input.

ConversationBufferMemory: Stores the session history, allowing for context-aware follow-up questions.

SMTP + SSL: Ensure the secure delivery of memos via email.

saveMemo function: Handles the local saving of generated memos for future reference.

🔮 Future Roadmap
[ ] Enhanced Export Options: Add support for PDF and Docx formats.

[ ] Cloud Integrations: Connect with Notion and Google Docs for seamless workflow integration.

[ ] Collaboration Features: Introduce multi-user support for team-based memo creation.

[ ] Web Interface: Develop an interactive web-based UI using Streamlit or Gradio.

📄 License
This project is licensed under the MIT License. See the LICENSE file for more details.