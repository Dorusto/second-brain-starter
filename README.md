# Second Brain Starter

Most note-taking templates hand you someone else's system. This one starts with questions.

Claude Code asks what you want from your notes and why your last system stopped working. It then proposes a few small pieces, such as a rule, a file, a routine, an automatic check or a tool. Nothing is created or installed until you say yes to that piece.

It answers in your language.

## What you need

- [Claude Code](https://code.claude.com/docs/en/overview) and a Claude account
- A folder for your notes, new or existing

You don't need Obsidian, a server or any particular method. Your notes stay as plain files on your computer. If Claude suggests a tool that sends them elsewhere, it has to tell you before you agree.

## Install

Run these once, in your terminal:

```bash
claude plugin marketplace add Dorusto/second-brain-starter
claude plugin install second-brain@second-brain-starter
```

## Use

Go to your notes folder and start Claude Code:

```bash
mkdir -p ~/notes && cd ~/notes
claude
```

Then type:

```
/second-brain:start
```

Set aside about 20 minutes. Use real examples when you answer, such as the idea you lost last week or the project you dropped. The more specific you are, the less you'll end up with, and that's the point.

Say no to anything you don't see yourself using. To change the system later, open Claude Code in the same folder and say what you stopped using.

## What it can change

- It works only in the folder where you started it, unless you agree to something else.
- It explains each change before making it, and how to undo it.
- It shows you the code of anything that would run automatically.
- Before installing a tool, it tells you where the tool comes from, what it can access and what it costs.

Claude can still make mistakes, so read what it proposes before you say yes. If your folder already holds notes you care about, make a copy first.

## Try it in a throwaway container

To try it without touching your computer, use Docker:

```bash
docker run -it --rm node:22 bash -c '
  npm install -g @anthropic-ai/claude-code &&
  claude plugin marketplace add Dorusto/second-brain-starter &&
  claude plugin install second-brain@second-brain-starter &&
  mkdir -p ~/notes && cd ~/notes && claude'
```

You'll need to log in to Claude inside the container. Everything in it disappears when you exit.

## Remove

```bash
claude plugin uninstall second-brain@second-brain-starter
claude plugin marketplace remove second-brain-starter
```

This removes the plugin. Your notes and the pieces built in your folder stay.

## License

[MIT](LICENSE)
