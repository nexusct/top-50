# Security Policy

## Overview

This repository contains a static HTML website that displays a directory of GitHub repositories. As a client-side only application with no backend services or user data collection, the attack surface is limited. However, we take security seriously and follow best practices to protect users.

## Reporting Security Issues

If you discover a security vulnerability in this project, please report it responsibly:

### How to Report

**DO NOT** open a public GitHub issue for security vulnerabilities.

Instead, please report security issues by:

1. **Email**: Contact the repository maintainer directly through their GitHub profile email (if available)
2. **GitHub Security Advisory**: Use the [GitHub Security Advisory](https://github.com/nexusct/top-50/security/advisories/new) feature (preferred)
3. **Private vulnerability report**: Submit through GitHub's private vulnerability reporting feature

### What to Include

When reporting a security issue, please provide:

- **Description**: A clear description of the vulnerability
- **Impact**: Potential impact and attack scenario
- **Reproduction Steps**: Detailed steps to reproduce the issue
- **Proof of Concept**: Code or screenshots demonstrating the vulnerability (if applicable)
- **Suggested Fix**: Any recommendations for resolving the issue (optional)
- **Your Contact Information**: So we can follow up with questions

### Response Timeline

- **Acknowledgment**: Within 48 hours of report receipt
- **Initial Assessment**: Within 5 business days
- **Fix Development**: Depends on severity (critical issues prioritized)
- **Public Disclosure**: After a fix is deployed and users have had time to update

## Security Best Practices

### For Developers

If you contribute to this project, please follow these security guidelines:

#### 1. No Hardcoded Secrets
- **Never commit** API keys, tokens, passwords, or other credentials to the repository
- Use environment variables for any sensitive configuration (if backend features are added)
- Add sensitive files to `.gitignore`
- Use placeholder values in example files (e.g., `.env.example`)

#### 2. Input Sanitization
- Always sanitize user input before rendering
- Use safe DOM APIs (e.g., `textContent` instead of `innerHTML` when inserting user data)
- Validate and escape data appropriately
- Be cautious with `eval()`, `innerHTML`, `outerHTML`, and `document.write()`

#### 3. Dependency Management
This project currently has no external dependencies, which reduces supply chain attack risks. If dependencies are added:
- Keep dependencies up to date
- Review dependency security advisories regularly
- Use tools like `npm audit` or `yarn audit`
- Pin dependency versions
- Minimize the number of dependencies

#### 4. Content Security Policy
If this site is deployed with HTTP headers control, consider implementing a Content Security Policy (CSP):
```http
Content-Security-Policy: default-src 'self'; script-src 'self' 'unsafe-inline'; style-src 'self' 'unsafe-inline'; img-src 'self' data: https:; font-src 'self'; connect-src 'self'; frame-ancestors 'none';
```

#### 5. HTTPS Only
- Always serve the site over HTTPS in production
- Enable HSTS (HTTP Strict Transport Security) if possible
- Redirect HTTP traffic to HTTPS

### For Users

When browsing this site:
- This site does not collect personal information
- Theme preferences are stored locally in your browser's LocalStorage
- No cookies are used
- External links to GitHub repositories open in new tabs with `rel="noreferrer"` for privacy
- The site does not track user behavior or analytics

## Known Security Considerations

### Current Implementation

1. **Static Content**: All repository data is hardcoded in the HTML file. There is no dynamic data fetching or user-generated content.

2. **No Backend**: This is a purely client-side application with no server-side processing, database, or authentication system.

3. **External Links**: All repository links point to external GitHub URLs. Users should exercise normal caution when visiting external sites.

4. **LocalStorage**: Theme preference is stored in browser LocalStorage. This data never leaves the user's browser.

5. **No Form Submission**: The site does not include forms that submit data anywhere.

6. **Clipboard API**: The "Copy Link" feature uses the browser's Clipboard API, which requires user interaction and is limited to the site's own content.

### Potential Risks Mitigated

✅ **XSS (Cross-Site Scripting)**: Mitigated by using static data and safe DOM manipulation  
✅ **CSRF (Cross-Site Request Forgery)**: Not applicable (no state-changing operations)  
✅ **SQL Injection**: Not applicable (no database)  
✅ **Command Injection**: Not applicable (no server-side execution)  
✅ **Path Traversal**: Not applicable (no file system access)  
✅ **Authentication Bypass**: Not applicable (no authentication)  
✅ **Session Hijacking**: Not applicable (no sessions)

## Security Checklist for Production Deployment

Before deploying this site to production:

- [ ] Serve over HTTPS with valid TLS certificate
- [ ] Enable HSTS headers if hosting platform supports it
- [ ] Implement Content Security Policy headers if possible
- [ ] Review all external links for legitimacy
- [ ] Ensure `.env` files (if any) are not committed to git
- [ ] Verify `.gitignore` is properly configured
- [ ] Remove any debug code or console.log statements
- [ ] Test in multiple browsers and devices
- [ ] Review code for any `innerHTML` usage with user input
- [ ] Confirm no sensitive data is hardcoded in source
- [ ] Set appropriate cache headers for static assets
- [ ] Configure proper CORS headers if API access is added

## Secure Configuration

### Git Best Practices

The repository should maintain a `.gitignore` file that excludes:
```gitignore
# Environment variables and secrets
.env
.env.local
.env.*.local
*.key
*.pem
*.p12

# Operating system files
.DS_Store
Thumbs.db
desktop.ini

# Editor directories and files
.vscode/
.idea/
*.swp
*.swo
*~

# Logs
*.log
logs/

# Temporary files
*.tmp
.cache/
```

### Environment-Based Configuration

If this project evolves to require environment-specific configuration:
- Use `.env.example` with placeholder values (safe to commit)
- Use `.env` or `.env.local` for actual secrets (never commit)
- Document required environment variables in README
- Rotate any accidentally committed secrets immediately

## Security Updates

This section will be updated when security patches are released:

- **v1.0.0** (August 2026): Initial release with security baseline

## Additional Resources

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/)
- [GitHub Security Best Practices](https://docs.github.com/en/code-security)
- [Content Security Policy Reference](https://content-security-policy.com/)
- [MDN Web Security](https://developer.mozilla.org/en-US/docs/Web/Security)

## Acknowledgments

We appreciate the security research community's efforts in responsibly disclosing vulnerabilities and helping keep open source projects secure.

---

**Last Updated**: August 19, 2026  
**Security Contact**: Use GitHub Security Advisories or private vulnerability reporting
