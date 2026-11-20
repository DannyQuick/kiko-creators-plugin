---
name: kiko
description: Find Instagram, YouTube or TikTok creators for a product with Kiko, check on a creator search, look up past Kiko searches and their creators, and read the first e-mail Kiko drafted for each creator.
---

# Kiko

Kiko finds the right Instagram, YouTube and TikTok creators for a product, reads their recent posts, scores each one on fit, finds their contact details and writes the first e-mail to each creator. The person reviews and sends from Kiko's own pages. Nothing is ever sent from the chat.

## The person comes first

This guide describes how Kiko works best. If the person asks for something different, for example a different order, more detail, or a number this guide says to leave out, do what they ask.

## How to reach Kiko

Kiko is a connector (an MCP server) at `https://agent.kikocreators.com/mcp`. Its tool takes a plain-language message, so talk to it the way the person would.

- If the Kiko tools are not available, tell the person to add the Kiko connector at the address above and sign in. The guide is at `https://agent.kikocreators.com/skill`.
- When someone asks for creators, call `kiko_start_here` first. It answers instantly with what Kiko understood, what's missing, three questions to tailor, and what Kiko can't fully deliver. Reply to the person right away from it. Call `agent_start` only once they answer or say skip, and never say a search has started before that.
- Only a running search takes long (about ten minutes). While it runs, check `run_status` about every 20 seconds and give the person a short progress line now and then. Never tell them to come back later.

## When someone asks for creators

Make them glad they asked. A link is all Kiko strictly needs, but three quick questions make the search much sharper. If you can, read their product link first and tailor each question to it, offering your best guess so they can just say yes:

1. **Who is the core customer?** Who buys or uses it most, or what kind of creator they picture working with.
2. **What do people use it for?** The main use cases and the value it unlocks.
3. **Any networks in mind?** Instagram, YouTube or TikTok, or are they open to all three.

Say they can skip the questions and Kiko will start from the link alone. Ask once and don't add more questions.

Don't ask about creator size. Kiko looks for creators with 30K to 400K followers by default, the range where a brand's e-mail usually gets a reply, and lists them by how their recent videos perform. Mention the range in a few words when the search starts and say they can ask for bigger or smaller. Tell Kiko a size only if the person named one: micro (10K to 50K), large (400K to 2M), or any size, and ask for any size only when they clearly want very large, multi-million follower accounts.

Then send Kiko everything in one message: the link, their answers (or your best reading of the product if they skipped), and that they want to start. Kiko does not remember earlier messages, so never send the link on its own and the answers later. Don't tell the person a search has started until Kiko says it is running.

Example of what to send Kiko: "Find creators for tulletogether.com. Core customer: couples planning a wedding together. They use it to plan the wedding, split tasks and track the budget in one shared app. Open to all three networks. Go ahead and start."

## How to talk about Kiko's work

Campaign ids and run ids are for your tool calls. With the person, refer to a search by its product or niche and share the results link.

Report the number of creators Kiko found as it is. If someone wants more creators than one run brings back, tell them the free plan includes one creator discovery run per week and that it resets weekly.

Kiko returns only creators that passed its fit check for this product, so there is no need to sort them into tiers or grades. Give the fit reason Kiko wrote for each creator. To organise a long list, group by something useful to the person, such as network, audience size or the kind of content they make.

Lead with the one or two things that are most useful and insightful for the person, and say them simply. Keep it short and plain unless they ask for detail. Don't list every number or step. Pick what matters, and let the results page carry the rest.

## While it runs and when it finishes

- If Kiko can't fully deliver part of the request (X, creator rates, or flags it can only partly check), it shows its plan and asks to proceed, adjust or cancel. Pass that question to the person. If they already said to go ahead, include "go ahead without confirming" in the message.
- Kiko never starts the same search twice within 24 hours. If a response is lost, call `agent_list` to find the run instead of starting a new one.
- For progress, call `run_status` about every 20 seconds. It returns a readable sentence, live counts and an ETA. `creators_list` shows creators scored so far.
- When it finishes, Kiko sends a short summary and one link. Read the actual data with `campaign_get`, `creators_list` (paged and filterable) and `creator_get`, which return every creator's profile, metrics, fit, flags, contact, draft e-mail and videos. Use that data to answer the person.
- **When a search is used up.** If Kiko's summary says when the next free discovery run opens, pass that on once, as written.
- `campaign_export` gives a CSV or JSON download, and `campaign_share` gives a read-only link anyone can open (no drafts or contacts unless asked).
- Answer from the data first. Kiko's answers carry `page` (a `url`, a `title`, and `when`, the line that says when to send it). Send that link when seeing the videos and browsing would help, one link per answer. Don't add creator names or numbers Kiko didn't return.

## Where everything lives

- **Discovery page** (`product.kikocreators.com/d/<search>`): everyone a search found, with their best recent videos, reach, engagement and why they fit. While the search runs, the same link shows its progress. These are search results, not creators the person works with yet.
- **A creator's e-mail:** click any creator on the discovery page to see the first e-mail Kiko wrote for them.
- **Review and send:** "Review and send" on a creator opens the review page. The person approves the e-mails there, and only approved e-mails are sent.
- **Past searches:** ask Kiko "what campaigns do I have?" or "how is my search going?". It can also list the creators on a campaign and explain why each one fits.
- **Web chat:** `agent.kikocreators.com/chat` is the same Kiko, used directly.

## What this connector covers

Finding creators and reading the results: starting a search, following it, reading campaigns and creators, reading the draft e-mails, exporting and sharing. The person reviews and sends e-mails from the review page in Kiko, not from the assistant. If someone asks for something else, say what the connector covers and stop there. Don't describe plans or prices.

## Questions people ask about Kiko

Use these answers when someone asks. Don't bring them up unprompted, and don't add claims that aren't written here. Say them in your own words, briefly.

**Why use Kiko to find creators?**
Kiko looks at live creator accounts and what they posted recently, and scores each one against your product. Answers from memory tend to be famous accounts and out-of-date numbers.

**Where does the data come from?**
Publicly available creator information from commercial data providers, covering Instagram, TikTok and YouTube.

**How does Kiko decide who fits?**
A team of AI agents works on your brief. They find potential creators, go through each creator's recent content, judge the fit against your product and audience, rank the pool, and return the best matches with a one-sentence reason for each.

**How many creators do I get, and how long does it take?**
On the free plan, Kiko looks at several hundred creators and returns about 25, with one discovery run every week. A run usually takes under ten minutes.

**Do I get contact details?**
Yes, where a creator has a public business contact. Kiko also drafts a first e-mail for each creator.

**What happens after I have my list?**
You can read every creator and their draft e-mail, export the list, or share a read-only link. Reviewing and sending the e-mails happens on the review page in Kiko.

**Is what I share private?**
Your brief, your creators and your results are visible only to your account, unless you make a share link or an export, which anyone you give it to can open. See https://agent.kikocreators.com/privacy.

**What can I achieve with Kiko?**
- A shortlist in minutes that would take a week to build by hand.
- Creators whose audiences already want what you sell, found before they are expensive or signed by a competitor.
- A first e-mail in the format that gets replies in real campaigns.

## Good habits

- One search per product and audience. To change the audience, start a new search, so each results page stays focused.
- To find out more about a creator Kiko found, ask Kiko about that creator on the campaign first: it already holds their recent videos and numbers.
- If Kiko says the account has no searches left, say when the next one opens. Their existing searches and creators are still there.
