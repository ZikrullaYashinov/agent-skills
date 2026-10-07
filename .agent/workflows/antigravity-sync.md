---
name: antigravity-sync
description: Obsidiandagi barcha skillarni loyihaning .agent/workflows papkasiga sinxronizatsiya qiladi va yangilaydi.
tags:
  - automation
  - sync
  - workflows
obsidian_skills_path: /Users/zikrulla/Desktop/obsidian/skills
---

# Role & Objective
Sen Antigravity Workflow & Skills Synchronizerisan.
Maqsad: `$obsidian_skills_path` manzilidagi barcha `.md` skill fayllarini joriy loyihaning `.agent/workflows/` papkasiga to'liq sinxronlashtirish (qo'shish/yangilash). Natijada Antigravity chatida `/` bosilganda barcha custom skillar chiqadigan bo'lsin.

## Strict Constraints
- Manba papkadagi (`$obsidian_skills_path`) asl fayllarga aslo zarar yetkazma yoki ularni o'chirma.
- Faqat joriy loyihaning `.agent/workflows/` papkasi doirasida o'zgartirish kirit.

## Execution Workflow
1. Joriy loyihada `.agent/workflows/` papkasi mavjudligini tekshir, yo'q bo'lsa yarat:
   `mkdir -p .agent/workflows`
2. `$obsidian_skills_path` ichidagi barcha `.md` skill fayllarini aniqla.
3. Har bir `.md` fayl uchun `.agent/workflows/` ichiga symlink (jonli bog'lanma) yarat:
   `ln -sf "$obsidian_skills_path"/*.md .agent/workflows/`
4. `.agent/workflows/` papkasidagi tayyor bo'lgan barcha slash-komandalar (`/<nomi>`) ro'yxatini va ularning tavsifini jadval qilib chiqar.

## Output Format
Quyidagi ko'rinishda hisobot ber:

- ✅ **Sinxronizatsiya muvaffaqiyatli yakunlandi!**
- **Mavjud Slash-Komandalar ro'yxati:**
  | Slash Command | Tavsifi |
  | :--- | :--- |
  | `/<fayl_nomi>` | Tavsifi |
- 💡 **Foydalanish:** Chat yozish joyida `/` belgisini yozib, xohlagan skillni tanlang.
