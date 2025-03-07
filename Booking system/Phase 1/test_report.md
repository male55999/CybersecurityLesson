# Test Report - Booking System Phase 1
**Date:** 07-03-2025  
**Tester:** Maria Alejandra Cabrera Arauz

## Differences Between Versions

### **Findings in the First Version (2025-02-17)**
- **Medium-Risk Issues (2):**
  - **Missing Content Security Policy (CSP) Header**: The application lacked a CSP configuration, which exposed it to Cross-Site Scripting (XSS) and data injection attacks.
  - **Missing Anti-Clickjacking Header**: No X-Frame-Options or CSP `frame-ancestors` directive, making it vulnerable to Clickjacking attacks.
- **Low-Risk Issues (2):**
  - **Application Error Disclosure**: Some error messages exposed internal application details.
  - **Missing X-Content-Type-Options Header**: Increased risk of MIME-type sniffing attacks.

### **Findings in the Second Version (2025-03-03)**
- **Medium-Risk Issues (1):**
  - **Wildcard Directive in CSP**: The CSP policy is now present, but it allows wildcard sources (`*`), which can still lead to security risks.
- **Informational Issues (3):**
  - **Sensitive Information Disclosure in URL**: Some API requests include sensitive data in query parameters.
  - **User-Controlled HTML Attributes (Potential XSS)**: Some HTML elements accept user input without proper validation.
  - **Authentication Request Identified**: Indicating potential exposure of authentication mechanisms.

### **Key Improvements in the Second Version**
- CSP is now implemented but still requires further restrictions.  
- No Clickjacking vulnerabilities detected.  
- Reduced error disclosure issues.  

### **Remaining Security Concerns**
- The CSP wildcard directive should be removed or restricted to specific trusted sources.
- User input sanitization is needed to prevent potential XSS attacks.
- Sensitive information should not be passed through URLs.  

---
