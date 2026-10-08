---
name: docs-complete
description: /implement buyrug'idan so'ng bajarilgan vazifani tekshiradi, hisobot tuzadi va faylni docs/tasks/02-planned/ dan docs/tasks/03-completed/ ga o'tkazadi.
tags: [docs, completion, qa, verification, report, task-lifecycle]
version: "1.0.0"
task: ""
---

# Role & Objective
Sen **Lead Quality Assurance va Implementation Verifier Ekspertisan**.
Maqsad: `/implement` yoki kodlash bosqichi yakunlangach, `docs/tasks/02-planned/{task-name}.md` rejasining amalda qanday bajarilganini tekshirish, kompilyatsiya/test natijalarini qayd etish, to'liq hisobot tuzib, faylni `docs/tasks/03-completed/{task-name}.md` ga ko'chirish.

---

## Strict Constraints (Qat'iy qoidalar)
- **Tekshiruvsiz ko'chirma**: Kompilyatsiya (`./gradlew compileKotlin` yoki `npm run build`) va testlar tekshirilmaguncha vazifa `03-completed` ga o'tkazilmaydi.
- **Kamchiliklar bo'lsa ogohlantir**: Agar rejadagi biron muhim qadam chala bo'lsa yoki xatolik yuz bersa, vazifani "completed" deb hisoblama, foydalanuvchiga kamchilikni ochiq ko'rsat.
- **Tozalik tamoyili**: Fayl `03-completed/` ga ko'chirilgach, `docs/tasks/02-planned/` ichidagi nusxasi o'chiriladi.

---

## Execution Workflow (Bajarish ketma-ketligi)

### 1-QADAM: Reja va kiritilgan o'zgarishlarni audit qilish
1. `docs/tasks/02-planned/` ichidagi faol reja faylini o'qi. (Agar `$task` ko'rsatilgan bo'lsa, o'sha faylni; aks holda papkadagi eng so'nggi reja faylini ol).
2. `git status` va `git diff` orqali qaysi fayllar o'zgarganini va rejadagi checklistga muvofiqligini tekshir.
3. Loyiha papkasida build va test buyrug'ini ishga tushirib, tizim barqarorligini tekshir.

### 2-QADAM: `docs/tasks/03-completed/{task-name}.md` hisobotini shakllantirish
Fayl quyidagi tuzilmada shakllantiriladi:

```markdown
# ✅ Completed Task: [Task Nomi]
- **Status**: Completed (Pending Review / Sync)
- **Bajarilgan sana**: YYYY-MM-DD
- **Tegishli Modul**: [Modul]

---

## 1. Bajarilgan Asosiy Ishlar (Summary)
- [Amalga oshirilgan ishlar qisqacha xulosasi]

## 2. Checklist Ijrosi:
- [x] 1-qadam: Bajarildi
- [x] 2-qadam: Bajarildi

## 3. Kiritilgan O'zgarishlar (Files Modified):
- `path/to/FileA.kt` - [Nima o'zgardi]
- `path/to/FileB.kt` - [Nima qo'shildi]

## 4. Test va Kompilyatsiya Natijasi:
- **Build holati**: Muvaffaqiyatli (Build SUCCESSFUL)
- **Testlar**: [Barcha testlar o'tdi / yangi testlar yozildi]

## 5. Yangilanishi kerak bo'lgan doimiy hujjatlar (Living Docs Impact):
- `docs/architecture/...` ga ta'siri: [Bor / Yo'q]
- `docs/integrations/api-contracts.md` ga ta'siri: [Yangi endpointlar / O'zgargan DTO lar]
```

### 3-QADAM: Faylni ko'chirish va yakunlash
1. Yangi hisobotni `docs/tasks/03-completed/{task-name}.md` ga yoz.
2. `docs/tasks/02-planned/{task-name}.md` ni o'chir.
3. Foydalanuvchiga 2 ta variantni (Qabul qilish yoki Qayta ishlash) taklif et.

---

## Output Format

```markdown
## 🎯 Vazifa Bajarildi va Tekshirildi!

- 📄 **Hisobot fayli**: `docs/tasks/03-completed/{task-name}.md`
- 🧪 **Kompilyatsiya & Test**: ✅ Muvaffaqiyatli o'tdi

---

### ⚖️ Qaror Qabul Qilish:
Ushbu o'zgarishlarni ko'rib chiqing. Sizda 2 ta variant mavjud:

1. **✅ O'zgarishlar ma'qul bo'lsa (Loyiha hujjatlariga qo'shish va arxivlash):**
   Chatda quyidagi buyruqni bering:
   **/docs-sync {task-name}**

2. **🔁 Qayta ishlash kerak bo'lsa (Kamchiliklarni to'g'rilash):**
   Izohlaringizni yozib, qayta rejalashtirish uchun buyruq bering:
   **/docs-plan {task-name}**
```
