# split_and_lock_versions.md  
**Version History: Split + Lock Security Framework**

---

## v1.0 (Initial Release)
- Defined the "Split + Lock" strategy
- Included a basic system prompt with inline instructions
- Introduced 5 knowledge files (checklist, testing, OWASP mapping, hardening guide)
- No audit tagging or advanced prompt injection handling

---

## v1.1
- Added role simulation defense to the system prompt
- Reworded fallback responses to improve user comprehension
- Improved denial logic around GPT development and assistance

---

## v1.2
- Introduced:
  - Replay + chained prompt resistance
  - Fallback response audit tagging: `(SECURITY_LOCKED)`
  - File access denial language
- Added: `SECURITY_LOCK_TAGS.md`, `SYSTEM_PROMPT_SCORING.yaml`

---

## v1.3 (Current Default)
- Restructured folder tree for modular deployment
- Updated `README.md` for simplicity and clarity
- Recommended dual system prompts:
  - `UNIVERSAL_GPT_SECURITY_TEMPLATE.md` (Standard)
  - `UNIVERSAL_GPT_SECURITY_TEMPLATE_HARDENED.md` (Enterprise)
- Hardened version includes:
  - Instruction hierarchy enforcement
  - Prompt injection pattern blocking
  - Content safety boundaries (emails, tokens, exploits)
  - Knowledge file protection logic
  - Canary token placeholders
- All fallback responses standardized with grep-friendly tags

---

## Next Candidate: v1.4 (Planned)
- Add: automatic validation hooks or testing harnesses (CI, red team logs)
- Consider: role-based config profile support
- Optional: integration with external logging or usage analytics

---
