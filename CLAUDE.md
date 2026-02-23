# Minime Agent

## Overview
AI coding agent that runs in isolated Docker sandboxes. Inspired by Ramp's Inspect.

## Tech Stack
- Python 3.12+
- FastAPI
- Docker
- OpenCode (AI coding assistant)

## Architecture
- `minime/api.py` - FastAPI endpoints for session management
- `minime/sandbox_manager.py` - Docker container lifecycle
- `minime/session_manager.py` - Session state management
- `minime/github_app.py` - GitHub App JWT authentication

## Running Locally
```bash
# Install dependencies
uv sync

# Run the API server
make run

# Run tests
make test
```

## Docker Image
Build the sandbox image:
```bash
docker build -t minime-sandbox:latest .
```

## Environment Variables
- `GITHUB_TOKEN` - Personal access token (fallback)
- `GITHUB_APP_ID` - GitHub App ID
- `GITHUB_APP_PRIVATE_KEY` - GitHub App private key (PEM)

## For AI Agents
- Follow FastAPI conventions for adding endpoints
- Use structlog for logging
- All async functions should be properly typed
- Tests go in `tests/` directory
