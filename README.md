# Kiko

Kiko finds creators for your product. Give it a link and a line about who the product is for, and it searches Instagram, YouTube and TikTok, reads each creator's recent posts, scores how well they fit, and returns the best matches with their recent videos, their public contact details and a sample first e-mail.

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
- Show me the creators Kiko found.

A search takes 10 to 15 minutes. Reading from Kiko changes nothing. Starting a search and making a link are actions, and Claude asks for your permission before it runs one unless you have told it to always allow it.

## What the discovery tools cover

**Start and follow a search.** Check what Kiko understood from your request and what is still missing, start a creator search, read a search, answer a question Kiko asks along the way, cancel a search, follow its progress, list your searches, and see how many searches your account has left.

**Read results.** List the creators a search found with handle, platform, followers, typical views, engagement, open one creator in full with their recent videos, and read the discovery draft, a sample first e-mail, Kiko wrote for each creator.

**Share.** Make a read-only link to share with your team, list the links that still work, and revoke a link you made.

Most of these tools only read. The ones that write start, answer or cancel a search, write the discovery drafts, and make or revoke share links. None of them sends an e-mail. A discovery draft is a preview.

## Data

The plugin sends what you ask Kiko to do to your Kiko account through `agent.kikocreators.com`: your product link, your description of the product and its audience, and your requests about searches and creators. Kiko returns your searches, the creators it found and the discovery drafts. The plugin sends data to no other service and stores nothing itself.

## Creator data

Kiko returns public, business-facing information about creators.

- **Where it comes from.** Creator profiles, videos and statistics come from creators' public pages on Instagram, YouTube and TikTok, collected for Kiko by commercial social media data providers. Contact details are public business contact e-mail addresses.
- **Legal basis.** Kiko holds this information on the basis of legitimate interest: brands use it to offer creators paid work, which is what a public business contact is for. Kiko does not sell it and does not use it for advertising.
- **Opting out.** A creator can ask to be removed, or to stop being contacted, by writing to emma@meetkiko.com. Kiko removes their contact details within 30 days.

## Links

- Docs: https://agent.kikocreators.com/docs
- Connect guide: https://agent.kikocreators.com/skill
- Privacy: https://agent.kikocreators.com/privacy
- Terms: https://agent.kikocreators.com/terms
- Support: https://agent.kikocreators.com/support
- Website: https://meetkiko.com

## License

Copyright (c) 2026 Interlude LLC. All rights reserved. You may install this plugin and use it with the Kiko service. See `LICENSE`.
