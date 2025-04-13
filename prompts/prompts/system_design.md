# System Design Prompts

This guide provides structured templates for system design discussions and architecture planning.

## 🏗️ High-Level Design Template

```
As a senior system architect, help me design a system that:

1. System Requirements:
- Purpose: [Core functionality]
- Scale: [Expected load/users]
- Performance: [SLAs/latency requirements]
- Reliability: [Uptime/redundancy needs]

2. Key Components:
- Services: [Major system parts]
- Data Stores: [Storage requirements]
- External Systems: [3rd party integrations]
- Infrastructure: [Hosting/cloud needs]

3. Design Constraints:
- Budget: [Cost constraints]
- Technology: [Stack limitations]
- Timeline: [Development time]
- Team: [Available resources]

4. Expected Outcome:
- Architecture Diagram: [System overview]
- Component Details: [Service descriptions]
- Data Flow: [Information movement]
```

Example:
```
As a senior system architect, help me design a system that:

1. System Requirements:
- Purpose: E-commerce platform with real-time inventory
- Scale: 1M monthly active users, 100K products
- Performance: Page load < 2s, API responses < 200ms
- Reliability: 99.99% uptime, multi-region failover

2. Key Components:
- Services:
  * Product Service (catalog, search)
  * Order Service (cart, checkout)
  * Inventory Service (stock management)
  * User Service (auth, profiles)
- Data Stores:
  * PostgreSQL for orders and users
  * Elasticsearch for product search
  * Redis for cart and sessions
- External Systems:
  * Payment gateway (Stripe)
  * Shipping API (FedEx/UPS)
  * Email service (SendGrid)
- Infrastructure:
  * AWS multi-region deployment
  * CloudFront CDN
  * EKS for container orchestration

3. Design Constraints:
- Budget: $50K/month cloud costs
- Technology: Must use existing Java microservices
- Timeline: 6 months to MVP
- Team: 8 developers, 2 DevOps engineers

4. Expected Outcome:
- Architecture Diagram: 
  * Microservices topology
  * Data flow patterns
  * Scaling strategies
- Component Details:
  * Service boundaries
  * API contracts
  * Data models
- Data Flow:
  * User journey mapping
  * System interactions
  * Failure scenarios
```

## 📊 Scalability Analysis Template

```
Help me analyze scalability for this system:

1. Current State:
- Load: [Current usage]
- Performance: [Current metrics]
- Pain Points: [Known issues]
- Architecture: [Current design]

2. Growth Projections:
- Traffic: [Expected increase]
- Data: [Storage growth]
- Users: [User growth]
- Features: [New capabilities]

3. Scaling Strategy:
- Horizontal Scaling: [Service replication]
- Vertical Scaling: [Resource upgrade]
- Caching: [Cache strategy]
- Database: [Data scaling]

4. Implementation Plan:
- Priority: [What to scale first]
- Steps: [How to implement]
- Validation: [How to verify]
- Rollback: [Backup plan]
```

## 🔐 Security Design Template

```
Help me design security for this system:

1. Security Requirements:
- Data Sensitivity: [What to protect]
- Compliance: [Required standards]
- Access Control: [Who needs access]
- Threats: [What to defend against]

2. Security Measures:
- Authentication: [Identity verification]
- Authorization: [Access control]
- Encryption: [Data protection]
- Monitoring: [Security tracking]

3. Implementation:
- Security Layers: [Defense depth]
- Tools/Services: [Security stack]
- Best Practices: [Industry standards]
- Testing: [Security validation]
```

## 🔄 Migration Architecture Template

```
Help me design a migration strategy:

1. Current System:
- Architecture: [Existing design]
- Dependencies: [Current integrations]
- Pain Points: [Known issues]
- Constraints: [Limitations]

2. Target System:
- New Architecture: [Desired state]
- Improvements: [Key benefits]
- Requirements: [Must-haves]
- Technology: [New stack]

3. Migration Plan:
- Phases: [Migration steps]
- Timeline: [Schedule]
- Risks: [Potential issues]
- Rollback: [Backup plan]

4. Validation Strategy:
- Testing: [Verification steps]
- Metrics: [Success measures]
- Monitoring: [What to watch]
```

## 💡 Architecture Review Template

```
Please review this system architecture:

1. Architecture Overview:
- Components: [System parts]
- Interactions: [How parts connect]
- Data Flow: [Information movement]
- Technology: [Current stack]

2. Analysis Areas:
- Scalability: [Growth handling]
- Reliability: [Failure handling]
- Performance: [Speed/efficiency]
- Maintainability: [Code/system health]

3. Recommendations:
- Improvements: [What to enhance]
- Risks: [What to watch]
- Alternatives: [Other approaches]
- Priority: [What to do first]
```

## Tips for Better System Design Prompts

1. Always specify:
   - Scale requirements
   - Performance needs
   - Reliability requirements
   - Budget constraints

2. Include context about:
   - Existing systems
   - Team capabilities
   - Timeline constraints
   - Technology preferences

3. Ask for:
   - Trade-off analysis
   - Alternative approaches
   - Risk assessment
   - Implementation strategy