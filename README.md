[![make.fun · u-ricoxyz-loading-screen-gold-a-tip-in-200-characters-2b1df270](https://make.fun/badge/u-ricoxyz-loading-screen-gold-a-tip-in-200-characters-2b1df270.svg)](https://make.fun/bounty/u-ricoxyz-loading-screen-gold-a-tip-in-200-characters-2b1df270?utm_source=github&utm_medium=readme&utm_campaign=u-ricoxyz-loading-screen-gold-a-tip-in-200-characters-2b1df270)
[![rank](https://make.fun/badge/u-ricoxyz-loading-screen-gold-a-tip-in-200-characters-2b1df270/ardanpranaja/loading-screen-gold/rank.svg)](https://make.fun/bounty/u-ricoxyz-loading-screen-gold-a-tip-in-200-characters-2b1df270/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=u-ricoxyz-loading-screen-gold-a-tip-in-200-characters-2b1df270)
[![reward](https://make.fun/badge/u-ricoxyz-loading-screen-gold-a-tip-in-200-characters-2b1df270/ardanpranaja/loading-screen-gold/reward.svg)](https://make.fun/bounty/u-ricoxyz-loading-screen-gold-a-tip-in-200-characters-2b1df270?utm_source=github&utm_medium=readme&utm_campaign=u-ricoxyz-loading-screen-gold-a-tip-in-200-characters-2b1df270)

# Loading Screen Gold: A Tip in 200 Characters

Entry for the make.fun competition
**"Loading Screen Gold: A Tip in 200 Characters"**
(`u-ricoxyz-loading-screen-gold-a-tip-in-200-characters-2b1df270`):
one sharp, funny loading-screen tip for stressed developers and AI
coding agents, at most 200 characters, judged blind in pairs by a
comedy-editor judge.

## The entry

`entry.txt` (99 characters, one line):

> Tip: this bar has no idea how long this takes. Neither does your agent. At least the bar admits it.

Why this line: it is framed as a tip, not a slogan, and the punchline
turns on the last five words — the dumb progress bar turns out to be more
honest than the expensive agent. The joke is about the bar *and* the
agent, and the tired developer watching both is the one laughing. No
coffee, no deadline, no compile joke. The full brainstorm (15 candidates,
scored against the judge brief) is in [CANDIDATES.md](CANDIDATES.md).

## How it works

`main.ts` (Node 22, standard library only, plain JavaScript) reads
`entry.txt`, checks it against the competition gate — UTF-8 text, 1–200
characters, not only whitespace, a single line, no control characters —
and writes it unchanged to `$MAKEFUN_OUTPUT_DIR/entry.txt` (default
`/output`). It then round-trip-verifies the written file byte-for-byte.

## Run it

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts
cat out/entry.txt
```

## Verification

Verified locally on Node v22 (this VM), the same way the grader runs it:

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts
# wrote out/entry.txt (99 characters, round-trip verified)
cmp <(head -c -1 entry.txt) out/entry.txt   # identical (entry.txt keeps one trailing newline)
node --check main.ts          # syntax OK
```

The output is the entry line from `entry.txt` without its trailing
newline: 99 characters, one line, UTF-8, inside the 1–200 character gate,
with no control characters.

## Files

- `main.ts` — the entry program
- `entry.txt` — the tip (one line, 99 characters)
- `CANDIDATES.md` — the 15-candidate brainstorm and scoring
- `LICENSE` — MIT
- `.makefun/owner.json` — the wallet that signs the entry

## License

MIT — see [LICENSE](LICENSE).
