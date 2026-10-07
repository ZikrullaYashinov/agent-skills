# 🤖 Mening AI Agent Skillarim

Quyida barcha mavjud skillar, ularning versiyasi, tavsifi va teglari avtomatik yig'iladi:

```dataview
TABLE 
    version as "Versiya",
    description as "Tavsifi",
    tags as "Teglar",
    file.mtime as "Oxirgi o'zgarish"
FROM "skills"
SORT file.name ASC
```
