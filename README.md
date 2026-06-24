# SBX Quickstart Binaries

Prebuilt `docker labspace` CLI plugin binaries (macOS & Windows) for running the **Docker Sandboxes (SBX) Quickstart** workshop.

The `docker labspace` plugin lets you launch interactive, browser-based Docker workshops ([Labspaces](https://docs.docker.com/ai/sandboxes/get-started/)) directly from the Docker CLI. This repo hosts the compiled binaries so you can install the plugin without building it yourself.

## Contents

| File | Platform |
|------|----------|
| `docker-labspace-darwin-arm64` | macOS (Apple Silicon / arm64) |
| `docker-labspace-windows-amd64.exe` | Windows (x86-64) |
| `Labspace CLI Install` | Plain-text copy of the install steps below |

## Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed and running
- A Docker login (needed to start SBX)
- At least one LLM API key — **Anthropic**, **OpenAI**, or **Gemini**
- A **GitHub Personal Access Token (PAT)**

## Install

Download the binary for your OS, rename it to `docker-labspace`, and move it into `~/.docker/cli-plugins`.

### macOS

```bash
mkdir -p ~/.docker/cli-plugins/
mv ~/Downloads/docker-labspace-darwin-arm64 ~/.docker/cli-plugins/docker-labspace

# Make it executable and clear the macOS quarantine flag
chmod +x ~/.docker/cli-plugins/docker-labspace
xattr -d com.apple.quarantine ~/.docker/cli-plugins/docker-labspace
```

### Windows (PowerShell)

```powershell
# Create the directory first if it doesn't exist
Move-Item "$HOME\Downloads\docker-labspace-windows-amd64.exe" "$HOME\.docker\cli-plugins\docker-labspace"
```

### Validate

```bash
docker labspace version
```

## Launch the workshop

```bash
docker labspace launch dockersamples/labspace-sbx-quickstart
```

Then open your browser to **http://localhost:3030** and work through the lab.

## Related

- **Workshop source:** [ajeetraina/labspace-sbx-quickstart](https://github.com/ajeetraina/labspace-sbx-quickstart)
- **Docker Sandboxes docs:** https://docs.docker.com/ai/sandboxes/get-started/
