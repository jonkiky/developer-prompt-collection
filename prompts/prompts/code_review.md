# Code Review Prompts

This guide provides structured templates for conducting effective code reviews and getting actionable feedback.

## 🔍 General Code Review Template

```
As an experienced code reviewer, please review this code:

1. Code Context:
- Purpose: [What the code does]
- Language/Framework: [Tech stack]
- Changes: [What's being modified]
- Dependencies: [Related systems]

2. Review Focus Areas:
- Functionality: [Does it work]
- Performance: [Speed/efficiency]
- Security: [Vulnerabilities]
- Maintainability: [Code quality]

3. Specific Checks:
- Logic: [Business logic correctness]
- Error Handling: [Edge cases]
- Tests: [Test coverage]
- Documentation: [Comments/docs]
```

Example:
```
As an experienced code reviewer, please review this code:

1. Code Context:
- Purpose: User authentication service implementation
- Language/Framework: Node.js with Express, TypeScript
- Changes: Adding JWT authentication and password hashing
- Dependencies: bcrypt, jsonwebtoken, express-validator

2. Review Focus Areas:
- Functionality: JWT token generation and validation
- Performance: Password hashing optimization
- Security: Password storage, token security
- Maintainability: Service layer organization

3. Specific Checks:
- Logic: Token expiration and refresh flow
- Error Handling: Invalid credentials, expired tokens
- Tests: Auth middleware and service unit tests
- Documentation: API endpoints and security measures

Code to review:
```typescript
import { hash, compare } from 'bcrypt';
import { sign, verify } from 'jsonwebtoken';
import { Request, Response } from 'express';

export class AuthService {
  private readonly SALT_ROUNDS = 10;
  private readonly JWT_SECRET = process.env.JWT_SECRET || 'default-secret';

  async hashPassword(password: string): Promise<string> {
    return hash(password, this.SALT_ROUNDS);
  }

  async login(email: string, password: string): Promise<string | null> {
    const user = await this.userRepository.findByEmail(email);
    if (!user) return null;

    const isValid = await compare(password, user.passwordHash);
    if (!isValid) return null;

    return sign({ userId: user.id }, this.JWT_SECRET, { expiresIn: '1h' });
  }

  async validateToken(token: string): Promise<any> {
    try {
      return verify(token, this.JWT_SECRET);
    } catch {
      return null;
    }
  }
}
```
```

## 🎯 Pull Request Review Template

```
Please review this pull request:

1. Change Overview:
- Purpose: [Why these changes]
- Scope: [What's affected]
- Impact: [Expected outcomes]
- Risk Level: [Potential issues]

2. Technical Review:
- Architecture: [Design choices]
- Code Quality: [Style/standards]
- Performance: [Efficiency]
- Security: [Vulnerabilities]

3. Implementation Details:
- Logic Changes: [Core changes]
- Edge Cases: [Corner cases]
- Tests: [Coverage/quality]
- Documentation: [Updates needed]

4. Deployment Considerations:
- Dependencies: [What's needed]
- Migration: [Data changes]
- Rollback: [Backup plan]
- Monitoring: [What to watch]
```

## 🔄 Refactoring Suggestion Template

```
Please suggest refactoring for this code:

1. Current State:
- Code Issues: [Problems found]
- Pain Points: [Maintenance issues]
- Technical Debt: [Legacy concerns]
- Performance: [Speed issues]

2. Improvement Areas:
- Architecture: [Structure changes]
- Patterns: [Design patterns]
- Standards: [Best practices]
- Tools: [Helper libraries]

3. Refactoring Plan:
- Priority: [What to fix first]
- Steps: [How to refactor]
- Benefits: [Expected gains]
- Risks: [Potential issues]

4. Validation Strategy:
- Tests: [Coverage needed]
- Performance: [Metrics to check]
- Review: [Validation steps]
```

## 💡 Code Style Review Template

```
Review this code for style and standards:

1. Style Guidelines:
- Naming: [Conventions check]
- Formatting: [Layout/spacing]
- Organization: [Structure]
- Comments: [Documentation]

2. Best Practices:
- Language: [Language standards]
- Framework: [Framework patterns]
- Team: [Team conventions]
- Industry: [Common practices]

3. Improvements:
- Required: [Must-fix items]
- Suggested: [Nice-to-have]
- Examples: [How to fix]
```

## 🎓 Learning-Focused Review Template

```
Please provide an educational code review:

1. Code Analysis:
- Patterns: [Design patterns used]
- Architecture: [Structure choices]
- Algorithms: [Implementation]
- Tools: [Library usage]

2. Learning Points:
- Best Practices: [What's good]
- Anti-patterns: [What to avoid]
- Alternatives: [Other approaches]
- Resources: [Where to learn more]

3. Improvement Guide:
- Quick Wins: [Easy fixes]
- Deep Learning: [Advanced topics]
- Examples: [Better approaches]
- Practice: [Exercises]
```

## Tips for Better Code Review Prompts

1. Provide context:
   - Project background
   - Team standards
   - Performance requirements
   - Security needs

2. Specify review focus:
   - Critical areas
   - Known concerns
   - Time constraints
   - Required depth

3. Ask for:
   - Concrete examples
   - Alternative solutions
   - Trade-off analysis
   - Learning resources