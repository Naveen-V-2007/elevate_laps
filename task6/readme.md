# Password Strength Analysis

## Objective

To understand what makes a password secure by creating and testing multiple passwords using an online password strength checker.

## Tool Used

* PasswordMeter.com

## Tested Passwords and Results

| Password           | Strength Rating | Observation                                                               |
| ------------------ | --------------- | ------------------------------------------------------------------------- |
| `cybersecurity`    | Fair            | Good length but lacks complexity.                                         |
| `name@123`         | Very Weak       | Short and contains a common pattern (`123`).                              |
| `Harry potter`     | Strong          | Benefits from length and the inclusion of a space character.              |
| `Hr@1997`          | Very Weak       | Contains multiple character types but is short and uses a guessable year. |
| `:Harry potter@97` | Very Strong     | High entropy and extremely resistant to cracking attempts.                |

## Key Findings

* Password length has a greater impact on strength than character variety alone.
* A short password containing uppercase letters, lowercase letters, numbers, and symbols can still be weak.
* Longer passphrases often outperform shorter complex passwords.
* Memorable passphrases provide a good balance between usability and security.

## Password Attack Methods

### 1. Brute Force Attack

Attempts every possible combination of characters until the correct password is found.

### 2. Dictionary Attack

Uses lists of common words, phrases, and leaked passwords to guess passwords quickly.

### 3. Rainbow Table Attack

Uses precomputed hash tables to reverse password hashes. Modern defenses such as salting and bcrypt significantly reduce this risk.

### 4. Credential Stuffing

Uses usernames and passwords leaked from one website to gain access to accounts on other websites where the same password has been reused.

## Best Practices for Strong Passwords

* Use passwords that are at least 12–16 characters long.
* Prefer passphrases over short complex passwords.
* Avoid personal information such as names, birthdays, and years.
* Avoid common words and predictable keyboard patterns.
* Use a unique password for every account.
* Enable Multi-Factor Authentication (MFA) whenever possible.
* Consider using a password manager to generate and store passwords securely.

## Conclusion

This exercise demonstrated that password length is often more important than character variety. While complexity helps, long and memorable passphrases provide significantly stronger protection against modern password-cracking techniques. The password `:Harry potter@97` achieved the strongest result, showing that a well-constructed passphrase can be both user-friendly and highly secure.
