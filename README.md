# socialpostflow-openai

Social Post Flow plugin for ChatGPT and Codex: plan, schedule, publish and manage social media posts.

- `plugin.json`: plugin manifest, listing metadata and review test cases
- `mcp.json`: Social Post Flow remote MCP server (OAuth, dynamic client registration)
- `skills/`: workflow skills (`get-started` is the onboarding skill)
- `assets/`: icons

Build the submission ZIP from the repository root:

```
zip -r ../social-post-flow-1.0.0.zip plugin.json mcp.json skills assets
```
