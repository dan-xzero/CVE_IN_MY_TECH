# Tech Vulnerability Scanner

This repository contains a Python-based toolchain for:
- Cloning repositories from Bitbucket
- Generating SBOM (via [Syft](https://github.com/anchore/syft))
- Scanning for vulnerabilities using [Grype](https://github.com/anchore/grype) and NVD data
- Using OpenAI for advanced vulnerability assessment
- Sending results and notifications to Slack

---

## Requirements

1. **Python 3.7+**  
2. **Pip** (or other package managers like Poetry/Pipenv)  
3. **Docker** (optional, if you want container-based approaches)  
4. **Syft** and **Grype** binaries installed locally (or available on `PATH`).

You’ll also need to install the required Python dependencies from `requirements.txt`.

---

## Environment Variables

Create a `.env` file (or export environment variables) with:

- **BITBUCKET_WORKSPACE**: your Bitbucket workspace name
- **ATLASSIAN_USERNAME**: your Bitbucket username (for authentication)
- **ATLASSIAN_API_KEY**: your Bitbucket app password/API key
- **OPENAI_API_KEY**: your OpenAI API key
- **NVD_API_KEY**: your NVD API key
- **SLACK_WEBHOOK_URL**: Slack webhook for minimal messages
- **SLACK_API_TOKEN**: Slack API token for uploading files

An example `.env` might look like:

```bash
BITBUCKET_WORKSPACE=myworkspace
ATLASSIAN_USERNAME=johndoe
ATLASSIAN_API_KEY=xxxxxx
OPENAI_API_KEY=sk-xxxxxx
NVD_API_KEY=yyyyyy
SLACK_WEBHOOK_URL=https://hooks.slack.com/services/...
SLACK_API_TOKEN=xoxb-....
