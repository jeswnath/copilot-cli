# Product Spec: Secure Login Flow (Demo Input)

## Context
This is a sample product specification used in Session 2 to demonstrate MCP filesystem ingestion.
The target product is a web application used by employees to access internal tools.

## Business Goal
Provide a secure and reliable login flow that minimizes unauthorized access while keeping sign-in fast for valid users.

## Scope
In scope:
- Username/password login
- "Remember me" option
- Account lockout after repeated failures
- Password reset via email OTP
- Session timeout and re-authentication

Out of scope:
- Social login (Google, Microsoft)
- Biometric login
- SSO integration with enterprise identity providers

## Users
- Employee user (primary)
- IT support staff (secondary for account recovery)

## Functional Notes
1. Users must log in with email and password.
2. Email format should be validated client-side and server-side.
3. After 5 failed login attempts within 15 minutes, the account must be temporarily locked for 30 minutes.
4. Locked users should see a clear lockout message with remaining lockout time.
5. "Forgot password" should send a one-time passcode (OTP) to the registered email.
6. OTP should expire in 10 minutes.
7. Successful login should redirect users to the dashboard.
8. If "Remember me" is selected, session should persist for 7 days unless user logs out.
9. If "Remember me" is not selected, session should expire after 30 minutes of inactivity.
10. All login attempts must be recorded in an audit log.

## Non-Functional Expectations
- Security: enforce TLS; passwords stored with strong hashing and salt.
- Performance: login API should respond within 2 seconds for 95% of requests.
- Reliability: login service availability target is 99.9%.
- Usability: error messages should be clear, non-technical, and actionable.

## Constraints
- Must comply with internal security policy SEC-21.
- Must be implemented without introducing a new identity provider.

## Suggested Prompt for Demo
Use this with the Requirements Writer agent:

"Read the file demo-login-spec.md and generate structured functional requirements for the login flow. Follow the SDLC requirements standard and include NFR tags."
