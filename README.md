<img width="1392" alt="Screenshot 2025-03-20 at 16 11 15" src="https://github.com/user-attachments/assets/f5ff62c9-5364-4b86-925b-cd2d5a836284" />

# AI Coding Agent Prompt: Security Audit

Perform a **comprehensive security audit** of the codebase to ensure it meets **17 critical security checks** before production deployment.

For each check:
- **Analyze** the code to identify potential security risks.
- **List** issues clearly and provide **code snippets** where necessary.
- **Suggest and apply** fixes using best practices.
- **Explain** why the fix is necessary.

## Security Checks to Perform

### 1. Sanitize all user inputs
Ensure all user input is properly sanitized before being processed. Use appropriate libraries or built-in functions to prevent security risks like **XSS** and **SQL injection**.

### 2. Secure environment variables
Verify that sensitive environment variables (e.g., API keys, database credentials, authentication secrets) are **not committed to version control**. Check `.gitignore` or equivalent mechanisms and ensure variables are securely configured in the deployment environment.

### 3. Update environment variables for production
Confirm that all necessary environment variables are correctly set for the **production environment**.

### 4. Implement an API abstraction layer
Ensure that client-side code does not directly call database endpoints. API calls should be routed through **secure backend functions** that handle data access.

### 5. Enforce API rate limiting
Implement rate limiting to prevent spam and abuse. Use tools like **Redis** or in-memory strategies to **limit requests per user/IP** based on endpoint sensitivity.

### 6. Use secure authentication and session management
Ensure authentication is handled using a **secure, industry-standard method** (e.g., OAuth, JWT, session-based auth). If using a framework, confirm that **sessions, tokens, and authentication flows** follow best security practices.

### 7. Configure authentication callback URLs properly
Verify that authentication callback URLs are correctly configured for the **production domain** to prevent unintended redirects or authentication failures.

### 8. Disable debug mode in production
Ensure that **debugging tools, verbose logging, and stack traces** are disabled in production to avoid exposing sensitive application details.

### 9. Use a production-ready database
Ensure that the application uses a **scalable, concurrent-safe database** (e.g., PostgreSQL, MySQL, MongoDB). Avoid lightweight databases (e.g., SQLite) in production unless specifically required.

### 10. Fix all linter and static analysis errors
Run the **linter and static code analysis tools** to detect and fix vulnerabilities or code quality issues. List errors by type before fixing them incrementally.

### 11. Implement structured logging
Remove raw `console.log` statements and use a **structured logging tool** (e.g., Winston, Pino, Log4j). Ensure logs are securely stored and do not contain sensitive data.

### 12. Prevent sensitive information exposure in error messages
Ensure that detailed error messages are **only logged on the backend**, while users receive **generic error messages** to prevent information leaks.

### 13. Establish an incident response plan
Verify that there is a **clear plan** for handling **security breaches, service disruptions, or data leaks**.

### 14. Configure a Content Security Policy (CSP)
If the application runs in a browser environment, ensure that **CSP rules** are enforced to prevent XSS attacks and unauthorized resource loading.

### 15. Keep dependencies up to date
Run **security audits on dependencies** (e.g., `npm audit`, `pip-audit`, `cargo audit`). Regularly update packages, remove unused dependencies, and set up **automated security alerts** (e.g., GitHub Dependabot).

### 16. Validate user input on the server side
Beyond sanitization, ensure that all user input is **properly validated** using libraries like **Zod, Joi, Yup, or built-in validation methods**. Handle validation errors gracefully.

### 17. Implement secure database practices
Ensure that the database follows best practices:
- Regular **backups** with restore verification
- **Connection pooling** for performance
- **Monitoring for suspicious activity**
- **Prepared statements** to prevent SQL injection

Run each check sequentially and apply necessary fixes while maintaining code integrity. Document any issues found and resolved.
