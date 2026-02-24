---
name: model-select
description: Select and configure Claude models by checking API keys, fetching available models from Anthropic API, and managing model settings. Use when working with Claude models, switching between different model versions, or configuring API access.
license: MIT
metadata:
  author: qidu
  version: "1.0.0"
compatibility: Requires jq and internet access to call Anthropic API. Refer to spec at https://agentskills.io/specification
---

# Claude Model Select Skill

This skill helps manage Claude model selection and configuration by interacting with the Anthropic API and Claude Code settings.

## Commands

- `check` / `status` - Check API key availability and show current settings
- `models` / `list` - List available models from Anthropic API
- `set <model>` - Set the active model in Claude Code settings
- `current` / `now` - Show the currently configured model
- `help` - Show usage information

## Environment Variables

- `ANTHROPIC_API_KEY` - Primary API key (recommended)
- `ANTHROPIC_AUTH_TOKEN` - Alternative environment variable name

## Usage

```bash
# Check current settings and API key status
model-select check

# List available Claude models from Anthropic
model-select models

# Set a specific model as active
model-select set claude-opus-4-0

# Show current model
model-select current
```

## Examples

### Checking API Key and Settings

```bash
$ model-select check
=== Claude Model Select ===

API key found.
Current Settings:
model: claude-sonnet-4-0
```

### Setting a New Model

```bash
$ model-select set claude-haiku-3-5-2025-02-20
=== Claude Model Select ===

Model set to: claude-haiku-3-5-2025-02-20
```

## Requirements

- `jq` - JSON processing tool
- `curl` - For API requests
- Network access to `https://api.anthropic.com`
