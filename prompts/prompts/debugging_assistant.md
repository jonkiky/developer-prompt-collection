# Debugging Assistant Prompts

This guide provides structured templates for debugging code issues effectively. Each template is designed to help you get precise, actionable debugging assistance.

## 🔍 Error Analysis Template

```
As an experienced debugger, please help me analyze this error:

1. Error Message/Behavior:
[Paste exact error message or describe unexpected behavior]

2. Context:
- Language/Framework: [e.g., Python 3.9, React 18]
- Environment: [e.g., local development, production]
- Recent changes: [Any relevant code changes]

3. Code snippet where error occurs:
```[language]
[Your code here]
```

4. What I've tried so far:
- [List debugging steps already taken]
- [List attempted solutions]
```

Example:
```
As an experienced debugger, please help me analyze this error:

1. Error Message/Behavior:
TypeError: Cannot read property 'map' of undefined
at UserList.render (UserList.js:15)

2. Context:
- Language/Framework: React 18, TypeScript 4.8
- Environment: Local development
- Recent changes: Added user filtering feature

3. Code snippet where error occurs:
```typescript
class UserList extends React.Component<Props, State> {
  render() {
    return (
      <div className="user-list">
        {this.props.users.map(user => (
          <UserCard key={user.id} user={user} />
        ))}
      </div>
    );
  }
}
```

4. What I've tried so far:
- Added console.log to check this.props.users value
- Verified API response in Network tab
- Added null check before map
- Checked Redux store initialization
```

## 🎯 Performance Debugging Template

```
I need help optimizing this [language] code:

1. Current Performance:
- Execution time: [current metrics]
- Resource usage: [memory/CPU usage]
- Scale: [data size/user load]

2. Code to optimize:
```[language]
[Your code here]
```

3. Performance targets:
- Desired execution time: [target]
- Resource constraints: [limits]
- Scale requirements: [expected load]

4. Profiling data (if available):
[Include profiling results]
```

## 🔄 Runtime Behavior Template

```
Help me understand why this code isn't behaving as expected:

1. Expected behavior:
[Describe what should happen]

2. Actual behavior:
[Describe what is happening]

3. Reproducible example:
```[language]
[Minimal code that shows the issue]
```

4. Input/Output:
- Input data: [example input]
- Expected output: [what you want]
- Actual output: [what you get]
```

## 💡 Debug Strategy Request

```
Please help me create a debugging strategy for:

1. Issue description:
[Describe the problem]

2. System context:
- Architecture: [relevant system details]
- Dependencies: [related services/components]
- Environment: [where this runs]

3. Impact:
- Affected users/systems: [scope]
- Frequency: [how often it occurs]
- Severity: [impact level]

4. Available tools:
[List monitoring/debugging tools available]
```

## 🎓 Learning From Bugs Template

```
Help me understand and prevent this bug:

1. Bug description:
[What went wrong]

2. Root cause (if known):
[Why it happened]

3. Questions:
- How could this have been prevented?
- What patterns should I watch for?
- What best practices would help?

4. Future prevention:
- What tests could catch this?
- What guardrails needed?
```

## Tips for Better Debugging Prompts

1. Always include:
   - Complete error messages
   - Relevant code context
   - Environment details
   - Steps to reproduce

2. Be specific about:
   - What you've already tried
   - What you're expecting
   - What actually happens

3. For complex issues:
   - Break down the problem
   - Start with minimal examples
   - Iterate with follow-up questions