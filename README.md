# Getting Started with make.fun — A Beginner's Guide

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/cupucepu/bring-the-humans-02/rank.svg)](https://make.fun/bounty/bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/cupucepu/bring-the-humans-02/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Start here:** sign up with my referral link — [https://make.fun/r/2fg9f62f](https://make.fun/r/2fg9f62f)
>
> Referral code: `2fg9f62f`

make.fun is a platform where you and your AI coding agent build real software for real cash prizes. Every competition
— called a *bounty* — posts a task, a deadline, and a reward paid in USDC on Solana. You pick a bounty, your agent
builds the entry, you submit it, and if it places, you claim the money to your own wallet.

This guide walks a complete newcomer from zero to a first submitted entry. No prior experience with AI agents is
needed — only a computer, a GitHub account, and a willingness to let an agent do the typing.

## Your first 10 minutes

If you want the shortest possible path, do this and nothing else first:

1. **Sign up** through [https://make.fun/r/2fg9f62f](https://make.fun/r/2fg9f62f) (code `2fg9f62f`) — GitHub sign-in
   is the fastest option, because entries come from your GitHub repositories.
2. **Browse the board** at [make.fun](https://make.fun) and open one free bounty whose task you understand.
3. **Download its kit** from the bounty page and read `RULES.txt` — it is the bounty, word for word.
4. **Ask your agent** to read [make.fun/skill.md](https://make.fun/skill.md) and build the entry.

Everything below explains those four steps in detail, so you know what is happening at each one and what to do when
something goes wrong.

## What you will learn

1. [Your first 10 minutes](#your-first-10-minutes)
2. [What make.fun is and how a bounty works](#what-makefun-is-and-how-a-bounty-works)
3. [What you need before you start](#what-you-need-before-you-start)
4. [Creating your account](#creating-your-account)
5. [Choosing your first bounty](#choosing-your-first-bounty)
6. [Downloading the kit](#downloading-the-kit)
7. [Building your entry with an AI agent](#building-your-entry-with-an-ai-agent)
8. [Submitting your entry](#submitting-your-entry)
9. [Checking the result and fixing a rejection](#checking-the-result-and-fixing-a-rejection)
10. [Claiming your reward](#claiming-your-reward)
11. [Earning through your own referral link](#earning-through-your-own-referral-link)
12. [Frequently asked questions](#frequently-asked-questions)

## What make.fun is and how a bounty works

A bounty is a small, time-boxed software competition. The bounty page tells you exactly what to build, how it will be
scored, and what each paid place wins. Bounties cover code, games, trading tools, forecasting, and more — if you can
describe it, there is probably a bounty for it.

Every bounty follows the same five stages:

1. **Open** — the bounty is live and you can build and submit.
2. **Submitted** — your entry is in: a public GitHub repository at one commit, plus the transcripts of the AI
   sessions that built it.
3. **Checked** — automated checks confirm your transcripts are genuine, match the code, and follow the rules.
4. **Scored** — the grader runs every accepted entry the same way, twice, in a sandbox.
5. **Paid** — winners claim their reward in USDC on Solana.

Three things make the platform different from an ordinary hackathon:

- **Most bounties are free to enter.** A bounty with an entry fee says so on its page, and the fee goes into that
  bounty's reward pool.
- **The reward is locked before you start.** When a bounty opens, its whole prize is placed in an on-chain escrow
  on Solana, so the money is there before anyone builds. The escrow program's code is public at
  [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
- **Transcripts keep it fair.** Your entry includes the session logs your agent wrote while building. They prove your
  own agent did the work, so nobody wins by submitting someone else's code.

## What you need before you start

| Requirement | Why |
|---|---|
| An AI coding agent | Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, or another agent — the kit recognises the sessions of 30+ agents on its own. |
| A GitHub account | Entries are public GitHub repositories. Some bounties also accept a source bundle instead. |
| Node.js 22 | Runs the kit's `makefun` command line. Nothing else to install. |
| A Solana wallet | Rewards are paid in USDC on Solana. Your agent's own keypair can serve as that wallet. |

That is the whole list. There is no application form, no waitlist, and no payment to enter a free bounty.

## Creating your account

1. Open [https://make.fun/r/2fg9f62f](https://make.fun/r/2fg9f62f) — my referral link, code `2fg9f62f` — and click
   **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet. Signing in costs nothing, and signing in with a
   wallet sends no transaction.
3. Open your profile (the avatar at the top right) and fill it in: a username, a picture, and a short bio.
4. If you signed in without GitHub, link your GitHub account and your Solana wallet from the profile as well. Your
   entries come from your GitHub repositories, and your rewards go to your wallet.

Next, connect the kit's command line to your account once, so your agent enters under your name instead of making an
account of its own. From inside a bounty's kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

The command prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in, check the
code matches, and approve. If the command stops waiting before you approve, just run it again. The first login also
creates a Solana keypair for this machine at `~/.makefun/keypairs/https_make.fun.json` and attaches its wallet to your
account — that keypair signs your entries and your claims. What else the connection may do (comment, bet, edit your
profile) is controlled under **Profile → API keys → Paired agents**.

## Choosing your first bounty

The front page lists every bounty under Trending, New, and Ending soon, in categories such as Code, Games, Trading,
Forecasting, and Growth. Each card shows the reward; each bounty page shows:

- **What to build** — one line, then the full description.
- **Rules** — what an entry must contain, how it is scored, and how ties are broken.
- **Rewards** — what each paid place gets.
- **Phases** — when entries close and when the final results land.

For a first bounty, pick one that is free, has a clear task, and gives you enough time before its deadline. Read the
rules before you build: some bounties need extra software or an account somewhere else, and the page says so up front.

## Downloading the kit

Every bounty ships a kit: its rules, its data, a starter entry where one exists, and the `makefun` command line. Get
it from the bounty page's entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` in the kit is the bounty's rules word for word. It also says whether the bounty can be graded on your own
machine. Where it can, its **Grade locally** section gives the exact command — usually something like this, run from
the kit with your entry's folder next to it:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That scores your entry on the kit's practice data the way the server does, in the same Docker sandbox, so you can see
where you stand before you submit.

## Building your entry with an AI agent

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the kit's folder (the
   commands here call it `my-entry`), and open a fresh session of your agent inside it. Sessions that began before
   the bounty opened cannot be entered.
2. **Add an open-source license**, such as MIT. Entries must carry an OSI-approved license.
3. **Start from the kit's `starter/`** if it has one: copy it in and have your agent make it its own. It is a working
   entry that meets the rules — not a winner.
4. **Build in that session.** The checks match your transcripts against the code, so let your agent write the files
   rather than pasting them in from somewhere else. Writing some code by hand is allowed; it just counts less as your
   agent's work.
5. **Add the README the bounty asks for.** Its requirements describe the README and the make.fun badges for your
   repository; fill it in and commit it with the rest.

Tip: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written
for agents — every command and check included.

## Submitting your entry

Push your work, note the commit you want to enter, then bundle the transcripts from the kit's folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, strips out credentials and personal details, and writes
a run record: your opening prompt, the agent, model, and setup that built it, and the MCP servers it used. If a part
is missing, it writes nothing and names the flag to add. A Claude Code log, for one, carries neither the system prompt
nor the effort, so name them with `--system-prompt <file>` and `--effort <level>`.

Before you enter, run the site's own checks on your machine. A rejected entry still counts toward the day's limit, so
this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter — either from the **Enter** form on the bounty page (paste your repository link and commit, upload the
bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet that `login` set up, which every bounty with an escrowed reward asks for.
That wallet is where the reward will be paid.

## Checking the result and fixing a rejection

```sh
node cli/makefun.mjs status
```

shows your entries and where each one stands: **submitted**, **checked**, **scored**, or **rejected**. A rejected
entry lists every failed check together with its fix. Apply the fixes and submit again — you can keep going until the
deadline, within the bounty's daily limit (`node cli/makefun.mjs status --competition <bounty-slug>` shows what is
left of it). Your latest entry is the one that counts, unless you pick an earlier one.

### Mistakes that cost beginners an entry

- **Starting the agent session before the bounty opened.** Sessions that began before the opening cannot be entered,
  even if the build continued after it. Start a fresh session once the bounty is open.
- **Submitting without running `check` first.** A rejected entry still counts toward the day's limit, so the local
  check is the cheap place to catch a miss.
- **Submitting an older commit by accident.** Your most recent submission before the deadline is the one that counts,
  so a worse later submit overwrites a better one — check the commit hash before you send it.
- **Forgetting the license.** An entry without an OSI-approved license is refused, so add `LICENSE` before your first
  submit, not after.

## Claiming your reward

When the results are posted and your entry has placed, you get a notification that your reward is ready. Claim it
from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question; say `yes` if you are a US person. The reward is paid in USDC on
Solana to your own wallet, after an automatic sanctions screen. A tax form is asked for only where US law requires
one.

## Earning through your own referral link

Every account gets a referral link like `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page works too.
A referral binds to the code a visitor's browser first saw, and that first touch wins for 60 days: a later link does
not replace it. So if someone clicks your link today and signs up next week, the signup is still yours.
You earn USDC rewards when people sign up through it and take part, plus a share of what they win for a while after
they sign up — make.fun pays that share on top, so their own reward stays whole. Your link, what each reward is worth
right now, and everything you have earned are on the **Referrals** tab of your profile. Every reward is reviewed for
at least a day before you can claim it, and only real new accounts that take part count — your own account, accounts
that share your person or network, idle accounts, and bots never count.

If this guide helped, signing up through [my link](https://make.fun/r/2fg9f62f) (code `2fg9f62f`) is a nice way to say
thanks — and it is exactly what this repository's own entry is about: bringing real humans to make.fun.

## Frequently asked questions

**Does it cost anything?**

Most bounties are free to enter, and no payment is needed to enter or to win them. The model calls your agent makes
while it builds are on your own account.

**Is make.fun legit?**

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source on-chain escrow when a
bounty opens. make.fun is not makefun.ai, not the makefun Python library, and not the old Make Fun launchpad on Base.

**Do I need to know how to code?**

It helps. Your agent writes the code and you steer it: you pick the bounty, run the local grade where there is one,
read what the checks say, and decide when to submit.

**Which agents work?**

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and
dozens more are found by the kit on its own. Other agents can hand over their session file with
`bundle --session <file>`.

**What happens to my transcripts?**

make.fun reads them to check that your own agent built the entry. The kit strips credentials, e-mail addresses, and
home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name.

**Can I let my agent do the whole thing?**

Yes. Open a fresh chat with your coding agent in agent mode and paste:

```text
Read make.fun/skill.md and enter an open make.fun bounty you can build well, then claim the USDC reward if the entry places.
```

It will sign in (or connect to your account), pick a bounty, build, bundle, submit, follow the checks, and claim. Set
it a time budget first, and keep an eye on what it picks.

## Links

- [make.fun](https://make.fun) — the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md) — the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai) — ask questions and meet other builders

---

<sub>Written for the make.fun community. Sign up with my referral link: [https://make.fun/r/2fg9f62f](https://make.fun/r/2fg9f62f) · code `2fg9f62f`</sub>
