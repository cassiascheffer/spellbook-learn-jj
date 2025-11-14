# JJ Tutorial Plugin

An interactive, hands-on tutorial for learning Jujutsu (jj), a modern version control system. This plugin provides a guided learning experience through Claude Code where you practice real commands, get your work verified, and ask questions along the way.

## What You'll Learn

This tutorial covers 8 progressive lessons:

1. **Initial Setup & Configuration** - Configure jj for first-time use
2. **Understanding the Working Copy Model** - Learn how jj's working copy differs from Git
3. **Making Your First Change** - Create and describe commits
4. **Exploring Log & Revsets** - Query commit history with powerful expressions
5. **Managing Multiple Changes** - Navigate between commits and understand change IDs
6. **Rebasing & Conflict Resolution** - Move commits and handle conflicts gracefully
7. **Operation Log & Undo** - Use jj's safety net to undo any operation
8. **Advanced Content Manipulation** - Split, squash, and edit commits surgically

## Features

- **Interactive**: Claude guides you through exercises and verifies your work
- **Hands-on**: Creates a practice repository where you try real commands
- **Flexible**: Start fresh or continue from where you left off
- **Question-friendly**: Ask questions anytime during the tutorial
- **Practical**: Uses realistic scenarios and actual command output
- **Progressive**: Builds from basics to advanced topics

## Prerequisites

- **Jujutsu installed**: Install from https://jj-vcs.github.io/jj/latest/install-and-setup/
  - macOS: `brew install jj`
  - Linux: See installation docs for your distribution
  - Windows: See installation docs

- **Claude Code**: This plugin requires Claude Code CLI

## Installation

### Option 1: Install from Claude Code Marketplace

```bash
# Once published to the marketplace
claude-code plugins install jj-tutorial
```

### Option 2: Install Locally

1. Clone or download this plugin:
   ```bash
   git clone <this-repo-url>
   # or download and extract the ZIP
   ```

2. Link to your Claude Code plugins directory:
   ```bash
   ln -s /path/to/jj-tutorial-plugin ~/.claude/plugins/jj-tutorial
   ```

3. Verify installation:
   ```bash
   claude-code /help
   # You should see /learn-jj in the available commands
   ```

## Usage

### Starting the Tutorial

In any directory, run:

```bash
/learn-jj
```

Claude will:
1. Check if you're starting fresh or continuing
2. Set up a practice repository (`jj-practice/`)
3. Guide you through the lessons interactively

### During the Tutorial

- **Follow along**: Claude will explain concepts and guide you through exercises
- **Run commands**: Try the commands Claude suggests in your terminal
- **Share output**: Paste command output so Claude can verify your work
- **Ask questions**: If you're confused or curious, just ask!
- **Take your time**: Go at your own pace, repeat lessons if needed

### Continuing Later

The tutorial creates a `jj-practice/` directory that persists between sessions. When you run `/learn-jj` again:

- Claude will detect your existing practice repo
- You can continue from where you left off
- Or jump to a specific lesson
- Or start fresh (will ask first)

## Example Session

```bash
$ claude-code

> /learn-jj

[Claude]: Welcome to the interactive Jujutsu tutorial!

I can see you don't have a practice repository yet. Are you ready to start
learning jj from the beginning?

> yes

[Claude]: Great! Let's start with Lesson 1: Initial Setup & Configuration.

First, let me verify that jj is installed...

[Tutorial proceeds with interactive exercises...]
```

## Tips for Success

1. **Actually run the commands** - Don't just read, practice!
2. **Share your output** - This lets Claude verify and provide specific feedback
3. **Ask questions** - If anything is unclear, ask immediately
4. **Use the practice repo** - Don't worry about making mistakes, that's what it's for
5. **Take breaks** - You can continue anytime, the practice repo persists
6. **Experiment** - Try variations of commands to deepen understanding

## What Makes This Tutorial Different

Unlike static tutorials or documentation:

- **Interactive verification**: Claude checks your actual command output
- **Adaptive**: Claude adjusts explanations based on your questions
- **Contextual help**: Get help exactly when you need it
- **Practical exercises**: Work with a real repository, not contrived examples
- **Safety**: Practice in a dedicated repo without fear of breaking anything

## Troubleshooting

**Command not found: `/learn-jj`**
- Verify plugin installation: check `~/.claude/plugins/` directory
- Restart Claude Code after installing the plugin

**jj not found**
- Install jj first: https://jj-vcs.github.io/jj/latest/install-and-setup/
- Verify with: `which jj`

**Want to start over completely**
- Delete the `jj-practice/` directory
- Run `/learn-jj` again

## Contributing

Found an issue or have a suggestion? Please open an issue or pull request!

## License

MIT

## Learn More

- **Jujutsu Documentation**: https://jj-vcs.github.io/jj/latest/
- **Jujutsu GitHub**: https://github.com/jj-vcs/jj
- **Tutorial Feedback**: [Link to issues]

---

Happy learning! Remember: jj is designed to be safe and reversible. Don't be afraid to experiment!
