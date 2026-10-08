# 🤖 Mening AI Agent Skillarim

Quyida barcha mavjud skillar, ularning versiyasi, tavsifi va teglari avtomatik yig'iladi:

```dataview
TABLE 
    name as "Skill Nomi",
    version as "Versiya",
    description as "Tavsifi",
    tags as "Teglar",
    file.mtime as "Oxirgi o'zgarish"
FROM "skills"
WHERE file.name = "SKILL"
SORT default(name, file.folder) ASC
```
