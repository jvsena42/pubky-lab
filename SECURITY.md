# 🔒 Security Guidelines for PubkyLab

## Overview

PubkyLab is designed with security and privacy in mind. This document outlines security considerations and best practices.

## 🔑 Credentials Management

### ⚠️ Never Hardcode Secrets

**DO NOT** include sensitive credentials in the code or documentation:
- ❌ Homeserver public keys
- ❌ Invitation codes
- ❌ API keys
- ❌ Private keys
- ❌ Access tokens

### ✅ Proper Credential Handling

**DO** handle credentials properly:
- ✅ Accept credentials via user input only
- ✅ Use environment variables for server-side code
- ✅ Store in secure configuration management systems
- ✅ Document where users can obtain credentials
- ✅ Never commit credentials to version control

## 🔐 Key Security Features

### Client-Side Key Generation
- Keypairs are generated in the browser using WebCrypto
- Private keys never leave the user's device
- Keys are ephemeral by default (not stored)

### Session Management
- Sessions use HTTP-only cookies when possible
- Session tokens are managed by the SDK
- Automatic session expiration

### Data Privacy
- All data operations are over HTTPS
- End-to-end encryption for sensitive operations
- User data stored on user's chosen homeserver

## 🛡️ Security Best Practices

### For Users

1. **Verify Homeserver**
   - Only use homeservers you trust
   - Verify the homeserver public key through official channels
   - Be cautious with unknown homeservers

2. **Protect Your Keys**
   - Never share your private keys
   - Use recovery files with strong passphrases
   - Store recovery files securely

3. **Use HTTPS**
   - Always access PubkyLab over HTTPS in production
   - Avoid using on untrusted networks without VPN

4. **Clear Browser Data**
   - Clear browser data after using on shared computers
   - Use private/incognito mode when appropriate

### For Developers

1. **Deployment Security**
   ```bash
   # Use HTTPS for all deployments
   # GitHub Pages: Automatic HTTPS
   # Vercel: Automatic HTTPS
   ```

2. **Environment Variables**
   - Never commit `.env` files
   - Use `.gitignore` for sensitive files
   - Use platform-specific secret management

3. **Code Review**
   - Review code for hardcoded secrets
   - Use tools like `git-secrets` or `truffleHog`
   - Enable branch protection rules

4. **Dependencies**
   - Only use trusted CDNs (jsdelivr, unpkg)
   - Verify SDK integrity
   - Monitor for security updates

## 🔍 Security Checklist

Before deploying or sharing:

- [ ] No hardcoded credentials in code
- [ ] No secrets in documentation
- [ ] HTTPS enabled for production
- [ ] `.gitignore` includes sensitive files
- [ ] Dependencies are from trusted sources
- [ ] Code reviewed for security issues
- [ ] Users instructed on secure usage

## 🚨 Security Considerations

### Data Storage
- **Public Data**: Anything in `/pub/` is publicly readable
- **Path Convention**: Use domain-like paths to avoid conflicts
- **No Encryption**: SDK does not encrypt data by default

### Browser Storage
- **No localStorage**: Credentials not stored in browser by default
- **Session Cookies**: Used for authentication
- **Clear on Signout**: Data cleared when signing out

### Network Security
- **TLS Required**: All production deployments must use HTTPS
- **CORS**: Properly configured for API access
- **CSP**: Consider Content Security Policy headers

## 🔐 Obtaining Credentials Securely

### Homeserver Public Key
1. Contact your homeserver administrator
2. Verify through official documentation
3. Cross-reference with multiple sources
4. Use official homeserver discovery methods

### Invitation Codes
1. Request from homeserver admin
2. Use one-time codes when possible
3. Never reuse or share invitation codes
4. Treat as sensitive credentials

## 📝 Reporting Security Issues

If you discover a security vulnerability:

1. **DO NOT** create a public GitHub issue
2. Email security concerns to the project maintainers
3. Include:
   - Description of the vulnerability
   - Steps to reproduce
   - Potential impact
   - Suggested fix (if any)

## 🔄 Security Updates

### Staying Secure

1. **Monitor SDK Updates**
   - Watch for security patches
   - Update SDK version in importmap
   - Test after updates

2. **Review Dependencies**
   - Check for known vulnerabilities
   - Update CDN versions when needed
   - Use Subresource Integrity (SRI) when possible

3. **Follow Best Practices**
   - Keep documentation current
   - Review security guidelines regularly
   - Educate users on security

## 🎓 Security Education

### For End Users

**Safe Usage**:
- Use trusted homeservers
- Verify URLs before entering credentials
- Don't trust unfamiliar deployments
- Understand data privacy implications

**Data Classification**:
- Public data: Anyone can read
- Private data: Requires authentication
- Sensitive data: Consider additional encryption

### For Developers

**Secure Development**:
```javascript
// ✅ Good: User provides credentials
const homeserver = prompt("Enter homeserver public key:");

// ❌ Bad: Hardcoded credentials
const homeserver = "hardcoded-key-here";
```

**Input Validation**:
```javascript
// Always validate user input
if (!isValidPublicKey(homeserverKey)) {
    throw new Error("Invalid homeserver key format");
}
```

## 🛠️ Security Tools

### Recommended Tools

1. **git-secrets** - Prevent committing secrets
   ```bash
   brew install git-secrets
   git secrets --install
   git secrets --register-aws
   ```

2. **truffleHog** - Find secrets in git history
   ```bash
   pip install truffleHog
   truffleHog --regex --entropy=False .
   ```

3. **npm audit** - Check dependencies
   ```bash
   npm audit
   ```

## 📋 Security Audit Log

| Date | Issue | Resolution | Status |
|------|-------|------------|--------|
| 2025-10-22 | Hardcoded staging credentials | Removed from all files | ✅ Fixed |

## ⚖️ Compliance

### Privacy Considerations

- **GDPR**: Users control their data
- **Data Location**: User chooses homeserver
- **Right to Delete**: Users can delete their data
- **Transparency**: Code is open source

### Terms of Use

Users should:
- Comply with homeserver terms of service
- Respect intellectual property
- Follow applicable laws and regulations
- Use responsibly

## 🔗 Additional Resources

- [Pubky Security Documentation](https://github.com/pubky/pubky-core)
- [WebCrypto Security](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Security Best Practices](https://cheatsheetseries.owasp.org/)

---

**Remember**: Security is a shared responsibility. Stay vigilant, keep credentials secure, and report issues responsibly.

For security concerns: [Open a private security advisory](https://github.com/pubky/pubky-core/security/advisories/new)
