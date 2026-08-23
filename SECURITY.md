# Security Policy

## Overview

This repository contains a static HTML website displaying a directory of GitHub repositories. While it's a client-side-only application with no backend or user data collection, we implement security best practices to protect users.

## Reporting Security Issues

If you discover a security vulnerability, please report it responsibly:

### How to Report

**DO NOT** open a public GitHub issue for security vulnerabilities.

Instead, report security issues by:

1. **GitHub Security Advisory** (preferred): [Create a private security advisory](https://github.com/nexusct/top-50/security/advisories/new)
2. **Email**: Contact the repository maintainer via their GitHub profile
3. **Private vulnerability report**: Use GitHub's private vulnerability reporting

### What to Include

- **Description**: Clear description of the vulnerability
- **Impact**: Potential impact and attack scenario
- **Reproduction Steps**: Detailed steps to reproduce
- **Proof of Concept**: Code or screenshots (if applicable)
- **Suggested Fix**: Recommendations for resolution (optional)
- **Contact Information**: For follow-up questions

### Response Timeline

- **Acknowledgment**: Within 48 hours
- **Initial Assessment**: Within 5 business days
- **Fix Development**: Prioritized by severity
- **Public Disclosure**: After fix deployment and update window

## Security Best Practices

### For Developers

#### 1. No Hardcoded Secrets
- **Never commit** API keys, tokens, passwords, or credentials
- Use environment variables for sensitive configuration
- Add sensitive files to `.gitignore`
- Use placeholder values in example files

#### 2. Input Sanitization
- Always sanitize user input before rendering
- Use safe DOM APIs (`textContent` over `innerHTML` for user data)
- Validate and escape data appropriately
- Avoid `eval()`, `innerHTML` with unescaped data, `outerHTML`, and `document.write()`

#### 3. Dependency Management
This project currently has no external dependencies. If dependencies are added:
- Keep dependencies up to date
- Review security advisories regularly
- Use `npm audit` or `yarn audit`
- Pin dependency versions
- Minimize the number of dependencies

#### 4. Content Security Policy
Recommended CSP headers for production deployment:
```http
Content-Security-Policy: default-src 'self'; script-src 'self' 'unsafe-inline'; style-src 'self' 'unsafe-inline'; img-src 'self' data: https:; font-src 'self'; connect-src 'self'; frame-ancestors 'none'; base-uri 'self'; form-action 'self';
```

#### 5. HTTPS Only
- Always serve over HTTPS in production
- Enable HSTS (HTTP Strict Transport Security)
- Redirect HTTP traffic to HTTPS

### For Users

When browsing this site:
- No personal information is collected
- Theme preferences stored locally in browser LocalStorage
- No cookies are used
- External links open with `rel="noreferrer"` for privacy
- No analytics or tracking

## Known Security Considerations

### Current Implementation

1. **Static Content**: All repository data is hardcoded in HTML. No dynamic data fetching or user-generated content.

2. **No Backend**: Purely client-side application with no server-side processing, database, or authentication.

3. **External Links**: All repository links point to external GitHub URLs.

4. **LocalStorage**: Theme preference stored in browser LocalStorage only.

5. **No Form Submission**: No forms that submit data.

6. **Clipboard API**: Copy link feature uses browser Clipboard API with user interaction only.

### Threats Mitigated

✅ **XSS (Cross-Site Scripting)**: Mitigated by HTML escaping and safe DOM manipulation  
✅ **CSRF (Cross-Site Request Forgery)**: Not applicable (no state-changing operations)  
✅ **SQL Injection**: Not applicable (no database)  
✅ **Command Injection**: Not applicable (no server-side execution)  
✅ **Path Traversal**: Not applicable (no file system access)  
✅ **Authentication Bypass**: Not applicable (no authentication)  
✅ **Session Hijacking**: Not applicable (no sessions)

## Production Deployment Checklist

Before deploying to production:

- [ ] Serve over HTTPS with valid TLS certificate
- [ ] Enable HSTS headers if supported
- [ ] Implement Content Security Policy headers
- [ ] Review all external links for legitimacy
- [ ] Verify no `.env` files committed
- [ ] Verify `.gitignore` is properly configured
- [ ] Remove debug code and `console.log` statements
- [ ] Test in multiple browsers and devices
- [ ] Verify no `innerHTML` usage with unescaped user input
- [ ] Confirm no sensitive data hardcoded in source
- [ ] Set appropriate cache headers for static assets
- [ ] Configure CORS headers if API access is added

## Secure Configuration

### Git Best Practices

The `.gitignore` file excludes:
- Environment variables and secrets
- Operating system files
- Editor configurations
- Logs and temporary files
- Credentials and API keys

### Environment-Based Configuration

If environment-specific configuration is needed:
- Use `.env.example` with placeholder values (safe to commit)
- Use `.env` for actual secrets (never commit)
- Document required environment variables
- Rotate accidentally committed secrets immediately

## Security Updates

- **2026-08-23**: Comprehensive security hardening - XSS fixes, HTML escaping, bounds checking
- **2026-08-19**: Initial security baseline

## Additional Resources

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/)
- [GitHub Security Best Practices](https://docs.github.com/en/code-security)
- [Content Security Policy Reference](https://content-security-policy.com/)
- [MDN Web Security](https://developer.mozilla.org/en-US/docs/Web/Security)

## Acknowledgments

We appreciate the security research community's efforts in responsibly disclosing vulnerabilities and keeping open source secure.

---

**Last Updated**: August 23, 2026  
**Security Contact**: Use GitHub Security Advisories or private vulnerability reporting
