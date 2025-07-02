# 🤖 .NET GitHub Copilot Rules

A collection of [GitHub Copilot AI rules](https://code.visualstudio.com/docs/copilot/copilot-customization) for .NET development best practices.

> [!TIP]
> You can enhance Copilot's chat responses by providing it with contextual details about your team's workflow, tools, or project specifics.

## 📚 Customizations: Instructions, Prompts, MCPs, etc.

This set of rules is a good starting point and should be customized to fit your specific needs. You can add or remove rules as necessary.

### 💻 .NET Development

Rules for writing clean, maintainable C# code:
- ✨ Modern C# coding patterns
- 🧪 Testing best practices
- 📁 Code organization
- 🛡️ Error handling
- 🔌 Dependency management

* Code-generation instructions - [csharp/coding-guidelines.md](.vscode/instructions/coding-guidelines.instructions.md), [csharp/coding-style.md](.vscode/instructions/coding-style.instructions.md)
* Test-generation instructions -  [csharp/testing-xunit.md](.vscode/instructions/testing-xunit.instructions.md)

### ⏳ [Git](.vscode/git-message.instructions.md)

* Commit message generation instructions - [git-message.md](.vscode/git-message.instructions.md)

### Tools

Here is my top content extraction tools for GitHub Copilot:

* `#fetch` - fetch web page
* `#githubRepo` - fetch remote GitHub repository
* `#context7` - fetch docs
* `#codebase` - work with the code base

### MCP Servers

More at <https://www.mcpevals.io/blog/mcp-inspector-guide>

```bash
npx @modelcontextprotocol/inspector --config .vscode/.mcp.json --server microsoft.docs.mcp
```

* https://code.visualstudio.com/mcp

## How to Use This Repository

Copy the relevant instructions you want to use into your project's `.vscode/instructions` directory and configure `github.copilot.chat.codeGeneration.instructions` if needed.

Here is an example of how to set up your `.vscode/settings.json` file:

```json
{
  "chat.promptFiles": true,
  "chat.promptFilesLocations": {
    ".vscode/prompts": true
  },
  "chat.instructionsFilesLocations": {
    ".vscode/instructions": true
  },
  "github.copilot.chat.codeGeneration.instructions": [],
  "github.copilot.chat.commitMessageGeneration.instructions": [
    {
      "file": ".vscode/git-message.instructions.md"
    }
  ],
  "github.copilot.chat.reviewSelection.enabled": true,
  "github.copilot.chat.reviewSelection.instructions": [
    {
      "file": ".vscode/instructions/coding-guidelines.instructions.md"
    },
    {
      "file": ".vscode/instructions/coding-style.instructions.md"
    }
  ],
  "github.copilot.chat.testGeneration.instructions": [
    {
      "file": ".vscode/instructions/testing-xunit.instructions.md"
    }
  ]
}
```

## 🚀 Motivation

### Productivity

You can create reusable instructions and prompts for your team to handle common tasks and GenAI scenarios effectively.

### Coding with Agents in Mind

Shift your mindset from being a code typist to an AI operator when appropriate. Start with an instruction prompt and gather as much context as possible. Once you clearly understand the task, determine the level of AI assistance needed.

💡 To stay in the "Productivity Zone", gain experience with various AI models.

### Treat AI as a Teammate

Building a successful, maintainable project requires clean, idiomatic, and consistent code. This is where *coding guidelines* are essential. They:
- Promote consistency, readability, and maintainability.
- Streamline collaboration and reduce technical debt.
- Provide context for AI tools, ensuring generated code aligns with project standards.

Without clear guidelines, AI contributions may introduce inconsistencies, increasing maintenance overhead.

### Documentation

Document your coding guidelines so it can be consumed by AI tools. Not only can it be used for additional context for code generation, but also now you can chat with LLMs about your coding guidelines. It becomes integral part of your project.

💡 For example, you can ask Copilot to review your code, and it will refer to the guidelines you provided.

### Agent Mode

With the introduction of [Agent Mode](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode), clear guidelines are crucial. They ensure consistency and independence in AI-generated contributions.

## Code Formatting and Linting

Although, coding guidelines could hint AI to generate code in a specific way, it is not a replacement for code formatting and linting tools. Further more, AI could disrupt your code formatting so make sure to use formatters and analyzers to keep your code clean and consistent.

## Changelog:

* New release <https://code.visualstudio.com/updates/v1_100> introduces a better way to provide context to Copilot. 
  * Custom Instructions (user/workspace)
  * Custom Prompts (user/workspace)

## Blogs

* https://nikiforovall.blog/productivity/2025/03/08/github-copilot-instructions-for-dotnet.html
* https://nikiforovall.blog/productivity/2025/04/19/github-copilot-prompt-engineering.html
* https://nikiforovall.blog/productivity/2025/05/03/github-copilot-prompt-engineering-code-review.html

## 💳 Credits

Inspired by <https://github.com/Aaronontheweb/dotnet-cursor-rules>
