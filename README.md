# DigitalProduct — โรงงานหา/สร้าง/ขาย digital product

> เจ้าของ: software engineer 10 ปี อยู่ไทย ขายตลาดโลก เป้าหมาย passive income
> เริ่ม 25 ก.ค. 2026 | สถานะ: **Stage 0 — ยังไม่รู้จักตลาด ยังไม่เลือกอะไร**

---

## เข้าที่ไหนก่อน

| ถ้าคุณ... | ไปที่ |
|---|---|
| เพิ่งเปิด session ใหม่ | [CLAUDE.md](CLAUDE.md) — บริบท + กฎประจำบ้าน |
| อยากรู้ว่าตอนนี้เราอยู่ตรงไหน | [pipeline/STATUS.md](pipeline/STATUS.md) |
| อยากเข้าใจว่าสายพานทำงานยังไง | [pipeline/README.md](pipeline/README.md) |
| อยากรู้ว่าเรารู้อะไรแล้วบ้าง | [knowledge/](knowledge/) |
| อยากรู้ว่าเรา**ไม่รู้**อะไร | [knowledge/99-open-questions.md](knowledge/99-open-questions.md) |
| อยากรู้ว่ามี agent อะไรบ้าง ทำอะไร | [.claude/agents/](.claude/agents/) และตารางด้านล่าง |
| อยากปูพื้นความรู้เรื่อง digital product | [course/](course/README.md) — คอร์ส 3 บท |

---

## สายพาน (pipeline) แบบย่อ

```
Stage 0  MAP        ทำแผนที่ตลาด — ใครซื้ออะไร เงินอยู่ไหน        ← 📍 อยู่ตรงนี้
Stage 1  SCOUT      ล่าโอกาส 30-50 ตัวจากสัญญาณ demand จริง
Stage 2  SCREEN     ให้คะแนน คัดเหลือ 3-5 ตัว
Stage 3  VALIDATE   พิสูจน์ด้วยเงินจริง/คนจริง ว่ามีคนจ่าย
Stage 4  BUILD      สร้าง v1 ที่เล็กที่สุดที่ขายได้
Stage 5  LAUNCH     ปล่อย + สร้างเครื่องยนต์ traffic
Stage 6  OPERATE    รับเงิน ภาษี support retention
Stage 7  DECIDE     kill หรือ scale → วนกลับ Stage 1
```

แต่ละ stage มี **gate** ที่ต้องผ่านก่อนไปต่อ และมี **เกณฑ์ kill** ที่ชัดเจน — ดูรายละเอียดที่ [pipeline/README.md](pipeline/README.md)

---

## ทีม agent

เรียกใช้ผ่าน Task/Agent tool หรือบอกชื่อกับ Claude ตรง ๆ ได้เลย

### 🔍 หน่วยลาดตระเวน (Recon) — ใช้ Sonnet ประหยัด token
| Agent | หน้าที่ | ใช้ที่ Stage |
|---|---|---|
| [market-cartographer](.claude/agents/market-cartographer.md) | ทำแผนที่ตลาดทั้งใบ **ฝั่งคนซื้อ** — segment, หมวด, ราคา, ปริมาณเงิน | 0 |
| [niche-scout](.claude/agents/niche-scout.md) | ล่าสัญญาณ demand จริง — คนบ่นที่ไหน ค้นอะไร จ่ายเงินให้อะไรอยู่แล้ว | 1 |
| [competitor-analyst](.claude/agents/competitor-analyst.md) | ผ่าคู่แข่ง — ราคา positioning traffic มาจากไหน จุดอ่อน | 1-2 |
| [fact-checker](.claude/agents/fact-checker.md) | ไล่ตรวจตัวเลขกับต้นทาง ฆ่าสถิติมั่วจากเว็บ AI-slop | ทุก stage |

### 🧠 หน่วยยุทธศาสตร์ (Strategy) — ใช้ Opus เพราะผลผลิตคือดุลยพินิจ
| Agent | หน้าที่ | ใช้ที่ Stage |
|---|---|---|
| [offer-architect](.claude/agents/offer-architect.md) | แปลงโอกาสเป็นข้อเสนอ — positioning, ราคา, packaging, moat กัน AI | 2-3 |
| [red-team](.claude/agents/red-team.md) | ถล่มทุกแผนให้พัง หา assumption ที่ผิด รวมถึงถล่มความมั่นใจของ Claude เอง | ทุก stage |
| [decision-keeper](.claude/agents/decision-keeper.md) | ให้คะแนนตัวเลือก คุม gate เขียน decision log กันลืมว่าทำไมถึงเลือก | 2, 7 |

### 🧪 หน่วยพิสูจน์ (Validation)
| Agent | หน้าที่ | ใช้ที่ Stage |
|---|---|---|
| [demand-validator](.claude/agents/demand-validator.md) | ออกแบบการทดสอบว่ามีคนจ่ายจริงไหม ก่อนลงแรงสร้าง | 3 |

### 📣 หน่วยการตลาด (Go-to-market)
| Agent | หน้าที่ | ใช้ที่ Stage |
|---|---|---|
| [copywriter](.claude/agents/copywriter.md) | เขียน landing page / sales copy / email / ad copy (อังกฤษ) | 3-5 |
| [seo-strategist](.claude/agents/seo-strategist.md) | SEO ยุค AI Overview — alternative/vs pages, programmatic, GEO/AEO | 5 |
| [audience-builder](.claude/agents/audience-builder.md) | สร้างคนฟัง — build-in-public, X, short-form, community | 1-7 (เริ่มเร็วสุด) |
| [launch-manager](.claude/agents/launch-manager.md) | คุม launch 4 สายพร้อมกัน PH/HN/X/community | 5 |
| [media-buyer](.claude/agents/media-buyer.md) | ยิงแอด — และคอยห้ามไม่ให้ยิงตอนที่ยังไม่ควรยิง | 5-6 |

### 💰 หน่วยเงินและปฏิบัติการ (Money & Ops)
| Agent | หน้าที่ | ใช้ที่ Stage |
|---|---|---|
| [monetization-ops](.claude/agents/monetization-ops.md) | ระบบรับเงิน MoR, license key, ภาษีไทย, การโอนเงิน | 4-6 |
| [funnel-analyst](.claude/agents/funnel-analyst.md) | ตัวเลข funnel, CRO, LTV/CAC, cohort | 5-7 |
| [support-retention](.claude/agents/support-retention.md) | support playbook, เก็บ testimonial, ลด churn | 6-7 |

**ตอนนี้ที่ Stage 0 ใช้จริงแค่ 3 ตัว**: `market-cartographer`, `fact-checker`, `red-team`
ที่เหลือเตรียมไว้ก่อน จะเริ่มทำงานเมื่อถึง stage ของมัน

---

## กฎที่สำคัญที่สุด

> **ห้ามชี้ทางถ้าไม่ได้ถูกขอ** — หน้าที่ของทีมนี้คือวางภูมิประเทศให้เห็นทั้งผืน ไม่ใช่ชี้นิ้วว่าไปทางไหน
> การตัดสินใจเป็นของเจ้าของโปรเจกต์คนเดียว

อ่านกฎทั้ง 8 ข้อที่ [CLAUDE.md](CLAUDE.md)
