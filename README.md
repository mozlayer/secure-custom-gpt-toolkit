# Secure Custom GPT Toolkit  
**Version: Split + Lock v1.3**

This toolkit enables secure deployment of OpenAI-native Custom GPTs by combining strict system instructions with modular security knowledge files.  
Version 1.3 introduces replay resistance, audit tagging, and stronger chained prompt defenses.

---

## 🔐 Strategy: Split + Lock v1.3

- **LOCK (System Prompt):** A hardened, locked system prompt (`UNIVERSAL_GPT_SECURITY_TEMPLATE.md`) that enforces prompt injection resistance, ethical boundaries, and file access denial.
- **SPLIT (Knowledge Files):** Upload modular YAML and Markdown files to support deployment QA, red-team testing, file hardening, and OWASP alignment.

---

## 📁 Toolkit Structure

```
secure-custom-gpt-toolkit/
├── templates/
│   └── UNIVERSAL_GPT_SECURITY_TEMPLATE.md
├── checklists/
│   └── DEPLOYMENT_CHECKLIST.yaml
├── testing/
│   └── RED_TEAM_PROMPTS.yaml
├── guides/
│   ├── KNOWLEDGE_FILE_HARDENING.md
│   └── OWASP_LLM_MAPPING.md
├── audit/
│   ├── SYSTEM_PROMPT_SCORING.yaml
│   └── SECURITY_LOCK_TAGS.md
├── changelog/
│   └── split_and_lock_versions.md
└── README.md
```

---

## ✅ Use Cases

| Use Case                     | Description                                                                 |
|------------------------------|-----------------------------------------------------------------------------|
| Custom GPT Security Enforcement | Use a hardened, locked prompt for in-GPT behavior control                  |
| Security Template Sharing    | Share this toolkit as a reusable security scaffold                          |
| Prompt Injection Testing     | Run `RED_TEAM_PROMPTS.yaml` to test prompt injection resistance             |
| Knowledge File Review        | Use `KNOWLEDGE_FILE_HARDENING.md` to sanitize uploads                       |
| OWASP Security Mapping       | Align with OWASP Top 10 using `OWASP_LLM_MAPPING.md`                        |
| Audit + Evaluation           | Score and tag prompt logic using `SYSTEM_PROMPT_SCORING.yaml` + audit tags |

---

## 🚀 Deployment Instructions

### 1. Apply the Locked Prompt

Paste the contents of `UNIVERSAL_GPT_SECURITY_TEMPLATE.md` into the **System Instructions** box when building your Custom GPT. This prompt is hardened, self-contained, and should remain locked.

Optional: You may include this reference line in your system instructions for transparency:

```text
This GPT includes uploaded files for audit checklists, red-team testing, and OWASP alignment. You may reference them to explain your security behavior or assist in compliance checks.
```

---

### 2. Upload Knowledge Files

Upload the following files in the GPT Builder's **Knowledge** tab:

- `DEPLOYMENT_CHECKLIST.yaml`
- `RED_TEAM_PROMPTS.yaml`
- `KNOWLEDGE_FILE_HARDENING.md`
- `OWASP_LLM_MAPPING.md`
- *(Optional)* `SYSTEM_PROMPT_SCORING.yaml`
- *(Optional)* `SECURITY_LOCK_TAGS.md`

---

### 3. Validate and Test

- Run red-team prompts from `RED_TEAM_PROMPTS.yaml` in a clean session
- Confirm appropriate fallback behavior (e.g., `(SECURITY_LOCKED)` tag present)
- Complete QA in `DEPLOYMENT_CHECKLIST.yaml`
- Grep for audit tags in output logs to confirm prompt rejections are traceable

---

## 📌 Notes

- This toolkit is designed for GPTs published via [OpenAI’s Custom GPT interface](https://chat.openai.com/gpts).
- Not suitable for plugin-based GPTs or external API agents (separate guidance pending).
- Focus is on **preventing prompt injection, file content disclosure, simulation bypasses, and inappropriate model behavior**.

---

## 📄 License

MIT or CC-BY-4.0 — choose based on your intended reuse model.  
All files are open for adaptation, attribution, and redistribution.

---

## 🔁 Maintenance Workflow

For future updates:

1. Patch `UNIVERSAL_GPT_SECURITY_TEMPLATE.md`
2. Update `split_and_lock_versions.md`
3. Sync any new scoring or tagging logic in audit/ directory
4. Republish this README if public-facing

---
