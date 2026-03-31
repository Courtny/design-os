# Miller's Law

> The average person can only keep 7 (± 2) items in their working memory.

George Miller's 1956 paper established that working memory has a hard limit. The magic number is 7, plus or minus 2. Designers exploit this through chunking — organizing information into smaller, manageable groups that are easier to hold in mind.

---

## Core Principles

**Chunking** — Organizing information into smaller, meaningful groups reduces cognitive load. Seven individual digits are hard to hold; a phone number formatted as `(415) 555-0182` is easy because it's three chunks, not ten digits.

**Memory Constraints** — Don't expect users to remember information from one screen to the next. If a user needs a value from step 1 to complete step 3, show it again on step 3. Don't make them go back.

---

## Application

1. **Format long strings in blocks of 3-4** — Phone numbers, credit card numbers, confirmation codes. `4111 1111 1111 1111` is far easier to verify than `4111111111111111`.
2. **Limit navigation menus and category lists to roughly 5-9 items** — When you need more, group them under parent categories rather than listing everything flat.
3. **Use visual "chunks" to separate content types on a page** — Cards, section headers, and white space all serve as chunk boundaries that help users process one group at a time.
4. **Surface key context at the right moment** — In multi-step flows, show a summary of prior choices at each step. Don't make users remember what they selected two screens ago.

---

## What It Doesn't Mean

Miller's Law is frequently misquoted as "never show more than 7 items." That's too rigid. The real principle is about **working memory load** — how much a user has to hold in mind simultaneously. A long list is fine if users are scanning and selecting (recognition, not recall). It becomes a problem when they have to memorize or mentally juggle items.

---

## Related Foundations

- [`hicks-law.md`](hicks-law.md) — Hick's Law addresses decision time; Miller's addresses memory load. They're complementary — fewer, better-chunked choices reduce both.
- [`nielsens-heuristics.md`](nielsens-heuristics.md) — H6 (recognition rather than recall) is directly grounded in Miller's constraints
- [`gestalt-principles.md`](gestalt-principles.md) — Chunking is implemented visually through proximity and similarity
