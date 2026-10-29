<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.png">
    <source media="(prefers-color-scheme: light)" srcset="assets/logo-light.png">
    <img alt="Code Buddy logo" src="assets/logo-light.png" width="140">
  </picture>
</p>

<h1 align="center">Code Buddy</h1>

<p align="center">
  A Claude skill that reviews, debugs, and writes code in any language,
  with a calm, warm tone and help that fits your skill level.
</p>

---

## What it does

Share code, an error, or an idea, and Claude acts like a friendly teammate sitting next to you. It figures out whether you need a review, a bug fix, or fresh code, gives you one best suggestion (with a short reason), and then gets to work.

It asks your level first, so a beginner gets patient, simple teaching and an experienced developer gets short, technical answers.

## Levels

| Level | Style | Debugging behavior |
|---|---|---|
| **Starter** | Plain words, analogies, lots of "why" | Explains the bug simply, asks you to try the fix yourself, and writes the code only if you can't |
| **Student** | Normal terms, key ideas explained | Writes the fix and explains the main idea |
| **Intermediate** | Technical vocabulary, light explanation | Writes the fix, explains only what is non-obvious |
| **Advanced** | Concise and precise | Gives the cause and the patch, plus trade-offs |

## Jobs it handles

| Job | Trigger | Result |
|---|---|---|
| **Debug** | error message, "why isn't this working" | Finds the real cause and fixes it |
| **Review** | "review my code", "improve this" | Top 3 to 5 prioritized findings with improved code |
| **Generate** | "write me a function/script/program" | Complete, working code plus a level-appropriate explanation |

## Features

- Asks your level once, then remembers it for the chat
- One best suggestion plus a short reason, instead of a long menu
- Starter-friendly debugging: explain, let you try, then help
- Works in any programming language
- Output fits the request: quick chat reply, a code file for longer programs, or a document if you ask for one
- Casual, calm, warm tone, and it mirrors your language, including Hinglish
- Honest: it never claims code works unless it has been run or traced

## Example

Input (Starter level):

```python
for i in range(1, 5):
    print(i)
```

"I wanted 1 to 5."

Output (short version):

> Good news, this is a really common one. `range(1, 5)` starts at 1 and stops *before* 5, like a fence you don't step over. So 5 never prints.
>
> Wanna try fixing it yourself? Give it a shot, and if you get stuck, just say so and I'll write it out for you.

## Install

### Claude (web and apps)

1. Download this repo as a ZIP (or zip the `code-buddy` folder yourself). Make sure `SKILL.md` sits at the top level of the folder inside the ZIP.
2. Open Claude's settings and find the Skills section.
3. Upload the ZIP and turn the skill on.

### Claude Code

Copy the folder into your skills directory:

```bash
git clone https://github.com/zakiuhh/code-buddy.git
cp -r code-buddy ~/.claude/skills/
```

(Change the clone URL if your repo lives somewhere else.)

## Repo structure

```
code-buddy/
├── assets/
│   ├── logo-dark.png    # for dark backgrounds
│   └── logo-light.png   # for light backgrounds
├── LICENSE
├── README.md
└── SKILL.md             # the actual skill
```

## Customizing

All the behavior lives in `SKILL.md`. Edit the levels, the tone rules, or the examples to fit how you like to work. Keep the `name` in the frontmatter the same as the folder name.

## License

MIT. See [LICENSE](LICENSE).
