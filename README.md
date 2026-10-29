# output-styles

Custom [output styles](https://code.claude.com/docs/en/output-styles) for Claude Code.

## concise-readable

Short replies written in plain, human-readable English. The style cuts content, never compresses sentences.

### Provenance

This style is based on the findings of [Why is AI-generated language so hard to understand?](https://arxiv.org/abs/2610.29162) by Thomas Hikaru Clark, Matias B. Martin, and Kyle Mahowald (arXiv:2610.29162, October 2026).

The paper reports that language models write with patterns that slow human readers more than human writing does. Examples are embedded relative clauses, long-distance dependencies, and rare word combinations. The authors suggest that models are optimized for dense output in math, coding, and reasoning, and that this causes the mismatch.

The style turns those findings into rules. Each sentence rule targets one of the difficult constructions: keep subjects next to their verbs, prefer subject relatives over object relatives, keep optional function words, and use common words and pairings. The main rule is to get shorter by leaving things out, not by packing more into each sentence.

This repository is not affiliated with the paper's authors, and the authors have not reviewed or endorsed the style.

### Install

Copy the file into your user-level output styles folder:

```sh
mkdir -p ~/.claude/output-styles
curl -o ~/.claude/output-styles/concise-readable.md \
  https://raw.githubusercontent.com/pmatos/output-styles/main/concise-readable.md
```

Then run `/output-style` in Claude Code and select **Concise Readable**.
