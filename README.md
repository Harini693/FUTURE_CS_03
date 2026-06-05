FUTURE_CS_03 - API Security Risk Analysis Report
Overview
This project was completed as part of the Future Interns Cyber Security Internship. The objective was to analyze a public API for security risks and identify vulnerabilities that could impact confidentiality, integrity, and availability.
Target API
https://jsonplaceholder.typicode.com
Tools Used
Postman Web
Browser DevTools
WPS Office
Methodology
Sent GET requests to API endpoints using Postman
Analyzed request and response headers
Checked authentication and authorization mechanisms
Reviewed API responses for exposed sensitive information
Examined rate limiting and caching behavior
Identified security weaknesses and classified risk levels
Recommended remediation measures
API Information
Field
Details
API Name
JSONPlaceholder
Base URL
https://jsonplaceholder.typicode.com
Endpoint Tested
/users
Request Method
GET
Response Code
200 OK
Hosted On
Cloudflare
Total Findings
8
Security Findings
High Risk Findings
1. No Authentication Required
Risk Level: High
Description:
The API allows access to user information without requiring authentication or an API key.
Recommendation:
Implement API key authentication or OAuth 2.0 for protected endpoints.
2. Personal Data Exposed
Risk Level: High
Description:
User details such as names, usernames, email addresses, and addresses are publicly accessible.
Recommendation:
Restrict sensitive data exposure and return only necessary information.
3. No Authorization Header Validation
Risk Level: High
Description:
Requests are processed without verifying authorization tokens or credentials.
Recommendation:
Require valid Bearer Tokens for all protected resources.
4. Insecure CORS Configuration
Risk Level: High
Description:
Cross-Origin Resource Sharing policies are not properly restricted.
Recommendation:
Allow requests only from trusted domains.
5. Accept Any Content Type
Risk Level: High
Description:
The API does not strictly enforce acceptable content types.
Recommendation:
Restrict requests to application/json where applicable.
Medium Risk Findings
6. Weak Rate Limiting
Risk Level: Medium
Description:
The API permits a large number of requests, increasing the risk of abuse and automated data harvesting.
Recommendation:
Implement stricter rate-limiting policies.
7. Rate Limit Reset Time Exposed
Risk Level: Medium
Description:
Rate limit reset information is exposed through response headers.
Recommendation:
Avoid exposing unnecessary rate-limiting details.
8. Sensitive Data Cached
Risk Level: Medium
Description:
Responses containing user information may be cached by intermediary services.
Recommendation:
Use Cache-Control: no-store for sensitive responses.
Risk Summary
Risk Level
Count
High
5
Medium
3
Low
0
Total
8
Recommendations
Implement authentication and authorization controls.
Follow OWASP API Security Top 10 guidelines.
Restrict CORS policies to trusted domains.
Apply strict rate-limiting mechanisms.
Validate all user inputs.
Prevent caching of sensitive information.
Enforce HTTPS communication.
Follow the principle of least privilege.
Conclusion
The API Security Risk Analysis identified a total of 8 security findings, including 5 High Risk and 3 Medium Risk vulnerabilities. The most significant issues involve missing authentication, exposed user information, and insecure API configurations. Implementing proper authentication, authorization, rate limiting, and secure response handling can significantly improve the overall security posture of the API.
