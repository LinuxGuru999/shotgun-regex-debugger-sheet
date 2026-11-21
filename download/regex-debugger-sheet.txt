# Regex Debugger Sheet

A one-page regex reference with common patterns

# Regex Debugger & Quick Reference Sheet

> **Goal:** Test, troubleshoot, and write regular expressions faster in one place.

---

## 1. Target String & Regex Input
*Paste your test string below and draft your regex pattern.*

*   **Test String:**
    ```text
    [ Paste text here to test against your regex ]
    ```
*   **Regex Pattern:**
    ```text
    / [ Paste pattern here ] / [ Flags ]
    ```
*   **Match Result:** 
    *   [ ] Match Found  
    *   [ ] No Match  
    *   [ ] Error

---

## 2. Cheat Sheet: Anchors & Quantifiers
| Symbol | Meaning | Example | Matches |
| :--- | :--- | :--- | :--- |
| `^` | Start of string/line | `^A` | "Apple", not "Banana" |
| `$` | End of string/line | `z$` | "Buzz", not "Zebra" |
| `*` | 0 or more times | `ab*c` | "ac", "abc", "abbc" |
| `+` | 1 or more times | `ab+c` | "abc", "abbc", not "ac" |
| `?` | 0 or 1 time (optional) | `colou?r` | "color", "colour" |
| `{n,m}` | Between $n$ and $m$ times | `\d{2,4}` | "12", "123", "1234" |

---

## 3. Cheat Sheet: Character Classes & Escapes
| Symbol | Meaning | Example | Matches |
| :--- | :--- | :--- | :--- |
| `.` | Any character (except newline) | `a.c` | "abc", "a1c", "a c" |
| `\d` | Any digit (0-9) | `\d+` | "42", "1990" |
| `\w` | Word char (a-z, A-Z, 0-9, _) | `\w+` | "User_1" |
| `\s` | Whitespace (space, tab, newline) | `a\sb` | "a b" |
| `[abc]` | Any character in brackets | `[aeiou]` | Any lowercase vowel |
| `[^abc]`| Any character NOT in brackets | `[^0-9]` | Any non-digit |

---

## 4. Common Production Patterns
*   **Email Address:** `^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$`
*   **URL (HTTP/HTTPS):** `https?://(www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)`
*   **Date (YYYY-MM-DD):** `^\d{4}-(0[1-9]|1[0-2])-(0[1-9]|[12]\d|3[01])$`
*   **IPv4 Address:** `^((25[0-5]|2[0-4]\d|[01]?\d\d?)\.){3}(25[0-5]|2[0-4]\d|[01]?\d\d?)$`

---

## 5. Worked Example
*Scenario: Extracting a standard US phone number (e.g., "555-123-4567") from a log file.*

*   **Test String:** `User called from 555-123-4567 regarding an order.`
*   **Regex Pattern:** `/\b\d{3}-\d{3}-\d{4}\b/g`
*   **Breakdown:**
    *   `\b` = Word boundary (ensures we don't match inside a larger number)
    *   `\d{3}` = Exactly 3 digits (`555`, `123`)
    *   `-` = Literal hyphen separator
    *   `\d{4}` = Exactly 4 digits (`4567`)
    *   `g` = Global flag (finds all matches in the string)
*   **Match Result:** `555-123-4567` (Match Successful)

---

## 6. Troubleshooting Log
*Use this space to note why a regex failed and how you fixed it.*

| Attempt | Issue / Error | Fix / Adjustment |
| :--- | :--- | :--- |
| *e.g., 1* | *Matched partial words* | *Added `\b` word boundaries.* |
| *2* | | |
| *3* | | |
