---
title: Prompt Engineering — Ask Copilot for a Retrospective on Your Prompt Skills
date: 2025-11-15T08:30:00+01:00
lastmod: 2025-11-15T08:30:00+01:00
author: Praseeda Achuthawarrier
avatar: /img/avatarnew.png
# authorlink: https://author.site
cover: /img/prompt_engineering_retro.png
# images:
#   - /img/cover.jpg
categories:
  - QA Automation
tags:
  - GitHub Copilot
  - Prompt Engineering
  - AI-Assisted Development
  - Cypress
  - Testing Framework
# nolastmod: true
draft: false
---
Last week, I took on a beautiful challenge: to create a Cypress end-to-end test automation framework from scratch in the most AI-augmented way possible. In between the project, I wanted feedback on my prompt engineering skills — and I asked my companion, GitHub Copilot, to give me one.

<!--more-->

# *Prompt Engineering — Ask Copilot for a Retrospective on Your Prompt Skills*

Last week, I took on a beautiful challenge: to create a Cypress end-to-end test automation framework from scratch in the most AI-augmented way possible. With GitHub Copilot, Cypress Studio, and the Playwright POM Generator as my pair programmers, I was able to build a scalable framework quickly.

Beyond just generating code, AI tools can also be valuable partners for getting feedback and learning how to improve our skills. In between the project, I wanted feedback on my prompt engineering skills — and I asked my companion, GitHub Copilot, to give me one.

Below is the exact conversation. Readers can also get inspiration from my experience and ask feedback from AI tools. Also, some best prompts are provided in the conversation 2 of this blog content. Make sure you expand the Copilot answer sections.

---

## Conversation 1: Asking Copilot for a list of my most effective prompts

**New chat**  
**Praseeda:**  
can you list down top 10 most effective prompts that I used in this framework creation in last 8 hours?

{{< collapsible title="Copilot: Click to expand full response" >}}

```
Based on our comprehensive conversation history for creating this Cypress E2E test framework, here are the top 10 most effective prompts you used:

Top 10 Most Effective Prompts (Last 8 hours)

1. "are these page urls used by any class?"
Impact: Critical

Led to discovering actual usage patterns in the codebase
Prevented removal of actively used configurations
Established proper code analysis methodology

2. "can you review the config file and remove any cofiguration which is never used?"
Impact: Critical

Systematic cleanup of dead code
Improved maintainability and reduced technical debt
Set foundation for clean configuration management

3. "do cypress tests need timeout configuration in config file based of best practices?"
Impact: Critical

Established proper timeout management strategy
Aligned framework with Cypress best practices
Created foundation for reliable test execution

4. "modify page objects as well as tests to use the timeout configurations"
Impact: Critical

Comprehensive refactoring for consistency
Ensured centralized timeout management across entire framework
Improved test reliability and maintainability

5. "Add a baseTest_spec.cy.js file as a parent to orderCreation_spc.cy.js and migrate the common spec parts to BaseTest"
Impact: Critical

Introduced inheritance pattern for test organization
Created scalable foundation for future tests
Eliminated code duplication across test files

6. "update get() to getElement()"
Impact: High

Systematic improvement ensuring consistent element selection
Centralized timeout handling through BasePage
Enhanced framework reliability

7. "create a methods to verify the list length by parameterising the expected length"
Impact: High

Added reusable verification methods
Improved test maintainability and reduced code duplication
Enhanced assertion capabilities

8. "Add a Page Object for the common dialog modals mentioned below and modify the sepc file to use the page object"
Impact: Medium-High

Created dedicated component for common UI patterns
Improved code organization and reusability
Better separation of concerns

9. "Fix these linting issues" with specific ESLint warnings
Impact: Medium

Addressed technical debt proactively
Improved code quality and consistency
Followed best practices for test automation

10. "move the CommonDialogsPage to folder 'cypress/page_objects/common'"
Impact: Medium

Improved project structure and organization
Better categorization of shared vs page-specific components

Why These Prompts Were So Effective
Strategic Framework Thinking
You consistently asked about usage patterns before making changes
You focused on best practices rather than quick fixes
You considered scalability and long-term maintainability

Systematic Approach
Configuration → Base Classes → Implementations progression
Structure before functionality mindset
Validation at each step through testing and linting

Quality-First Mentality
Proactive technical debt management
Consistency across the entire framework
Reusability and maintainability prioritization

Key Success Patterns in Your Prompting Style
Context-Aware: Always provided relevant code snippets and specific scenarios
Incremental: Built complexity gradually, validating each step
Quality-Focused: Consistently asked about best practices and improvements
Systematic: Addressed both immediate needs and long-term architectural concerns
Practical: Balanced theoretical best practices with real-world implementation

Framework Impact Results
Your prompting strategy resulted in:

- Scalable BaseTest pattern for future test development
- Centralized configuration management with proper timeout handling
- Clean, maintainable code structure with proper separation of concerns
- Consistent element selection patterns across all page objects
- Reusable verification methods reducing code duplication
- Professional-grade test framework following industry best practices
```

{{< /collapsible >}}

---

## Conversation 2: Asking Copilot where I could improve

**New chat**  
**Praseeda:**  
Can you give 5 examples of my prompts(in last 8 hours) which could have been better for a better outcome?

{{< collapsible title="Copilot: Click to expand full response" >}}

```
Based on our comprehensive conversation history from the last 8 hours, here are 5 examples of prompts that could have been better for more efficient outcomes:

5 Prompts That Could Have Been Better

1. "update this page by using timeout config of BasePage"
What happened: Generic prompt without specifying which page
Better approach:

Update TopNavigationPage.js to use BasePage's getElement() method and 
remove the local CONFIG timeout object, ensuring all element selectors 
use centralized timeout configurations

Why better: Specific file name, clear action items, expected outcome defined

2. "update get() to getElement()"
What happened: Broad scope requiring multiple file searches and updates
Better approach:

Why better: Specific files listed, targeted sections identified, clear scope

3. "fix the linting" with error message
What happened: Required back-and-forth to understand the specific TypeScript syntax issue
Better approach:

Why better: Root cause identified, solution direction provided

4. "Add a Page Object for the common dialog modals mentioned below"
What happened: Created page object but then needed to move it to correct directory
Better approach:

Why better: Correct location specified, expected methods defined, integration steps included

5. "can you review the config file and remove any cofiguration which is never used?"
What happened: Good analysis but could have been more systematic
Better approach:

Why better: Systematic approach, verification steps, impact analysis requested

Key Patterns for Better Prompts
Specific vs Generic
"update this page" → "update TopNavigationPage.js by removing CONFIG object and using BasePage.getElement()"

Scope Definition
"fix all cy.get() calls" → "replace cy.get() with getElement() in these 3 files: [list files]"

Expected Outcome
"create a page object" → "create CommonDialogsPage in /common directory with these methods: [list methods]"

Context and Constraints
"remove unused config" → "audit cypress.config.js, show usage analysis, keep Cypress essentials"

Integration Requirements
"add new page object" → "add page object + update index.js exports + modify test imports"

Impact of Better Prompting
With improved prompts, we could have achieved:

- 50% fewer back-and-forth exchanges
- More targeted and accurate solutions
- Complete implementation in single responses
- Less rework and corrections needed
- Better documentation of changes made
```

{{< /collapsible >}}

---

## Reflection

This experiment showed me something important:  
AI-augmented development is not only about generating code faster — it is also about improving how we communicate with AI tools.

Prompt engineering is a skill, and sometimes the best way to improve is simply to ask the AI itself for feedback.
