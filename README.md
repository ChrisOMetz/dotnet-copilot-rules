# 🤖 .NET GitHub Copilot Rules

A collection of [GitHub Copilot AI rules](https://code.visualstudio.com/docs/copilot/copilot-customization) for .NET development best practices.

> [!TIP]
> You can enhance Copilot's chat responses by providing it with contextual details about your team's workflow, tools, or project specifics.

## 📚 Available Rule Sets

This set of rules is a good starting point and should be customized to fit your specific needs. You can add or remove rules as necessary.


### 💻 [C# Development](.vscode/rules/csharp/)

Rules for writing clean, maintainable C# code:
- ✨ Modern C# coding patterns
- 🧪 Testing best practices
- 📁 Code organization
- 🛡️ Error handling
- 🔌 Dependency management

* Code-generation instructions
  * [csharp/coding-guidelines.md](.vscode/rules/csharp/coding-guidelines.md)
  * [csharp/coding-style.md](.vscode/rules/csharp/coding-style.md)
* Test-generation instructions
  * [csharp/testing-xunit.md](.vscode/rules/csharp/testing-xunit.md)

### ⏳ [Git](.vscode/rules/git-message.md)

* Commit message generation instructions
  * [git-message.md](.vscode/rules/git-message.md)

## 📝 Available Prompts

Prompt files (prompts) let you build and share reusable prompt instructions with additional context.

- Pros and Cons Prompt - [prompts/pros-and-cons.prompt.md](.vscode/prompts/pros-and-cons.prompt.md)

<!-- 
* Code-generation instructions
  * [csharp/coding-guidelines.md](.vscode/rules/csharp/coding-guidelines.md)
  * [csharp/coding-style.md](.vscode/rules/csharp/coding-style.md)
* Test-generation instructions
* Code review instructions
* Commit message generation instructions
* Pull request title and description generation instructions -->

See more at [Custom instructions for GitHub Copilot in VS Code](https://code.visualstudio.com/docs/copilot/copilot-customization)

## How to Use This Repository

Copy the relevant rules you want to use into your project's `.vscode/rules` directory and configure `github.copilot.chat.codeGeneration.instructions`.

Here is an example of how to set up your `.vscode/settings.json` file:

```json
{
    "github.copilot.chat.codeGeneration.instructions": [
        {
            "file": ".vscode/rules/csharp/coding-guidelines.md"
        },
        {
            "file": ".vscode/rules/csharp/coding-style.md"
        }
    ],
    "github.copilot.chat.reviewSelection.enabled": true,
    "github.copilot.chat.testGeneration.instructions": [
        {
            "file": ".vscode/rules/csharp/testing-xunit.md"
        }
    ],
    "chat.promptFiles": true,
    "chat.promptFilesLocations": {
        ".github/prompts": true,
        ".vscode/prompts": true
    }
}
```

## 🚀 Motivation

### Treating AI like a teammate!

If you want to build a successful and maintainable project, you need to make sure that your code is clean, maintainable, and idiomatic. This is where *coding guidelines* come in.

Coding guidelines ensure consistency, readability, and maintainability in a project. Documenting them helps developers follow best practices, streamline collaboration, and reduce technical debt.

With AI coding tools and agents becoming integral team members, clear coding guidelines are more important than ever. These tools assist in generating, refactoring, and reviewing code, but they rely on well-defined rules to align with project standards. Documenting coding guidelines provides essential context, ensuring AI-generated code maintains consistency, readability, and best practices. Without structured rules, AI contributions may introduce inconsistencies, increasing technical debt and maintenance overhead.

### Documentation

Document your coding guidelines so it can be consumed by AI tools. Not only it can be used for additional context for code generation, but also now you can chat with LLMs about your coding guidelines. It becomes integral part of your project.

💡 For example, you can ask Copilot for a review of your code and it will be able to refer to the coding guidelines you provided.

### Agent Mode

With an introduction of [Agent Mode](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode) it is even more important to have clear guidelines otherwise how you expect consistency and independence from AI agents?

## 💳 Credits

Inspired by <https://github.com/Aaronontheweb/dotnet-cursor-rules>
