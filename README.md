# smolagents_sandbox

This repository contains a sample code to build an AI agent using a combination of language models and external tools. The agents are built with smolagents. The agent performances are evaluated using a subset of the [GAIA] (https://huggingface.co/spaces/gaia-benchmark/leaderboard) benchmark.
The application is built with [Gradio](https://gradio.app/) for an interactive web interface.

## Features

- **Agent-based Question Answering**: Uses a custom agent to answer questions using tools like web search, Wikipedia lookup, Python code execution, and webpage visiting.
- **Gradio Interface**: User-friendly web UI for running the agent and submitting answers.
- **Automated Evaluation**: Fetches a set of questions, runs the agent, and submits answers for scoring.
- **Hugging Face Spaces Ready**: Includes configuration for easy deployment on Hugging Face Spaces with OAuth.

## Repository Structure

```
Agents_Assignment/
├── app.py              # Main Gradio app and agent logic
├── requirements.txt    # Python dependencies
├── README.md           # Project documentation (this file)
```

## Installation

1. **Clone the repository:**
   ```sh
   git clone https://github.com/your-username/Agents_Assignment.git
   cd Agents_Assignment
   ```

2. **(Optional) Create and activate a virtual environment:**
   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```

## Environment Variables

Before running the application, create a `.env` file in the project root and add your model/API key:

```
KEY=your_model_api_key_here
```

The value of `KEY` should correspond to the API key for the model you wish to use. For example, you can test with models like `gemini/gemini-2.0-flash` or `Qwen/Qwen3-235B-A22B-FP8`, or provide an API key for any other custom model as desired. Make sure your key matches the requirements of the selected model provider.

Replace `your_model_api_key_here` with your actual API key. This is required for the application to access the language model.

## Usage

To launch the Gradio app locally:

```sh
python app.py
```

- Open the provided local URL in your browser.
- Interact with the agent via the Gradio interface.

## Deployment on Hugging Face Spaces

This repository is ready for deployment on [Hugging Face Spaces](https://huggingface.co/spaces):

- Make sure to set the required secrets and environment variables in your Space settings if needed.
- The `app.py` file supports Hugging Face OAuth and runtime variables.
- Replace this README with the following configuration 
```
---
title: Template Final Assignment
emoji: 🕵🏻‍♂️
colorFrom: indigo
colorTo: indigo
sdk: gradio
sdk_version: 5.25.2
app_file: app.py
pinned: false
hf_oauth: true
# optional, default duration is 8 hours/480 minutes. Max duration is 30 days/43200 minutes.
hf_oauth_expiration_minutes: 480
---
```
Further check out the configuration reference at https://huggingface.co/docs/hub/spaces-config-reference

## Customization

- **Agent Logic**: Modify the agent logic in `app.py` to change the agent’s prompt, tools, or model.
- **Tools**: Add or remove tools in the agent’s toolset as needed.

## License

This project is licensed under the Apache 2.0 License.

---

For any questions or issues, please open an issue in this repository.