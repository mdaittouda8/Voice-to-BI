# Speech to SQL Query & Visualization App

This app allows you to speak natural language queries, converts them into SQL queries using OpenAI's GPT-4, executes the queries on an Azure SQL Database, and visualizes the results in interactive charts. It also integrates Azure's Cognitive Services for speech recognition.

## Features

- **Speech-to-Text**: Uses Azure Cognitive Services for speech recognition, allowing users to speak queries directly into the app.
- **SQL Query Generation**: Converts spoken queries into SQL using OpenAI's GPT-4 model.
- **Data Visualization**: Generates charts using Plotly, including bar charts, line charts, and pie charts, based on the query results.
- **Azure SQL Database Integration**: Executes SQL queries on an Azure SQL database and returns the results as a Pandas DataFrame.

## Prerequisites

Before running the app, make sure you have the following:

1. Python 3.11+ installed on your machine.
2. An OpenAI API key.
3. An Azure Speech API key.
4. Access to an Azure SQL Database.

## Installation

1. Clone this repository or download the script.
2. Create a virtual environment and activate it:

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. Install the necessary dependencies:

    ```bash
    pip install -r requirements.txt
    ```

4. Create a `.env` file in the same directory as the script, and add your credentials:

    ```text
    OPENAI_API_KEY=your_openai_api_key
    AZURE_SPEECH_KEY=your_azure_speech_key
    SQL_SERVER=your_sql_server
    SQL_DATABASE=your_sql_database
    SQL_USERNAME=your_sql_username
    SQL_PASSWORD=your_sql_password
    SQL_DRIVER=your_sql_driver
    ```

## Usage

1. **Run the App Locally**:

    In the terminal, navigate to the directory containing the script and run:

    ```bash
    streamlit run app.py
    ```

2. **Interact with the App**:
    - Click the "Start Speaking" button.
    - Speak your query, for example: "What is the average labor cost for jobs completed in 2024?"
    - The app will:
        - Convert your speech to text.
        - Use OpenAI GPT-4 to generate the corresponding SQL query.
        - Execute the SQL query on your Azure SQL Database.
        - Display the results in a table and generate an appropriate chart (bar, line, or pie) based on the data.

## Example Queries

Here are some example queries that the app can handle:

- "What is the average labor cost for jobs completed in 2024?"
- "How many jobs were completed last week?"
- "Show a pie chart of customer satisfaction ratings."

## Code Explanation

### `audio_to_text`

This function uses Azure's Cognitive Services Speech SDK to listen to the user's microphone input and convert it to text.

### `get_openai_response`

This function uses the OpenAI API (GPT-4) to generate an SQL query based on the user's natural language input.

### `read_sql_query`

This function executes the generated SQL query on an Azure SQL Database using the `pyodbc` library and returns the results as a Pandas DataFrame.

### `generate_chart`

This function generates different types of charts (bar, line, or pie) based on the data returned from the SQL query. It uses Plotly for chart generation.


## Acknowledgments

- [OpenAI](https://openai.com/) for GPT-4 API.
- [Azure Cognitive Services](https://azure.microsoft.com/en-us/services/cognitive-services/speech-to-text/) for speech recognition.
- [Plotly](https://plotly.com/python/) for chart generation.
- [Streamlit](https://streamlit.io/) for the interactive web app framework.
- [PyODBC](https://github.com/mkleehammer/pyodbc) for database connectivity.

## Troubleshooting

If you encounter any issues, please ensure that:

- Your Azure SQL Database credentials are correct.
- Your OpenAI and Azure Speech API keys are valid.
- The `.env` file is properly configured.
- All dependencies are installed correctly.

For further help, feel free to open an issue in the repository or contact the project maintainer.

---

Enjoy building with Speech to SQL Query & Visualization App!
