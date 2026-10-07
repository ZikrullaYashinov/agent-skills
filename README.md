# 🤖 AI Agent Skills Hub

Ushbu repozitoriy barcha AI Coding Agentlar (**Antigravity, Claude Code, Cursor, Codex**) uchun standartlashtirilgan, qayta ishlatiluvchi va markazlashgan **Agentic Skills** boshqaruv tizimidir.

---

## ⚡ Qanday ishlaydi? (Arxitektura)

```text
Obsidian (Yozish & Boshqarish) 
       │
       ▼
    skills/ ──(Jonli symlink)──► .agent/workflows/ ──► Antigravity (Slash "/" menyusi)
       │
       ▼
 GitHub (Avtomatik 10 daqiqalik zaxira / Sync)
```

1. **Obsidianda yozasiz:** Yangi skill shablon asosida `skills/` papkasida yaratiladi.
2. **Antigravity darhol taniydi:** `.agent/workflows` papkasi to'g'ridan-to'g'ri `skills/` ga ulangan, shuning uchun chatda `/` bosganda darhol paydo bo'ladi.
3. **GitHub saqlaydi:** `Obsidian Git` plagini har bir o'zgarishni orqa fonda avtomatik commit va push qilib boradi.

---

## 🚀 Yangi kompyuterda ishga tushirish (1 daqiqada)

Plaginlar va sozlamalarni qo'lda o'rnatish shart emas — barcha konfiguratsiyalar `.obsidian` ichida saqlangan.

1. **Reponi klon qiling:**
   ```bash
   git clone https://github.com/ZikrullaYashinov/agent-skills.git
   ```
2. **Obsidian dasturini oching** va **"Open folder as vault"** orqali klon qilingan papkani ko'rsating.
3. Birinchi ochilishda:
   - *"Trust author and enable plugins"* tugmasini bosing.
4. **Git sozlamasini tekshiring:**
   - GitHub hisobingiz sozlangan bo'lsa, avtomatik sinxronizatsiya o'z-o'zidan ishlay boshlaydi.

---

## 📁 Papkalar tuzilishi

- **`Dashboard.md`** — Dataview orqali barcha skillar, ularning parametrlari va teglarini ko'rsatuvchi asosiy boshqaruv paneli.
- **`skills/`** — Barcha faol agent skillari (`.md`).
- **`templates/`** — Yangi skill yaratish uchun universal shablon.
- **`integrations/`** — Turli agentlar (Antigravity, Claude, Cursor) uchun integratsiya qo'llanmalari.
- **`.agent/workflows`** — Antigravity agenti uchun avtomatik Slash (`/`) komandalar bog'lanmasi (symlink).

---

## 🛠️ Loyihalarga qanday ulanadi?

### 1-usul: Antigravity Workspace sifatida (Eng osoni — Tavsiya etiladi ⭐)
Antigravity loyihangizga (`Folders` bo'limiga) ushbu `obsidian/` papkasini qo'shib qo'ying. Shunda har qanday loyihada ishlaganda ham barcha skillar avtomatik ravishda `/` menyusida chiqadi (hech qanday nusxalash shart emas).

### 2-usul: Boshqa agentlar uchun (Claude Code / Cursor)
- **Claude Code:** `.claude/commands` papkasiga ulanadi.
- **Cursor / Copilot:** `.cursor/rules` papkasiga bog'lanadi.
*(Batafsil ma'lumot `integrations/` papkasidagi fayllarda keltirilgan).*

---

## ✍️ Yangi skill qo'shish standarti

Har bir yangi skill quyidagi toza YAML frontmatter bilan boshlanishi kerak:

```markdown
---
name: skill-nomi
description: "Ushbu skill nima qilishi haqida qisqacha tavsif"
tags: [soha, kategoriya]
project: "loyiha_nomi"
target_branch: "development"
source_branch: "feature-branch"
output_file: "REPORT.md"
---

# Role & Objective
...

## Strict Constraints
...

## Execution Workflow
...

## Output Format
...
```
