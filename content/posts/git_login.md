---

title: "GitHub CLI One-Time Login on Linux"
date: 2026-03-11
tags: ["GitHub", "CLI", "Linux", "Authentication"]
draft: false
------------

## Overview

This guide demonstrates how to log into GitHub using the **GitHub CLI (`gh`)** on Linux. It covers all terminal prompts to ensure a one-time secure authentication.

---

## Step-by-Step GitHub CLI Login

1. Open your terminal and start the login process:

```bash
gh auth login
```

2. **Prompt 1:** Where do you use GitHub?

```
? Where do you use GitHub?  [Use arrows to move, type to filter]
> GitHub.com
  Other
```

Select **GitHub.com** and press Enter.

3. **Prompt 2:** Preferred protocol for Git operations:

```
? What is your preferred protocol for Git operations on this host?  [Use arrows to move, type to filter]
> HTTPS
  SSH
```

Choose **HTTPS** and press Enter.

4. **Prompt 3:** How to authenticate GitHub CLI:

```
? How would you like to authenticate GitHub CLI?  [Use arrows to move, type to filter]
> Login with a web browser
  Paste an authentication token
```

Select **Login with a web browser** and press Enter.

5. **One-Time Code:**

```
! First copy your one-time code: 6876-5378
Press Enter to open https://github.com/login/device in your browser...
```

Copy the one-time code and open the provided URL in your browser.

6. **Browser Login:**

* Paste the one-time code into the GitHub login page.
* Sign in with your GitHub account.
* Authorize CLI access.

7. **Return to Terminal:**

Once authorization is complete, the terminal will confirm successful login.

```bash
Logged in as YOUR_USERNAME
```

---

## Verification

Check authentication status:

```bash
gh auth status
```

It should display your GitHub account and authentication method.

---

**Tip:** This is a **one-time login**. Future Git operations using `gh` will not require re-authentication unless credentials are revoked.
