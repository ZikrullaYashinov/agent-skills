# 🤖 AI Agent Skills Hub

Ushbu repozitoriy barcha AI Coding Agentlar (**Antigravity, Claude Code, Cursor, Codex**) uchun standartlashtirilgan, qayta ishlatiluvchi va markazlashgan **Agentic Skills** boshqaruv tizimidir.

---

## ⚡ Qanday ishlaydi? (Arxitektura)

```text
Obsidian (Yozish & Boshqarish) 
       │
       ▼
    skills/ ──(Jonli symlink)──► .agents/skills/ ──► Antigravity (Slash "/" menyusi & Semantic Discovery)
       │
       ▼
 GitHub (Avtomatik 10 daqiqalik zaxira / Sync)
```

1. **Obsidianda yozasiz:** Yangi skill shablon asosida `skills/<skill_name>/SKILL.md` katalogida yaratiladi.
2. **Antigravity darhol taniydi:** `.agents/skills` papkasi to'g'ridan-to'g'ri `skills/` ga ulangan, shuning uchun chatda `/` bosganda darhol paydo bo'ladi va agent kerakli vaziyatda uni avtomatik (Semantic Discovery orqali) chaqira oladi.
3. **Multi-file qo'llab-quvvatlash:** Har bir skill ichida qo'shimcha skriptlar (`scripts/`), namunalar (`examples/`) yoki ma'lumotnomalar (`references/`) saqlash mumkin.
4. **GitHub saqlaydi:** `Obsidian Git` plagini har bir o'zgarishni orqa fonda avtomatik commit va push qilib boradi.

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

- **`Dashboard.md`** — Dataview orqali barcha skillar, ularning versiyasi, tavsifi va teglari avtomatik yig'iladigan boshqaruv paneli.
- **`skills/`** — Barcha faol agent skillari kataloglari (`skills/<name>/SKILL.md`).
- **`templates/`** — Yangi skill yaratish uchun universal shablon.
- **`.agents/skills`** va **`.agent/skills`** — Antigravity agenti uchun avtomatik Skills va Slash (`/`) komandalar bog'lanmasi (symlink).
- **`.cursor/rules`** — Cursor & Codex agentlari uchun qoidalar bog'lanmasi (symlink).

---

## 🛠️ Loyihalarga qanday ulanadi?

### 1. Antigravity & Cursor Workspace sifatida (Eng osoni — Tavsiya etiladi ⭐)
Antigravity yoki Cursor loyihangizga (`Folders` / `Add Folder to Workspace` bo'limiga) ushbu `obsidian/` papkasini qo'shib qo'ying. Shunda har qanday loyihada ishlaganda ham barcha skillar avtomatik ravishda Antigravity'da `/` menyusida, Cursor'da esa `@rules` da chiqadi (hech qanday qo'lda nusxalash shart emas).

### 2. Claude Code uchun (Global rejim)
Butun kompyuteringizdagi barcha loyihalar uchun 1 marta buyruq berish kifoya:
```bash
mkdir -p ~/.claude
ln -sfn ~/Desktop/obsidian/skills ~/.claude/commands
```

---

## ✍️ Yangi skill qo'shish standarti

Har bir yangi skill `skills/<skill_name>/SKILL.md` manzili ostida joylashadi va quyidagi toza YAML frontmatter bilan boshlanadi:

```markdown
---
name: skill-nomi
description: "Ushbu skill nima qilishi va qachon ishlatilishi haqida 1 jumlalik aniq tavsif"
tags: [soha, kategoriya]
version: "1.0.0"
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
