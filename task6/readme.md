Tested 5 passwords on passwordmeter.com to understand what makes a password secure.
Results at a glance:

cybersecurity — Fair (good length, no complexity)
name@123 — Very Weak (short + pattern 123)
Harry potter — Strong (length + space as special char)
Hr@1997 — Very Weak (4 types but only 7 chars + guessable year)
:Harry potter@97 — Very Strong (~105 bits entropy, >1 trillion years to crack)

Core lesson: Length dominates over character variety. A short password with all 4 character types still loses to a longer password with fewer types.
Best practices: Use 12–16+ characters, passphrases over complex short passwords, avoid personal info and keyboard patterns, never reuse passwords, enable MFA.
Attacks covered: Brute force (tries all combinations), dictionary (uses wordlists/leaked passwords), rainbow tables (precomputed hashes — defeated by bcrypt + salting), and credential stuffing (reused passwords from breaches).
Takeaway: A passphrase like :Harry potter@97 is both memorable and cryptographically strong — the ideal balance of usability and security.
