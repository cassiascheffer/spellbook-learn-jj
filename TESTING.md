# Testing the JJ Tutorial Plugin

## Local Testing Instructions

### 1. Install the Plugin Locally

```bash
# Create plugins directory if it doesn't exist
mkdir -p ~/.claude/plugins

# Link this plugin
ln -s /Users/cassidy/code/learn-jj/jj-tutorial-plugin ~/.claude/plugins/jj-tutorial

# Verify the link
ls -l ~/.claude/plugins/jj-tutorial
```

### 2. Test in Claude Code

```bash
# Start Claude Code in any directory
claude-code

# Run the tutorial command
/learn-jj
```

### 3. Expected Behavior

Claude should:
1. ✓ Check for existing `jj-practice` directory
2. ✓ Ask if starting fresh or continuing
3. ✓ Create a TodoWrite list with 8 lessons
4. ✓ Verify jj is installed
5. ✓ Check user configuration
6. ✓ Guide through Lesson 1 setup

### 4. Test Scenarios

**Scenario 1: First Time User**
- No `jj-practice` directory exists
- Should start from Lesson 1
- Should create practice repo
- Should verify user identity

**Scenario 2: Continuing User**
- `jj-practice` directory exists
- Should ask which lesson to continue from
- Should restore TodoWrite progress
- Should allow jumping to specific lessons

**Scenario 3: Questions During Tutorial**
- User asks "How is this different from Git?"
- Claude should answer immediately
- Should provide examples in practice repo
- Should continue tutorial after answering

### 5. Verification Points

For each lesson, Claude should:
- ✓ Explain the concept clearly
- ✓ Demonstrate with an example
- ✓ Guide user through exercise
- ✓ Ask for command output
- ✓ Verify the output
- ✓ Provide specific feedback
- ✓ Mark lesson as completed when done

### 6. Common Issues to Test

**Issue**: Command not found
- Solution: Verify plugin is symlinked correctly

**Issue**: jj not installed
- Solution: Claude should detect and guide user to install

**Issue**: User gets stuck on an exercise
- Solution: Claude should help debug, show examples, offer to demonstrate

### 7. Manual Test Checklist

- [ ] Plugin installs correctly
- [ ] `/learn-jj` command is recognized
- [ ] Claude creates TodoWrite list
- [ ] Claude checks for jj installation
- [ ] Practice repo is created
- [ ] Lessons progress sequentially
- [ ] User can ask questions anytime
- [ ] Claude verifies command output
- [ ] Can continue from previous session
- [ ] Can jump to specific lessons

### 8. Quick Test Script

Run this to test the basic flow:

```bash
# Install plugin
mkdir -p ~/.claude/plugins
ln -sf /Users/cassidy/code/learn-jj/jj-tutorial-plugin ~/.claude/plugins/jj-tutorial

# Start Claude Code
claude-code

# In Claude Code, run:
# /learn-jj
# Answer "yes" to starting fresh
# Follow Lesson 1 instructions
# Verify Claude checks your output
```

## Debugging

If the command doesn't work:

1. Check plugin location:
   ```bash
   ls -la ~/.claude/plugins/jj-tutorial
   ```

2. Check plugin.json is valid:
   ```bash
   cat ~/.claude/plugins/jj-tutorial/plugin.json | jq .
   ```

3. Check command file exists:
   ```bash
   ls ~/.claude/plugins/jj-tutorial/commands/learn-jj.md
   ```

4. Restart Claude Code completely

## Next Steps After Testing

Once testing is successful:
1. Consider publishing to Claude Code marketplace
2. Gather user feedback
3. Iterate on lesson content
4. Add more advanced lessons if needed
