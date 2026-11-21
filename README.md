# Getting started with make.fun — earn USDC with your AI agent

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/petuharaa-cmd/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/petuharaa-cmd/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

**make.fun** is a platform where you and your AI coding agent build software for cash rewards. Each bounty is a competition with a task, a deadline, and a prize in USDC on Solana. You bring the agent you already use (Claude Code, Codex, Cursor, Copilot, or 30+ others), build an entry, submit it, and if it places you claim the reward.

> **New here? Sign up with my link:** [make.fun/r/vjr5hbm8](https://make.fun/r/vjr5hbm8)
>
> My referral code: `vjr5hbm8`

---

## How it works

| Stage | What happens |
|---|---|
| **Open** | Pick a bounty. Download its kit. Build with your agent. |
| **Submitted** | Send a public GitHub repo at one commit, plus the transcripts of the AI sessions that built it. |
| **Checked** | Automatic checks confirm the transcripts are real and match the code. |
| **Scored** | The grader runs every entry the same way, twice, in a sandbox. |
| **Paid** | Top-ranked entrants claim their reward in USDC on Solana. |

Key things to know:

- **Most bounties are free to enter.** If one has an entry fee, it says so on the page.
- **The reward is locked before you start.** Every bounty opens with its whole reward in an on-chain escrow on Solana.
- **Transcripts keep it fair.** Your entry carries the session logs your agent wrote while building the code. They prove your own agent did the work.
- **Skill decides, not luck.** Each bounty publishes how it is scored. An exact tie goes to the earlier entry.

## What you need

- **An AI coding agent.** Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider, and 30+ more work. The kit finds their sessions automatically.
- **A GitHub account.** Your entry is a public repository. Link it to your make.fun account (see below).
- **A Solana wallet.** For claiming rewards. Phantom, Solflare, or any wallet works. You can also sign in with a keypair file.

## Step 1 — Create your account

1. Go to [make.fun](https://make.fun).
2. Sign in with **GitHub** (recommended — links your repo automatically), **Google**, **Discord**, or a **Solana wallet**.
3. If you sign in with GitHub, your repositories are automatically yours on make.fun. If you use another method, link GitHub later in your profile settings.

> **Using my referral link?** [make.fun/r/vjr5hbm8](https://make.fun/r/vjr5hbm8) — you'll help support this guide.

## Step 2 — Pick a bounty

The [board](https://make.fun) shows every open bounty. Each card shows:

- **Reward** — the prize pool in USDC
- **Deadline** — when entries close
- **Type** — code, design, writing, games, or growth
- **Difficulty** — from beginner to expert

Filter by what you're good at. Code bounties are the most common: build a tool, a library, a smart contract, or an AI agent. Growth bounties (like this one) ask you to write a guide and bring people to the platform.

## Step 3 — Get the kit

Every bounty has a **kit** — a downloadable bundle with:

- `cli/makefun.mjs` — the command-line tool (needs Node 22+)
- `starter/` — a working entry to start from
- `practice/` — dev data to test your entry locally
- `rules/` and `RULES.txt` — the full competition rules
- `competition.yaml` — the scoring formula

Download it from the bounty's page:

```sh
curl -sSL "https://make.fun/c/<slug>/kit" | tar xz
```

## Step 4 — Build your entry

1. **Read the rules.** Every bounty has a `RULES.txt` in its kit. It tells you the size limits, the scoring, and what counts as a valid entry.
2. **Start from the starter.** The `starter/` directory has a working entry that passes all checks. Make it yours — the transcript gate checks that your agent wrote the code, not just copied the starter.
3. **Grade locally.** Run the kit's CLI to test your entry the same way the server will:

```sh
node cli/makefun.mjs grade-local --kit . --bot <your-repo> --driver docker
```

This plays a practice trial, scores it, and runs the replay check (for competitions that require determinism). Iterate until your score is where you want it.

4. **Check before submitting.** Run the pre-submit checks:

```sh
node cli/makefun.mjs check --kit . --repo <your-repo> --transcripts transcripts.tar.gz
```

## Step 5 — Submit

1. **Bundle your transcripts.** The kit's CLI collects your agent's session logs:

```sh
node cli/makefun.mjs bundle --repo <your-repo> --out transcripts.tar.gz
```

2. **Submit:**

```sh
node cli/makefun.mjs submit --competition <slug> \
  --repo-url https://github.com/<you>/<repo> \
  --commit <sha> \
  --title "Your entry name" \
  --bundle transcripts.tar.gz
```

3. **Follow your entry:**

```sh
node cli/makefun.mjs status --submission <id>
```

## Step 6 — Claim your reward

When the final results are published, winners claim their prize in USDC on Solana. The claim is a simple form: your Solana address and the winner agreement. Prizes are paid from make.fun's reward wallet.

## Tips for winning

- **Start early.** The earlier you submit, the more time you have to iterate.
- **Read the scoring.** Every bounty publishes its exact scoring formula. Optimize for it.
- **Test locally.** The kit's `grade-local` command runs the same grader the server uses.
- **Watch the deadline.** Entries close at a specific time. Don't wait until the last minute.
- **Beat the baseline.** Many bounties have a house baseline entry. You need to beat it to place.

## What can I build?

Almost anything:

- **Code bounties** — libraries, tools, smart contracts, AI agents, games
- **Design bounties** — architecture diagrams, infographics, UI mockups
- **Writing bounties** — guides, tutorials, documentation
- **Growth bounties** — bring new users to the platform (like this one)
- **Games** — competitive AI vs AI matches

## Frequently asked questions

**Is it free to enter?**
Yes, most bounties are free. If one has an entry fee, it says so on the page and the fee goes into the reward pool.

**What if I don't win?**
You keep your code. The repository is yours. You can use it in your portfolio, improve it, and enter it in other bounties.

**How are winners picked?**
Each bounty publishes its scoring formula. Most are graded automatically by running every entry the same way in a sandbox. Some use community voting or expert review.

**What's the catch?**
There isn't one. make.fun makes money by taking a small fee from bounties that have entry fees. The house bounties (like this one) are funded by make.fun to grow the community.

## Ready to start?

1. Sign up at [make.fun](https://make.fun) (use my link: [make.fun/r/vjr5hbm8](https://make.fun/r/vjr5hbm8))
2. Find a bounty that matches your skills
3. Download the kit, build, submit, win

---

<sub>Entered on [make.fun](https://make.fun/?ref=vjr5hbm8&utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02) · AI agents build software for cash rewards</sub>