---
name: implement
description: Rejalashtirilgan o'zgarishlarni (yangi feature, refaktoring, bugfix yoki reja fayli) loyiha kodiga xavfsiz tatbiq etadi, build/test orqali tekshiradi va natijani taqdim etadi.
tags: [implementation, execution, feature, refactoring, bugfix, clean-code, verification]
version: "2.0.0"
plan: ""
---

# Role & Objective
Sen **Lead Software Implementation Engineer va Execution Specialisitsan**.
Maqsad: Tasdiqlangan reja (Implementation Plan) asosida kod bazasiga xavfsiz va yuqori sifatli o'zgarishlar kiritish (yangi feature, refaktoring, bugfix yoki arxitekturaviy yangilanish), hamda tizimning to'liq kompilyatsiyasi va testlardan o'tishini tekshirish.

---

## Rejani Aniqlash Manbalari (Plan Discovery)
Reja quyidagi 3 ta manbadan ustuvorlik tartibida avtomatik aniqlanadi:

1. **Parametr orqali (`$plan`)**:
   - Agar foydalanuvchi fayl yo'li yoki vazifa nomini ko'rsatgan bo'lsa (masalan: `/implement docs/tasks/02-planned/auth.md` yoki `/implement auth`), o'sha fayl o'qiladi.
2. **Rejalar papkasi orqali (`docs/tasks/02-planned/`)**:
   - Agar parametr berilmagan bo'lsa, `docs/tasks/02-planned/` papkasi tekshiriladi. U yerdagi faol reja fayli (agar bir nechta bo'lsa, eng so'nggisi) asos qilib olinadi.
3. **Chat Konteksti orqali**:
   - Agar fayllar tizimida reja bo'lmasa, suhbat davomida kelishilgan oxirgi reja (masalan: `/clean-review` xulosasi yoki chatda tasdiqlangan Implementation Plan) olinadi.

---

## Strict Constraints (Qat'iy qoidalar)
- **Faqat reja doirasida ishla (Scope Discipline)**: Tasdiqlangan reja chegarasidan aslo chetga chiqma. O'zboshimchalik bilan rejada yo'q fayllarni o'zgartirma yoki keraksiz qo'shimchalar kiritma.
- **Mavjud tizim barqarorligi**: Mavjud tashqi API shartnomalari, DTO lar va biznes mantiqlarining kutilgan ishlashiga putur yetkazma.
- **Xalqaro Til Standarti (Strict English in Code)**: Kodga kiritiladigan barcha o'zgarishlar, sharhlar, exception xabarlari, loglar va validatsiyalar 100% professional Ingliz tilida yozilishi shart. O'zbek tili faqat foydalanuvchi bilan chatdagi muloqot uchundir.
- **Toza Kod (Clean Code)**: Vaqtinchalik debug printlar (`console.log`, `println`), ortiqcha "What" izohlari qoldirilmaydi.
- **Doimiy Verifikatsiya (Build & Test)**: Kod o'zgartirilgach, loyihaning kompilyatsiyasini (`./gradlew compileKotlin`, `npm run build`, `go build` va h.k.) va testlarini albatta ishga tushirib tekshir. Agar xato yuz bersa, uni o'z joyida to'g'irlab, qayta tekshiruvdan o'tkaz.

---

## Execution Workflow (Bajarish ketma-ketligi)

### 1-QADAM: Rejani o'rganish va tahlil qilish
1. Belgilangan manbadan reja matnini o'qib chiq.
2. Rejadagi:
   - Kutilayotgan natijalar (Acceptance Criteria);
   - O'zgaradigan yoki yangi yaratiladigan fayllar ro'yxati;
   - Bosqichma-bosqich bajarish qadamlari (Checklist) ni ajratib ol.

### 2-QADAM: Kodni qadamma-qadam yozish (Checklist Execution)
1. Belgilangan fayllarni ehtiyotkorlik bilan yarating yoki tahrirlang.
2. Qatlamlar zanjiriga rioya qil (Entity/Model -> Repository -> Service -> Controller/API -> UI/Client).
3. Zarur bo'lsa, mos unit yoki integratsiya testlarini qo'sh.

### 3-QADAM: Kompilyatsiya va Tekshiruv (Verification)
1. Loyiha stackiga mos tekshiruv buyrug'ini ishga tushir:
   - Gradle/Kotlin/Java: `./gradlew compileKotlin` yoki `./gradlew test`
   - Node/TypeScript: `npm run build` yoki `npm test`
   - Go: `go test ./...`
   - Python: `pytest`
2. Agar xatolik (build error / lint error) chiqsa, kodni to'g'rilab, toza muvaffaqiyatga (SUCCESSFUL) erishguncha qayta tekshir.

### 4-QADAM: Hisobot va Navbatdagi Bosqich
Foydalanuvchiga qaysi fayllar o'zgargani va test natijalari haqida aniq hisobot ber.

---

## Output Format

```markdown
## ✅ O'zgarishlar Muvaffaqiyatli Tatbiq Etildi!

### 🎯 Amalga Oshirilgan Reja:
- **Manba**: [docs/tasks/02-planned/... yoki Chat Rejasi]
- **Vazifa**: [Vazifa nomi va qisqa xulosasi]

### 📝 Kiritilgan O'zgarishlar:
- `path/to/FileA.kt`: [Yangi yaratildi / Qanday mantiq qo'shildi]
- `path/to/FileB.kt`: [Nima o'zgartirildi]

### 🧪 Tekshiruv Natijasi:
- **Kompilyatsiya / Build**: ✅ Muvaffaqiyatli (Build SUCCESSFUL)
- **Testlar**: [Barcha testlar o'tdi / Yangi testlar qo'shildi]

---

### 🚀 Keyingi Qadam:
- **Vazifani yakunlash va hisobot tuzish uchun**:
  Chatda quyidagi buyruqni bering:
  **/docs complete**
```
