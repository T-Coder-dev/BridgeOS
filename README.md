# BridgeOS
A kanban board for managing multiple Claude Code agents running in tmux sessions.
Spawn, monitor, and interact with agents from a single web UI. Manage your agents from
your mobile phone with Tailscale.

**Build for Vibeathon 2026**

<img width="1919" height="1079" alt="BridgeOS Home" src="https://github.com/user-attachments/assets/f666d8fc-31f9-4652-95c9-30504aa25b06" />


<img width="1919" height="1079" alt="New agent" src="https://github.com/user-attachments/assets/8789f560-c6f4-4509-83f9-37f64d5bcb49" />


## Prerequisites
* **Node.js** (v18+)
* **tmux**
* **Claude CLI** (`claude` command available in your PATH)
## Quick Start
```bash
git clone https://github.com/T-Coder-dev/BridgeOS.git
cd BridgeOS
npm install
npm start
```
Open [http://localhost:4200](http://localhost:4200) in your browser.
## Configuration
You can customize the server behavior using environment variables:
| Variable | Default | Description |
| :--- | :--- | :--- |
| `PORT` | `4200` | Server port |
| `HOST` | `localhost` | Bind address (0.0.0.0 for network access) |
Example with custom port:
```bash
PORT=4200 npm start
```
## Remote Access via Tailscale
You can access **BridgeOS** from your phone (or any device) by using Tailscale.
1. **Install Tailscale on your Mac:** `brew install tailscale` or download from
[tailscale.com](https://tailscale.com/download).

2. **Install Tailscale on your phone:** Download the app from the App Store or Google Play
and sign in with the same account.
3. **Start the server:** `npm start`. The server binds to `0.0.0.0` by default, making it
accessible on all network interfaces including Tailscale.
4. **Open on your phone:** Find your Mac&#39;s Tailscale IP in the app, then visit:
`http://&lt;tailscale-ip&gt;:4200`.
## Features
* **Spawn agents** — Click **[+ SPAWN]** or press `N`, enter a project path and prompt.
Each agent launches in its own tmux session running `claude`.
* **Kanban columns** — Agents are automatically sorted into **Running**, **Idle**, and
**Completed** columns based on their real-time state.
* **Auto-discovery** — BridgeOS scans your system for existing tmux sessions running
Claude and automatically adds them to the board.
* **Live output** — Click **VIEW OUTPUT** to see the full terminal output with full ANSI
color rendering.
* **Send messages** — Type in the prompt field on any card and press `Ctrl+Enter` to send
follow-up instructions to an agent.
* **File uploads** — Drag and drop files onto a card or click **FILE** to send files directly
to an agent&#39;s session.
* **Re-spawn** — Finished a task? Re-spawn completed agents with a new prompt from
the same project directory.
* **Attach** — Click **ATTACH** to copy the tmux attach command for direct terminal
access to the session.
