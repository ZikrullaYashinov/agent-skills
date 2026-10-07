# 🤖 AI Agent Skills Hub

Ushbu repozitoriy AI Coding Agentlar (Antigravity, Claude Code, Cursor, Codex) uchun standartlashtirilgan, qayta ishlatiluvchi **Agentic Skills** to'plamidir.

---

## 🚀 Yangi kompyuterda ishga tushirish (1 daqiqada)

Plaginlarni qo'lda o'rnatish shart emas — barcha sozlamalar `.obsidian` ichida saqlangan.

1. **Reponi klon qiling:**
   ```bash
   git clone https://github.com/ZikrullaYashinov/agent-skills.git
   ```
2. **Obsidian dasturini oching** va **"Open folder as vault"** ni bosib, klon qilingan papkani tanlang.
3. Agar Obsidian birinchi ochilishda so'rasa:
   - *"Trust author and enable plugins"* (Muallifga ishonish va plaginlarni yoqish) tugmasini bosing.
4. **Git sozlamasini tekshiring:**
   - Yangi kompyuteringizda GitHub SSH/HTTPS sozlangan bo'lsa, Obsidian Git avtomatik sinxronizatsiyani davom ettiradi.

---

## 📁 Papkalar tuzilishi

- **`Dashboard.md`** — Dataview orqali barcha skillar, ularning parametrlari va teglarini ko'rsatib turuvchi asosiy boshqaruv paneli.
- **`skills/`** — Barcha tayyor agent skillari (`.md`).
- **`templates/`** — Yangi skill yaratish uchun universal shablon.
- **`.agent/workflows`** — Antigravity agenti uchun avtomatik Slash (`/`) komandalar bog'lanmasi.

---

## 🛠️ Loyihalarga qanday ulanadi?

### 1-usul: Antigravity Workspace sifatida (Eng osoni - Sinxronizatsiyasiz!)
Antigravity-ga ushbu Obsidian papkasini loyiha (workspace) sifatida qo'shib qo'ying. Shunda har qanday boshqa loyihada ishlaganda ham barcha skillar avtomatik ravishda `/` menyusida chiqadi!

### 2-usul: Symlink orqali (Boshqa loyihalar uchun)
```bash
# Loyiha ichida turib:
ln -s ~/path/to/agent-skills/skills .agent/skills
```

---

## ✍️ Yangi skill qo'shish qoidalari

Har bir skill quyidagi standart YAML frontmatter bilan boshlanishi shart:

```markdown
---
name: skill-nomi
description: "Qisqacha tavsifi"
tags: [kategoriya, soha]
project: "loyiha_nomi"
target_branch: "asosiy_branch"
source_branch: "tekshiriladigan_branch"
output_file: "REPORT.md"
---
```
