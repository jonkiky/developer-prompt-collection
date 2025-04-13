# Code Generation Prompts

This guide helps you create effective prompts for generating code. Follow these structured templates to get better results.

## 🎯 Setting Clear Goals

Start your prompt with clear objectives:
"As an expert [language] developer, please help me create..."
"I need a [type] function that accomplishes [specific goal]..."

## 💡 Function Generation

Template:
```
As a [language] expert, please create a function that:
- Purpose: [clear description of what the function should do]
- Inputs: [describe expected parameters]
- Output: [describe expected return value]
- Constraints: [any performance/style requirements]
- Error handling: [how to handle edge cases]

Example code style I'd like to follow:
[paste a small code snippet showing your preferred style]
```

Example:
"As a Python expert, please create a data validation function that:
- Purpose: Validates user input for a registration form
- Inputs: username (string), age (integer), email (string)
- Output: Boolean + list of validation errors
- Constraints: Must complete validation in O(1) time
- Error handling: Return specific error messages for each validation failure

Example style:
```python
def validate_user(data: dict) -> tuple[bool, list]:
    # Similar to this style
    pass
```"

## 🧩 Component Development

Template:
```
Please help me create a [framework] component with these specifications:
1. Component purpose: [describe what it should do]
2. Props/Parameters: [list required and optional props]
3. Desired behavior: [describe interactions/animations]
4. Error states: [how to handle errors]
5. Style requirements: [describe visual needs]

Example of similar component:
[paste example code or describe similar component]
```

## 📝 Script Generation

Template:
```
I need a script to [specific task]. Please consider:
1. Environment: [where will this run]
2. Input: [what data/parameters needed]
3. Output: [expected results]
4. Error handling: [how to handle failures]
5. Performance needs: [any specific requirements]

Reference example:
[similar script or pseudocode]
```

## 🔄 Iterative Refinement

If the generated code isn't quite right:
- "Could you modify the [specific part] to handle [edge case]?"
- "The code works but needs to be more [requirement]. Can you optimize it for [specific goal]?"
- "Please add error handling for [specific scenario]"

## 🎨 Style Preferences

Always specify:
- Preferred naming conventions
- Code organization preferences
- Documentation style
- Error handling approach

Example:
"Please follow these style preferences:
- Use camelCase for variables
- Include JSDoc comments for functions
- Group related functions together
- Use early returns for error handling"