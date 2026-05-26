📜 Project Development Standards & Guidelines

🤖 AI Assistant Guidelines
Prompt Processing
Optimize input prompts appropriately before processing to ensure accurate understanding.
Clearly point out any objections or ambiguities in the prompt; do not generate blindly.
Maintain transparent communication and proactively ask for clarification when uncertain.
Development Principles
No TODO comments allowed. If a task cannot be completed at once, clearly state the reasons and the follow-up plan.
All business implementations must include clear comments and logging.
Prioritize code quality and maintainability over speed of completion.

🔐 Security Standards
Handling Sensitive Information
Strictly prohibit hardcoding keys, passwords, Tokens, or other sensitive information in the code.
All sensitive configurations must be read from configuration files or environment variables.
Do not print complete user passwords, credit card numbers, etc., in logs.
Desensitize (mask) sensitive data before outputting.
Data Security
SQL queries must use parameterized queries; string concatenation is strictly prohibited.
All user inputs must be strictly validated and must not be directly passed into database queries.
Prevent common security vulnerabilities such as SQL Injection and XSS.

🏗️ Architecture Standards
Interface Design
All interfaces must uniformly return the Result<T> wrapper class; hardcoding return types is prohibited.
Maintain consistency in API response formats to facilitate unified frontend handling.
Use reasonable HTTP status codes.
Code Organization
The Controller layer is responsible only for receiving requests and returning responses.
Parameter validation logic should be placed in the Service implementation classes; avoid writing if judgments in the Controller.
Follow the Single Responsibility Principle with clear responsibilities for each layer.

💻 Coding Standards
Naming Conventions
Method names should start with a verb: getUserById, createOrder, deleteById.
Class names use PascalCase; method and variable names use camelCase.
Constants use UPPER_SNAKE_CASE.
Package names use lowercase letters, with multiple words separated by dots.
Commenting Standards
All public methods must include complete Javadoc comments.
Comments should explain the method's purpose, parameter meanings, return values, and possible exceptions thrown.
Avoid meaningless comments (e.g., // get user, // return result).
Complex business logic requires detailed implementation explanations.
Coding Practices
Use batch operation methods like saveAll / deleteAllById; looping single operations is prohibited.
Use design patterns reasonably to improve code reusability.
Exception handling must be explicit; empty catch blocks are forbidden.
Release resources promptly after use, using try-with-resources or finally blocks.

📊 Logging Standards
Log Levels
ERROR: System errors and exceptions requiring immediate attention.
WARN: Potential issues that may affect system operation.
INFO: Key business process nodes and critical state changes.
DEBUG: Debugging information and detailed execution processes.
Log Content
Record key parameters and execution results for business operations.
Exception information must include the full stack trace.
Use structured logging to facilitate subsequent analysis.
Keep log output moderate to avoid impacting performance.

⚡ Performance Standards
Database Operations
Use indexes reasonably and avoid full table scans.
Replace looping single operations with batch operations.
Use paginated queries for large volumes of data.
Avoid the N+1 query problem.
Memory Management
Release unneeded object references promptly.
Pay attention to memory usage when handling large objects.
Use caching mechanisms reasonably.

🧪 Testing Standards
Unit Testing
Core business logic must have unit tests.
Test cases should cover normal flows and exception scenarios.
Use Mock technologies to isolate external dependencies.
Integration Testing
Conduct integration testing at the interface level.
Perform integration testing for database operations.
Ensure the independence of the test environment.

📋 Code Review Checklist
Mandatory Checks
Whether all the above standards are followed.
Whether there are any security risks.
Whether there is appropriate exception handling.
Whether logging is complete and reasonable.
Whether there are obvious performance issues.

Suggestions
Can the code be further simplified?
Is there a better implementation approach?
Is the documentation updated synchronously?
