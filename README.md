# awesome-ai-tutorials

A collection of AI tutorials and custom Claude commands for code analysis and development workflows.

## Custom Claude Commands

This repository contains a collection of custom commands for Claude Code that enhance development workflows and code analysis capabilities. All commands are stored in the `claude/commands/` directory.

### Available Commands

#### [Analysis Command](claude/commands/analysis.md)
- **Usage**: `/analysis:${DIRECTORY_PATH}`
- **Purpose**: Analyzes codebase directory structure and provides architectural insights with Mermaid diagrams

Provides comprehensive analysis including:
- Directory structure and file organization
- Architecture patterns and component relationships
- Code quality insights and recommendations
- Visual diagrams showing system architecture

**Examples:**
- `/analysis:src` - Analyze the src directory
- `/analysis:.` - Analyze the entire project root

#### [Commit Command](claude/commands/commit.md)
- **Usage**: `/commit`
- **Purpose**: Analyzes staged files and creates logical commit groups based on file relationships and changes

Provides intelligent commit management including:
- Automated analysis of staged changes
- Logical grouping of related files
- Multiple commits for different feature areas
- Conventional commit message generation
- No Claude attribution in commit messages

**Examples:**
- `/commit` - Analyze staged files and create grouped commits

### How to Use Commands

1. **With Claude Code CLI**: Use the commands directly in your Claude Code session
2. **Command Format**: Each command follows the pattern `/${COMMAND_NAME}:${PARAMETERS}`
3. **File Structure**: Commands are documented in individual `.md` files with detailed implementation instructions

### Adding New Commands

To add a new command:

1. Create a new `.md` file in `claude/commands/`
2. Follow the existing command structure:
   - Command description and purpose
   - Usage syntax and examples
   - Implementation instructions
   - Expected output format
3. Update this README with the new command details

### Command Development Guidelines

- **Clear Documentation**: Each command should have comprehensive usage examples
- **Consistent Format**: Follow the established pattern for command syntax
- **Implementation Details**: Include step-by-step instructions for Claude to execute
- **Output Specification**: Define expected output format and structure
- **Error Handling**: Consider edge cases and error scenarios