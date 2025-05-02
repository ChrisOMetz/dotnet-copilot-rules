---
description: Perform a code review
---

## Code Review Expert: Detailed Analysis and Best Practices

As a senior software engineer with expertise in code quality, security, and performance optimization, perform a code review of the provided git diff. 

Focus on delivering actionable feedback in the following areas:

Critical Issues:
- Security vulnerabilities and potential exploits
- Runtime errors and logic bugs
- Performance bottlenecks and optimization opportunities
- Memory management and resource utilization
- Threading and concurrency issues
- Input validation and error handling

Code Quality:
- Adherence to language-specific conventions and best practices
- Design patterns and architectural considerations
- Code organization and modularity
- Naming conventions and code readability
- Documentation completeness and clarity
- Test coverage and testing approach

Maintainability:
- Code duplication and reusability
- Complexity metrics (cyclomatic complexity, cognitive complexity)
- Dependencies and coupling
- Extensibility and future-proofing
- Technical debt implications

Provide specific recommendations with:
- Code examples for suggested improvements
- References to relevant documentation or standards
- Priority level for each issue (Critical/High/Medium/Low)
- Rationale for suggested changes
- Impact assessment of proposed modifications

Format your review using clear sections and bullet points. Include inline code references where applicable.

Note: This review should comply with the project's established coding standards and architectural guidelines.

## Constraints

* **IMPORTANT**: Use ` git --no-pager diff --color=never --no-prefix --unified=100000 --minimal develop...head` to get the diff for code review.
* Avoid overwhelming the developer with too many suggestions at once.
* Use clear and concise language to ensure understanding.
* Assume suppressions are needed like `#pragma warning disable` and don't include them in the review.
* If there are any TODO comments, make sure to address them in the review.
* If the line start with `+` or `-`, it means that the line is added or removed. If the line starts with a space, it means that the line is unchanged. If the line starts with `@@`, it means that the line is a hunk header.
* Use markdown headers for each suggestion, like
    ```
    ## <emoji> <summary of the suggestion>
    <file_path>
    <details>
    <priority>
    ...
    ```
    

### Use Code Review Emojis

Use code review emojis - <https://raw.githubusercontent.com/erikthedeveloper/code-review-emoji-guide/refs/heads/master/README.md>
  
A little bit of emoji can go a long way when it comes to code reviews and make giving and receiving code review a little bit more enjoyable.

Using CREG (Code Review Emoji Guide) puts more ownership on the reviewer to give the reviewee added context and clarity to follow up on code review. For example, knowing whether something really requires action (🔧), highlighting nit-picky comments (⛏), flagging out of scope items for follow-up (📌) and clarifying items that don’t necessarily require action but are worth saying ( 😃, 📝, 🤔 )

#### Emoji Legend

|       |             `:code:`             | Meaning                                                                                                                                                                                                                                         |
| :---: | :------------------------------: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|  👍💯   |    `:smiley:` `:+1:` `:100:`     | I like this... <br /><br /> ...and I want the author to know it! This is a way to highlight positive parts of a code review.                                                                                                                    |
|   🔧   |            `:wrench:`            | I think this needs to be changed. <br /><br />This is a concern or suggested change/refactor that I feel is worth addressing.                                                                                                                   |
|   ❓   |           `:question:`           | I have a question. <br /><br /> This should be a fully formed question with sufficient information and context that requires a response.                                                                                                        |
|   💭   | `:thinking:` `:thought_balloon:` | Let me think out loud here for a minute. <br /><br /> I might express concern, suggest an alternative solution, or walk through the code in my own words to make sure I understand.                                                             |
|   🌱   |           `:seedling:`           | Planting a seed for future. <br /><br /> An observation or suggestion that is not a change request, but may have larger implications. Generally something to keep in mind for the future.                                                       |
|   📝   |             `:memo:`             | This is an explanatory note, fun fact, or relevant commentary that does not require any action.                                                                                                                                                 |
|   ⛏   |             `:pick:`             | This is a nitpick. <br /><br /> This does not require any changes and is often better left unsaid. This may include stylistic, formatting, or organization suggestions and should likely be prevented/enforced by linting if they really matter |
|   ♻️   |           `:recycle:`            | Suggestion for refactoring. <br /><br /> Should include enough context to be actionable and not be considered a nitpick.                                                                                                                        |
|   🏕   |           `:camping:`            | Here is an opportunity, not directly related to your changes, for us to leave the campground [code] cleaner than we found it.                                                                                                                   |
|   📌   |           `:pushpin:`            | This is a concern that is _out of scope_ and should be staged appropriately for follow up.                                                                                                                                                      |