# Hi, I'm Ethan (Surxe)

![Discord](https://img.shields.io/badge/Discord-%40Surxe-5865F2?style=flat&logo=discord&logoColor=white)
![Public repos](https://img.shields.io/badge/dynamic/json?url=https://api.github.com/users/Surxe&query=$.public_repos&label=public%20repos&style=flat&logo=github&logoColor=white&color=2ea043)
![PRs merged](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fapi.github.com%2Fsearch%2Fissues%3Fq%3Dtype%3Apr%2Bauthor%3ASurxe%2Bis%3Amerged&query=$.total_count&label=PRs%20merged&style=flat&logo=git&logoColor=white&color=f05032)
![PRs merged since 2026](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fapi.github.com%2Fsearch%2Fissues%3Fq%3Dtype%3Apr%2Bauthor%3ASurxe%2Bis%3Amerged%2Bmerged%3A%253E%253D2026-01-01&query=$.total_count&label=PRs%20merged%20since%202026&style=flat&logo=git&logoColor=white&color=8957e5)

I write code mostly for things I actually use: datamining game files, turning the
results into structured data, and building the databases and wikis that hold it
all together. Most of my projects start as "I want this data in a form I can
query" and grow from there. The rest are small scripts to automate whatever's
been annoying me that week.

**What I work with and on**

- Datamining game files and turning them into structured, queryable data
- Databases and wikis as the backbone for that data
- General programming and quick for-fun scripting

I learned Python by building a [Wordle](https://github.com/Surxe/Wordle) clone
with a built-in solver, and kept going from there.

## War Robots: Frontiers Database

A group of repos that datamine War Robots: Frontiers and publish it as a
browsable database, wired together into a patch-day pipeline:

- [WRFrontiers-Exporter](https://github.com/Surxe/WRFrontiers-Exporter): decrypts and exports the raw game assets (JSON + PNG), with full headless Linux support
- [WRFrontiersDB-Parser](https://github.com/Surxe/WRFrontiersDB-Parser): extracts and structures the raw game data
- [WRFrontiersDB-Data](https://github.com/Surxe/WRFrontiersDB-Data): the versioned data archive the parser produces
- [WRFrontiersDB-Site](https://github.com/Surxe/WRFrontiersDB-Site): the Astro site that presents it
- [WRFrontiersDB-Orchestrator](https://github.com/Surxe/WRFrontiersDB-Orchestrator): chains the whole patch-day pipeline end to end — export → parse → push to the data repo → site build — gated on manifest-date confirmation, with secrets injected at runtime rather than stored in the repo
- [WRFrontiers-Discount-Visualizer](https://github.com/Surxe/WRFrontiers-Discount-Visualizer): visualizes the weekly in-game discounts, including a predictions page that forecasts next week's discounts from a walk-forward backtest
- [wrf-news-research](https://github.com/Surxe/wrf-news-research): tracking how and when the WRF team edits its news feed, which feeds the discount data

## Deadlock Wiki

I contribute to [deadlock-wiki/deadbot](https://github.com/deadlock-wiki/deadbot),
where I built the backend data extraction and storage: decompiling, parsing, and
uploading Deadlock's game data to the wiki.

## Learning Linux in the open

After moving to a Debian setup, I built a set of personal projects to learn the
platform properly, one real problem at a time:

- [my-system](https://github.com/Surxe/my-system): config-as-code and documented setup for my dual-boot Windows/Debian workstation — KDE shortcuts, the multi-user permission suite, and per-domain system docs
- [home-server](https://github.com/Surxe/home-server): config-as-code and one-command restore for a headless Proxmox box (an old laptop) that runs my always-on services off my main PC — host networking/wifi, backups, a generic VM creator, and a cross-box todo hub (it hosts things like my [valheim-server](https://github.com/Surxe/valheim-server))
- [dev-env](https://github.com/Surxe/dev-env): the shared dev-environment layer both machines pull in as a sibling clone — the portable Claude/DeepSeek skills, shell fragments, statusline, and memory that should be identical everywhere, kept in one repo so it can't drift between boxes
- [b2-backup](https://github.com/Surxe/b2-backup): Restic backups to Backblaze B2, built out of a concern for data loss, especially while migrating off Windows
- [dev-summary](https://github.com/Surxe/dev-summary): summarizes my recent git activity across every local repo in a single Claude call
- [claude-tts](https://github.com/Surxe/claude-tts): speaks Claude Code's terminal output aloud on Linux — a token-free dev→user audio bridge over Piper TTS and systemd path units
- [clip-db](https://github.com/Surxe/clip-db): tags, categorizes, and queries gaming clips via controlled-vocabulary LLM tagging — a batch tagger, a query MCP server (exact + semantic search + retrieval-augmented Q&A), a Discord distributor, and a regression-gated eval suite for the classifier
- [clip-classifier-aws](https://github.com/Surxe/clip-classifier-aws): a serverless AWS port of clip-db's classifier — Amazon Bedrock (Claude) behind AWS Lambda + API Gateway, packaged as a Docker container image and provisioned as infrastructure-as-code with AWS SAM
- [todo](https://github.com/Surxe/todo): a central capture system for dev ideas, driven from a shortcut, the shell, or a Claude Code session
- [steam-price-tracker](https://github.com/Surxe/steam-price-tracker): per-app Steam price tracking with a customizable discount threshold that emails me when a game drops below it, since Steam's wishlist only notifies on any discount at all
- [razer-battery-status](https://github.com/Surxe/razer-battery-status): a sudo-free battery readout for a Razer wireless mouse on Linux, since Razer's own software isn't supported here

## A note on how I run automation safely

I'm wary of handing an AI agent free rein over my machine and my accounts. Giving
tooling my own permissions and hoping it behaves isn't something I'm comfortable
with, so I put a real boundary in place before running any of it.

Claude Code runs under a separate, unprivileged PC user with its own GitHub
account, [Surxe-dev](https://github.com/Surxe-dev), so automation never touches my
primary account's credentials or my home directory. On the workstation, deployment
is handled by the `install.sh` in [my-system](https://github.com/Surxe/my-system),
which pulls in the shared [dev-env](https://github.com/Surxe/dev-env) layer and
*copies* config into each user's home across that privilege boundary rather than
symlinking, so the unprivileged user can never write back into mine.

## Reach me

- Discord: **@Surxe**

