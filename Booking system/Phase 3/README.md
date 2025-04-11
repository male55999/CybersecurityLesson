| **Page / Feature**                    | **Guest** | **Reserver** | **Administrator** |
|:-------------------------------------|:---------:|:------------:|:-----------------:|
| `/ Home Page`                      | ✅        | ✅           | ✅                |
| └─ View basic content                | ✅        | ✅           | ✅                |
| `/login`                             | ✅        | ✅           | ✅                |
| `/resources`                         | ❌        | ✅           | ✅                |
| └─ View resource list                | ❌        | ✅           | ✅                |
| `/resources/create`                 | ❌        | ❌           | ✅                |
| └─ Create new resource form          | ❌        | ❌           | ✅                |
| `/reservations`                      | ❌        | ✅           | ✅                |
| └─ View own reservations             | ❌        | ✅           | ✅                |
| `/reservations/create`              | ❌        | ✅           | ✅                |
| └─ Make new reservation              | ❌        | ✅           | ✅                |
| `/users`                             | ❌        | ❌           | ✅                |
| └─ View user list                    | ❌        | ❌           | ✅                |
| `/users/create`                      | ❌        | ❌           | ✅                |
| └─ Register new user                 | ❌        | ❌           | ✅                |
| `/logout`                            | ❌        | ✅           | ✅                |

**Symbols used:**  
✅ Pass (allowed)  
❌ Fail (not allowed)  
⚠️ Attention (needs review)


**Symbols used:**  
✅ Pass (a note can be added)  
❌ Fail (a note can be added)  
⚠️ Attention (a note can be added)

**Notes:**  
1. Without logging in.
2. Unable to log in as Guest.
3. **Security alerts found in ZAP**:
   - **Medium**: Absence of Anti-CSRF tokens, missing Content Security Policy (CSP) header, missing Anti-Clickjacking header.
   - **Low**: Disclosure of Unix timestamps, server version information, missing security headers like X-Content-Type-Options, missing Strict-Transport-Security (HSTS).
   - **Impact**: These alerts affect both **Reserver** and **Administrator** roles, but are more critical for the **Administrator**, who has higher permissions.
