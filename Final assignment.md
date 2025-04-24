# Cisco - Introduction to Cybersecurity
![Cisco Certificate Screenshot](https://github.com/male55999/CybersecurityLesson/blob/d0e6d10631924bfdfb7281e6714260d80e8a0f50/Cisco%20screenshot%20.png)
### Reflection
During this topic, I explored the fundamentals of cybersecurity and its increasing relevance in today’s hyper-connected world. I learned about the core principles of security confidentiality, integrity, and how they apply in real scenarios. The course also covered various types of cyber threats, like phishing, malware, and social engineering. What I found particularly useful were the real world examples and case studies that highlighted how businesses and individuals are affected by cyberattacks. This topic gave me a strong foundation and context for understanding the broader goals of security in IT systems.

# PortSwigger
![PortSwigger Dashboard Screenshot](https://github.com/male55999/CybersecurityLesson/blob/a2ed89f45e4a7204a4d77af45b4b26fa65894df5/PortSwigger%20screenshot.png)

### Labs
Topic SQL injection
- SQL injection vulnerability in WHERE clause allowing retrieval of hidden data
- SQL injection vulnerability allowing login bypass

Topic Authentication
- Username enumeration via different responses
- Password reset broken logic

Topic Access control
- Unprotected admin functionality
- User role can be modified in user profile

### Reflection
Throughout this topic, I learned how web applications can be exploited through weaknesses in input validation, authentication processes, and access control mechanisms. Each lab taught me how small misconfigurations or overlooked features can become serious vulnerabilities. I especially realized the importance of server-side validation and how user input, if not properly handled, can compromise entire systems. Practicing these attacks helped me understand how attackers think, which is essential to build safer applications.

# The Booking system project
### Phase 1
In the first phase, I tested the initial version of the booking system using Docker and OWASP ZAP. I successfully deployed the application using Docker and was able to run ZAP scans to identify several basic vulnerabilities, such as missing security headers and lack of input validation. What worked well in this phase was the Docker setup and the integration of ZAP for vulnerability scanning. However, I encountered issues when interpreting some of the ZAP findings and had to adjust the scanning scope. The most time-consuming part was analyzing the ZAP results and learning to distinguish between real vulnerabilities and false positives. From this phase, I learned how to set up a penetration test environment, perform automated scans, and document findings clearly using markdown.
### Phase 2
In the second phase, I worked with an updated version of the application. I used Docker Compose to run the containers and repeated the penetration testing process. This time, I focused on verifying if the vulnerabilities identified in Phase 1 had been fixed. I also extracted password hashes from the PostgreSQL database and cracked them using Hashcat. What worked well was setting up the Docker containers again and comparing ZAP reports effectively. What didn’t work at first was configuring Hashcat properly on Windows; I had to troubleshoot issues with file paths and hash formats. The most time-consuming part was building and tuning the correct Hashcat commands, especially when creating custom masks. I learned how to conduct more advanced password cracking attacks and how to validate security improvements across versions of the same application.
### Phase 3
In the final phase, I focused on performing dictionary and non-dictionary attacks using Burp Suite and Hydra. I captured login requests with Burp, configured payloads, and tested various combinations using both wordlists and brute-force patterns. What worked very well was the Burp Suite Intruder tool for launching dictionary attacks and analyzing responses. However, I ran into difficulties with Hydra syntax and had to adjust several parameters for successful execution. The most time-intensive task was configuring Hydra for non-dictionary attacks with custom masks that aligned with the structure of the remaining unknown passwords. From this phase, I learned how to simulate real-world login attacks, evaluate system response behaviors, and appreciate the importance of rate-limiting and secure password policies.
### Phase 4  
In this final phase, I evaluated the booking system from a legal and privacy perspective, focusing on GDPR compliance. I completed a detailed checklist that assessed data minimization, user data management, booking visibility, access control, privacy by design, and data security. I found several strengths, such as proper role-based access control and the fact that bookings do not expose personal data publicly. However, critical issues remain, like the lack of a consent mechanism during registration, the inability for users to view or delete their data, and missing protections like anonymization and CSRF tokens. To address these gaps, I created and documented a Cookie Policy, a Privacy Policy, and Terms of Service in markdown format. This phase helped me understand the legal responsibilities of web systems and how to translate compliance requirements into actionable documentation and design improvements.
### Final Reflection
Overall, the Booking System Project allowed me to apply theory in a real-world simulation. Across all three phases, I worked with tools like Docker, OWASP ZAP, Burp Suite, Hydra, and Hashcat. The project helped me understand the full lifecycle of a penetration test—from environment setup and vulnerability discovery to exploitation and reporting. Each phase presented new challenges that pushed me to troubleshoot, learn, and improve my technical skills.

# Logbook
### Git Repository
[https://github.com/male55999/CybersecurityLesson](https://github.com/male55999/CybersecurityLesson)

### Total Hours Spent
**81 hours**

### Hours per Topic
- Cisco Introduction to Cybersecurity: **17 hours**  
- PortSwigger Labs: **16 hours**  
- Booking System Project (Phases 1–4): **41 hours**  
- Documentation and lectures: **7 hours**
