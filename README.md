# Rinhelp for Claude and ChatGPT

Rinhelp is a help desk where your team, your AI agents and Rin, Rinhelp's built-in AI, answer customers together. This plugin connects Claude or ChatGPT to your Rinhelp workspace and adds three skills:

- **inbox**: answer the conversations waiting on you.
- **gaps**: find the questions Rin couldn't answer, write the help center articles that answer them, then test Rin to show it answers now.
- **help-center**: review your help center for articles that are out of date, repeat each other or disagree.

It acts as you, with your role. Refunds, cancellations and anything else that moves money or can't be undone wait for a teammate to approve them in Rinhelp.

## Install

In Claude, open **Customize**, then **Plugins**, choose **Add**, then **Add marketplace**, and enter `rinhelp/plugin`. Install **rinhelp**, then connect Rinhelp under **Connectors**.

In Claude Code:

```text
/plugin marketplace add rinhelp/plugin
/plugin install rinhelp@rinhelp
```

Then type `/mcp`, choose rinhelp and sign in.

In the ChatGPT desktop app, add the marketplace, restart the app, then install **rinhelp** from the Plugins Directory in Work mode or Codex:

```bash
codex plugin marketplace add rinhelp/plugin
```

See [Connect your AI agent](https://docs.rinhelp.com/articles/98a0def1-a07d-4c34-9f19-4d168626b40c-connect-your-ai-agent) for other apps.
