# NeurIPS Hacker Cup AI SWE Agent

A research-inspired AI Software Engineering Agent designed to inspect code repositories, analyze software issues, create structured implementation plans, validate proposed patches, and run automated tests.

## Overview

This project provides a modular scaffold for experimenting with AI-assisted software engineering workflows.

The agent is designed to support repository-level software development tasks through a structured pipeline.

It includes:
- Repository inspection
- Issue analysis and planning
- Unified diff validation
- Optional patch application
- Automated test execution
- FastAPI service endpoints
- Structured execution reports

**Disclaimer:** This is an independent research-inspired project scaffold. It is not an official NeurIPS competition submission or an officially affiliated competition agent.

## Features

- **Repository Analysis:** Inspect local repositories and identify relevant project files.
- **Issue Planning:** Convert software issues into structured implementation plans.
- **Patch Validation:** Validate proposed unified diffs before applying changes.
- **Controlled Patch Application:** Apply patches only through an explicit workflow.
- **Automated Testing:** Run pytest-based tests and optional Docker-based test environments.
- **API Integration:** Expose agent functionality through FastAPI endpoints.
- **Execution Reports:** Generate structured reports describing agent actions and test outcomes.

## Architecture

The system follows a modular workflow:

```text
Software Issue
      |
      v
Issue Analysis
      |
      v
Repository Inspection
      |
      v
Implementation Planning
      |
      v
Patch Validation
      |
      v
Optional Patch Application
      |
      v
Automated Testing
      |
      v
Execution Report
```

## Project Structure

```text
neurips-hacker-cup-ai-swe-agent/
├── agent/
├── api/
├── repository/
├── patching/
├── testing/
├── reports/
├── tests/
├── main.py
├── requirements.txt
├── .env.example
└── README.md
```

## Installation

Clone the repository:

```bash
git clone <YOUR_REPOSITORY_URL>
cd neurips-hacker-cup-ai-swe-agent
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate it:

**Windows**
```bash
venv\Scripts\activate
```

**Linux / macOS**
```bash
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Configuration

Create a `.env` file based on `.env.example`.

Configure any required model API credentials and execution settings.

## Running the Agent

Run the application:

```bash
python main.py
```

## Starting the API

Launch the FastAPI application:

```bash
uvicorn api.main:app --reload
```

Open the API documentation in your browser:

```text
http://127.0.0.1:8000/docs
```

## Testing

Run the test suite:

```bash
pytest
```

Docker-based testing can be enabled where the required Docker environment is available.

## Safety Considerations

- Patch validation should be performed before applying changes.
- Patch application is an explicit operation rather than an automatic default.
- Repository execution can involve untrusted code and should be isolated.
- Docker isolation is recommended for testing unfamiliar repositories.
- API credentials should be stored securely and never committed to Git.

## Current Limitations

- The included mock planner does not autonomously generate complete software patches.
- Agent capabilities depend on the configured planning and model integrations.
- Test results depend on the target repository and its execution environment.
- This scaffold should not be treated as a production-ready autonomous coding system.

## Future Improvements

- Integrate advanced code-generation models.
- Improve repository-level context retrieval.
- Add multi-step debugging and repair workflows.
- Support additional programming languages.
- Improve sandboxing and execution monitoring.
- Introduce benchmark-based agent evaluation.

## License

This project is intended for educational, research, and experimentation purposes. Add an appropriate open-source license before public distribution.
