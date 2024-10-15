# Trip Planner with CrewAI

This project is a trip planner powered by `CrewAI` and LangChain, utilizing the OpenAI API for generating intelligent travel suggestions and itinerary plans.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Troubleshooting](#troubleshooting)
- [License](#license)

## Overview

The **Trip Planner** leverages `CrewAI` to provide automated itinerary planning based on user inputs. It integrates with the OpenAI API to generate natural language-based responses, utilizing the `LangChain` framework to manage the flow of tasks. The project uses various agents to plan trips, including but not limited to identifying locations, managing trip details, and providing personalized travel suggestions.

## Features

- Automated itinerary generation.
- Personalized trip recommendations based on inputs.
- Sequential task execution using CrewAI.
- Integration with LangChain and OpenAI for natural language processing.

## Installation

### Requirements

- Python 3.10+
- Poetry (for dependency management)
- OpenAI API Key

### Steps

1. Clone the repository:

   ```bash
   git clone https://github.com/Vishal2053/Trip-Planner-using-CrewAI.git
   cd trip-planner
   ```

2. Install dependencies using Poetry:

   ```bash
   poetry install
   ```

3. Create a `.env` file in the root directory to store your OpenAI API key:

   ```bash
   touch .env
   ```

   Add your OpenAI API key inside `.env`:

   ```bash
   OPENAI_API_KEY=your_openai_api_key
   ```

4. Activate the virtual environment:

   ```bash
   poetry shell
   ```

## Usage

Once the environment is set up and dependencies are installed, you can run the trip planner as follows:

```bash
python main.py
```

The script will begin by executing tasks related to trip planning, such as gathering location details and generating itinerary options using OpenAI.

### Code Overview

- **main.py**: Entry point for the program. Initializes and runs the trip planner using CrewAI and LangChain.
- **CrewAI Integration**: This handles the sequential loop of tasks and executes the trip planning logic.
- **LangChain and OpenAI API**: Provides natural language responses for trip recommendations and suggestions.

## Configuration

To configure the project, ensure you have the following environment variables:

- `OPENAI_API_KEY`: Your API key from OpenAI.
  
Add these variables to your `.env` file or export them in your shell:

```bash
export OPENAI_API_KEY=your_openai_api_key
```

### Rate Limiting

If you exceed the OpenAI API quota, you might see an error like:

```
openai.RateLimitError: Error code: 429 - {'error': {'message': 'You exceeded your current quota, please check your plan and billing details.'}}
```

## Troubleshooting

### Exceeding API Quota

If you encounter a `RateLimitError` (Error code: 429):

1. **Check Your Quota**: Verify your OpenAI API quota and upgrade if necessary on the [OpenAI dashboard](https://platform.openai.com/account/billing).
2. **Reduce API Calls**: Optimize the number of requests made to the OpenAI API by caching or batching calls.
3. **Retry Mechanism**: Implement a retry mechanism to handle rate limits gracefully.
4. **Use a Local Model**: Consider switching to a local model (such as Hugging Face models) for testing to avoid overusing API requests during development.

### LangChain Issues

If you're having issues related to LangChain or task execution:

- Make sure you're using the correct versions of `LangChain` and `CrewAI` as specified in `pyproject.toml`.
- Review the documentation for `LangChain` to ensure proper use of chains and agents.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

You can modify the details, like the project URL and license information, as per your requirements. This README provides a clear structure for understanding, configuring, and troubleshooting the project on GitHub.
