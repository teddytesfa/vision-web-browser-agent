# Vision & Browser Agent

An intelligent AI agent that combines vision capabilities with web browser automation to perform complex research and verification tasks. Built with `smolagents` and Selenium, this agent can search the web, navigate websites, analyze visual content, and extract information autonomously.

## 🌟 Features

- **Vision-Powered Web Navigation**: Captures and analyzes screenshots at each step to understand page content
- **Intelligent Search**: Integrates DuckDuckGo search for finding relevant information
- **Browser Automation**: Uses Helium and Selenium for seamless web interaction
- **Multi-Model Support**: Compatible with various LLM providers (OpenAI, LiteLLM, Transformers, etc.)
- **Custom Tools**: Includes specialized tools for page search, navigation, and popup handling
- **Memory Management**: Optimizes screenshot storage to maintain lean processing
- **Step-by-Step Execution**: Breaks down complex tasks into manageable actions with visual feedback

## 🛠️ Technologies

- **smolagents**: AI agent framework for building autonomous agents
- **Selenium & Helium**: Browser automation and control
- **PIL (Pillow)**: Image processing and screenshot handling
- **LiteLLM**: Multi-provider LLM integration
- **DuckDuckGo Search API**: Web search capabilities

## 📋 Prerequisites

- Python 3.8+
- Chrome browser installed
- API key for your chosen LLM provider (e.g., OpenAI, Google Gemini)

## 🚀 Installation

1. Clone this repository:
```bash
git clone <your-repo-url>
cd <repo-directory>
```

2. Install required dependencies:
```bash
pip install smolagents selenium helium pillow python-dotenv
```

3. Set up your environment variables:
Create a `.env` file in the project root:
```
OPENAI_API_KEY=your_api_key_here
# Or use other providers like Google Gemini, Anthropic, etc.
```

## 💡 Usage

### Basic Usage

Run with the default product verification example:
```bash
python vision_web_browser.py
```

### Custom Prompts

Provide your own task:
```bash
python vision_web_browser.py "Search for the latest Tesla Model 3 specifications and compare prices across different websites"
```

### Specify Different Models

Use OpenAI GPT-4:
```bash
python vision_web_browser.py --model-type LiteLLMModel --model-id gpt-4o
```

Use Google Gemini:
```bash
python vision_web_browser.py --model-type LiteLLMModel --model-id gemini/gemini-1.5-pro
```

### Command Line Arguments

- `prompt`: The task description for the agent (optional, uses default if not provided)
- `--model-type`: The model provider type (default: `LiteLLMModel`)
- `--model-id`: The specific model to use (default: `gpt-4o`)

## 🔧 How It Works

1. **Initialization**: Sets up Chrome browser with optimized settings and initializes the AI agent
2. **Task Processing**: Agent receives a natural language task and plans its approach
3. **Tool Execution**: Uses available tools (search, navigation, clicking, scrolling) to complete the task
4. **Visual Feedback**: Captures screenshots after each action to understand the current state
5. **Memory Management**: Maintains recent screenshots while discarding older ones for efficiency
6. **Result Delivery**: Returns findings in a structured format

## 🎯 Example Use Cases

- **Product Research**: Verify product specifications and appearance before purchase
- **Price Comparison**: Navigate multiple e-commerce sites to compare prices
- **Information Gathering**: Research topics across multiple authoritative sources
- **Visual Verification**: Confirm visual elements and design details on websites
- **Competitive Analysis**: Analyze competitor websites and extract key information

## 🔍 Built-in Tools

### `search_item_ctrl_f(text, nth_result)`
Searches for text on the current page and scrolls to the nth occurrence.

### `go_back()`
Navigates to the previous page in browser history.

### `close_popups()`
Dismisses modal dialogs and popups using ESC key.

### `DuckDuckGoSearchTool()`
Performs web searches to find relevant URLs and information.

## 📸 Screenshot Management

The agent automatically:
- Captures screenshots after each action
- Stores them in the agent's memory for visual analysis
- Removes old screenshots (older than 2 steps) to optimize memory usage
- Includes current URL information with each screenshot

## ⚙️ Configuration

### Browser Settings
The Chrome browser is configured with:
- Window size: 1000x1350 pixels
- Scale factor: 1 (for consistent screenshots)
- PDF viewer disabled
- Non-headless mode (visible browser window)

### Agent Settings
- Max steps: 20 (prevents infinite loops)
- Verbosity level: 2 (detailed logging)
- Authorized imports: `helium` (for browser control)

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests
- Improve documentation

## 👤 Author

Built by Teddy Tesfa.

## 🙏 Acknowledgments

- [smolagents](https://github.com/huggingface/smolagents) - AI agent framework
- [Helium](https://github.com/mherrmann/selenium-python-helium) - Simplified Selenium wrapper
- Hugging Face Agent Course - Learning resource

---

**Note**: This agent requires active internet connection and may interact with real websites. Always ensure you comply with websites' terms of service and robots.txt when using automated browsing tools.
