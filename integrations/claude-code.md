# 🟣 Claude Code Init Prompt

> **Foydalanish:** Yangi loyihada Claude Code (terminal yoki CLI) bilan ishlashni boshlaganingizda ushbu matnni 1 marta chatga yuboring.

---

### 📋 Chatga nusxalab tashlanadigan matn:

```markdown
Mening markaziy Obsidian skillarimni ushbu loyihaga Claude Code custom commands sifatida ulab ber:

- Obsidian skills yo'li: /Users/zikrulla/Desktop/obsidian/skills

Bajariladigan qadamlar:
1. Loyihada `.claude/commands/` papkasi borligini tekshir, yo'q bo'lsa yarat (`mkdir -p .claude/commands`).
2. Obsidian skills papkasidagi barcha `.md` fayllarni `.claude/commands/` ga symlink orqali ula:
   `ln -sf /Users/zikrulla/Desktop/obsidian/skills/*.md .claude/commands/`
3. Claude Code terminalida `/` bosilganda paydo bo'ladigan yangi slash-komandalar ro'yxatini jadval ko'rinishida ko'rsat.
```
