# Kiko

Kiko finds creators for your product. Give it a link and a line about who the product is for, and it searches Instagram, YouTube and TikTok, reads each creator's recent posts, scores how well they fit, and returns the best matches with a one-sentence reason for each, their public contact details and a drafted first e-mail.

This plugin pairs two things:

- The Kiko connector, a remote MCP server at `https://agent.kikocreators.com/mcp`.
- The `kiko` skill, which tells Claude how to run a creator search with the connector and how to present the results.

## Connect

1. Install the plugin.
2. Open the plugin's Connectors tab and connect Kiko. In Claude Code the connector loads with the plugin, and `/mcp` shows its state.
3. Sign in with Google. Sign-in uses OAuth and is always required. A Kiko account is created the first time you sign in.

The plugin holds no keys, passwords or other secrets, and it runs no code on your computer.

## Use it

Ask Claude things like:

- Find creators for my product: https://owalalife.com/products/freesip . It is for students, gym-goers and commuters.
- How is my creator search going?
- Show me the creators Kiko found and why each one fits.

A search takes about ten minutes. Claude reads from Kiko without asking and asks you before it starts a search or creates a link.

## What the 19 tools cover

**Start and follow a search (9 tools).** Check what Kiko understood from your request and what is still missing, start a creator search, follow its progress, answer a question Kiko asks along the way, cancel a search, list your searches, and see how many searches your account has left.

**Read results (7 tools).** List your campaigns, open one campaign, list the creators it found with handle, platform, followers, typical views, engagement and why they fit, open one creator in full with their recent videos, and read the first e-mail Kiko drafted for each creator.

**Export and share (3 tools).** Download the creators as CSV or JSON, make a read-only link to share with your team, and revoke a link you made.

13 of the tools only read. The 6 that write start, update or cancel a search and make or revoke export and share links. No tool edits or sends an e-mail. You review and send from the review page in Kiko.

## Data

The plugin sends what you ask Kiko to do to your Kiko account through `agent.kikocreators.com`: your product link, your description of the product and its audience, and your requests about searches and creators. Kiko returns your searches, the creators it found and the drafted e-mails. The plugin sends data to no other service and stores nothing itself.

## Links

- Docs: https://agent.kikocreators.com/skill
- Privacy: https://agent.kikocreators.com/privacy
- Terms: https://agent.kikocreators.com/terms
- Support: https://agent.kikocreators.com/support
- Website: https://meetkiko.com

## License

Copyright (c) 2026 Interlude LLC. All rights reserved. You may install this plugin and use it with the Kiko service. See `LICENSE`.
