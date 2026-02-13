# BridgeOS

> A minimal, light-mode Kanban board for managing Claude Code agents in tmux.

![BridgeOS UI Preview](docs/screenshot.png)

**BridgeOS** provides a clean, computer-style interface to visualize and manage multiple concurrent `claude` agent sessions running in `tmux`. It organizes agents into **Running**, **Idle**, and **Completed** states, allowing you to monitor activity, send new prompts, and manage workflows visually.

## Features

- **Visual Kanban Board**: Drag-and-drop agents between states (conceptually).
- **Light & Minimal UI**: Clean, off-white aesthetic with IBM Plex Mono typography.
- **Real-time Updates**: Live monitoring of agent output via Server-Sent Events (SSE).
- **Agent spawning**: Easily spawn new `claude` agents in specific project directories.
- **Interactive Controls**: Handle common prompts (permission requests, y/n, selection) directly from the UI.
- **Output Viewer**: Read full terminal logs and send input to running agents.
- **File Uploads**: Drag and drop files onto agent cards to upload them to the agent's context.

## Prerequisites

- **Node.js** (v18+)
- **tmux** (must be installed and accessible in your path)
- **claude** (Anthropic's Claude Code CLI tool)

## Quick Start

1.  **Clone the repository**
    ```bash
    git clone https://github.com/yourusername/bridgeos.git
    cd bridgeos
    ```

2.  **Install dependencies**
    ```bash
    npm install
    ```

3.  **Start the server**
    ```bash
    npm start
    ```

4.  **Open in Browser**
    Navigate to `http://localhost:3000`

## Structure

- `server.js`: Express server that interfaces with `tmux` and `claude` CLI.
- `public/index.html`: Single-page application with vanilla JS/CSS for the frontend.
- `public/`: Static assets.

## License

MIT
