# Commit Command

This command analyzes staged files and creates logical commit groups based on file relationships and changes.

## Usage

```
/commit
```

## Command Implementation

When this command is executed, perform the following steps:

1. **Check Git Status**
   - Verify we're in a git repository
   - Check if there are staged files ready to commit

2. **Analyze Staged Changes**
   - Use `git diff --cached` to see staged changes
   - Use `git diff --cached --name-only` to get list of staged files
   - Analyze file paths and change types to identify logical groups

3. **Group Related Files**
   - Group files by directory/module
   - Group files by change type (new features, bug fixes, refactoring)
   - Group files that are logically related (e.g., model + migration, component + test)

4. **Create Logical Commits**
   - For each group, create a separate commit
   - Generate appropriate commit messages based on the changes
   - Use conventional commit format when appropriate

## Grouping Logic

### File Relationship Patterns
- **Frontend Components**: Group component files with their styles, tests, and stories
- **Backend Features**: Group models, services, controllers, and tests for the same feature
- **Configuration Changes**: Group related config files together
- **Documentation**: Group documentation updates separately
- **Dependencies**: Group package.json/requirements.txt with lock files

### Change Type Detection
- **Feature**: New files or significant additions
- **Fix**: Changes to existing files that appear to be bug fixes
- **Refactor**: Code reorganization without functional changes
- **Style**: Formatting, linting, or style-only changes
- **Test**: Test file additions or modifications
- **Docs**: Documentation changes
- **Config**: Configuration file changes

## Commit Message Format

Generate commit messages that:
- Are concise but descriptive
- Use conventional commit format when appropriate (feat:, fix:, refactor:, etc.)
- Focus on the "what" and "why" rather than technical details
- DO NOT include Claude attribution

### Examples
- `feat: add user authentication system`
- `fix: resolve memory leak in data processing`
- `refactor: simplify error handling logic`
- `test: add unit tests for payment service`
- `docs: update API documentation`

## Implementation Instructions

1. **Git Status Check**
   ```bash
   git status --porcelain
   ```

2. **Get Staged Files**
   ```bash
   git diff --cached --name-only
   ```

3. **Analyze Changes**
   ```bash
   git diff --cached
   ```

4. **Create Commits**
   - Use `git reset HEAD <files>` to unstage files temporarily
   - Use `git add <files>` to stage specific groups
   - Use `git commit -m "<message>"` for each group
   - Repeat for all groups

## Safety Measures

- Always verify staged changes before committing
- Confirm with user if creating multiple commits
- Show preview of planned commits before execution
- Ensure no files are lost during the grouping process

## Error Handling

- Check if repository is clean (no uncommitted changes)
- Handle cases where no files are staged
- Handle cases where files can't be grouped logically
- Provide clear error messages for git command failures