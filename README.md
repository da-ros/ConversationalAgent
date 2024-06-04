# Conversational Agent with LangChain and OpenAI

This project provides a functional conversational agent using LangChain and OpenAI's GPT. The agent can fetch weather data, perform Wikipedia searches, and more. This guide will walk you through the setup, usage, and best practices for using this script.

## Features

- Fetch real current temperature for a given location using the Open-Meteo API.
- Search and summarize Wikipedia articles.
- Extendable with additional tools and functionalities.

## Prerequisites

- Python 3.7+
- An OpenAI API key
- Required Python packages (listed in `requirements.txt`)

## Setup

1. **Clone the repository**

    ```bash
    git clone https://github.com/da-ros/ConversationalAgentLangChain.git
    cd ConversationalAgentLangChain
    ```

2. **Create a virtual environment**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. **Install dependencies**

    ```bash
    pip install -r requirements.txt
    ```

4. **Set up environment variables**

    Create a `.env` file in the root directory and add your OpenAI API key:

    ```
    OPENAI_API_KEY=your_openai_api_key
    ```

## Usage

1. **Running the script**

    Simply run the script to start the conversational agent:

    ```bash
    python L6-functional_conversation-student.py
    ```

2. **Example Interactions**

    - To get the current weather in San Francisco:
    
        ```python
        result = run_agent("what is the weather in sf?")
        print(result)
        ```

    - To search Wikipedia for LangChain:
    
        ```python
        result = run_agent("what is langchain?")
        print(result)
        ```

    - To interact with the chatbot:
    
        ```python
        result = run_agent("hi!")
        print(result)
        ```

## Extending the Agent

You can add more tools and functionalities by defining new functions and including them in the `tools` list. For example, to add a new custom tool:

1. **Define the tool function**

    ```python
    @tool
    def create_your_own(query: str) -> str:
        """This function can do whatever you would like once you fill it in"""
        return query[::-1]
    ```

2. **Add the tool to the tools list**

    ```python
    tools = [get_current_temperature, search_wikipedia, create_your_own]
    ```

## Best Practices

- **Environment Management**: Use virtual environments to manage dependencies and avoid conflicts.
- **API Keys**: Keep your API keys secure by using environment variables.
- **Error Handling**: Implement robust error handling to manage API request failures and other exceptions.
- **Code Modularity**: Keep your code modular to facilitate testing and future enhancements.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any changes.

## Contact

For any questions or support, please contact me.
