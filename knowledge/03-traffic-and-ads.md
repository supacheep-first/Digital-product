# 03 — Traffic และโฆษณา

> เก็บข้อมูล 25 ก.ค. 2026 | ตรวจซ้ำ ต.ค. 2026
> ⚠️ **benchmark ส่วนใหญ่ในไฟล์นี้เป็น ⚠️ (aggregator)** ยกเว้นที่ระบุ ✅ — ใช้ประเมินคร่าว ๆ ห้ามใช้ทำ financial model

---

## 1. คณิตศาสตร์พื้นฐานที่ต้องรู้ก่อน

```
สินค้า $29 + Meta Ads:
  CPC เฉลี่ย $1.72 ⚠️ × ~40 คลิก (CVR 2-3%) = ค่าแอด $68.80 ต่อ 1 ยอดขาย
  รายได้สุทธิ $29 − 5% = $27
  → ขาดทุน $41.80 ต่อชิ้น

สินค้า $299 + Meta Ads:
  ค่าแอด $68.80 (สมมติ CVR เท่ากัน — จริงจะต่ำกว่า)
  รายได้สุทธิ $284
  → กำไรขั้นต้น $215
```

| ราคาสินค้า | Paid ads |
|---|---|
| $10-50 | ❌ แทบไม่มีทางคุ้ม ยกเว้นมี upsell/subscription ต่อท้ายดัน AOV |
| $50-200 | 🟡 ต้อง funnel + retargeting เก่งเท่านั้น |
| $200+ / subscription | ✅ ใช้ได้จริง |

---

## 2. Benchmark โฆษณา 2026

| แพลตฟอร์ม | CPC | CPM / CTR | งบขั้นต่ำสมจริง | low-ticket | high-ticket |
|---|---|---|---|---|---|
| **Google Search** ✅ | $5.42 (Education $4.81, E-com $4.14) | CTR 6.64% | $25-50/วัน | ❌ | 🥇 intent สูงสุด |
| **Meta** ⚠️ | $1.72 (Traffic $0.70, Lead $1.92) | CPM $14.19, CTR ~1.4% | $25-50/วัน | 🟡 | ✅ ดีเมื่อ + retargeting |
| **TikTok** ⚠️ | median $0.62 (จริง $0.30-1.50) | CPM $4-13 | ขั้นต่ำระบบ $50/campaign + $20/ad group → จริง $700-1,000/เดือน | ✅ ดีสุดในกลุ่ม | ❌ |
| **YouTube** ⚠️ | ~$0.49 (Shorts CPV $0.10-0.30) | CPM $9.29 | $10-20/วัน | 🟡 | ✅ สร้าง authority |
| **Reddit** ⚠️ | $0.50-2.50 (B2B/SaaS $4-8) | CPM $2-10 | $5-20/วัน | ✅ ถ้าเจอ sub ตรง | ✅ ถูกกว่า LinkedIn 40-80% |
| **Pinterest** ⚠️ | ~$0.83 | CPM ขัดแย้งกัน ($2-5 vs $9.20) | $10-25/วัน | 🥇 template/printable | ❌ |
| **Microsoft/Bing** ⚠️ | $1.54 (ถูกกว่า Google 42-48%) | CTR 3.1%, CVR 3.5% | $10-20/วัน | 🟡 | ✅ CAC ถูกกว่า Google |
| **LinkedIn** ⚠️ | $5-10 | CPM $30-50 (ถึง $100), CTR 0.52% | $30-50+/วัน | ❌ | ✅ คอร์ส B2B |
| **X/Twitter** ⚠️ | $0.50-2 | CPM $2-9 (**ข้อมูลมั่วสุดในตาราง**) | $10-20/วัน | ❓ | ❓ |

**แหล่งเดียวที่เป็น primary:** WordStream/LocaliQ "2026 Google Ads Benchmarks" (พ.ค. 2026) ✅

---

## 3. Meta Ads 2026

1. **Advantage+ เป็น default ไม่ใช่ตัวเลือกอีกแล้ว** ⚠️ — ก.พ. 2026 Meta รวม manual + Advantage+ เป็น interface เดียว
   - Advantage+ = 62% ของงบ e-commerce, ROAS สูงกว่า 22%, CPA ต่ำกว่า 32%
   - **[ความเห็น]** การ "เลือก audience เก่ง" ไม่ใช่ทักษะที่ทำเงินอีกแล้ว — เหลือ **creative** กับ **offer**
2. **Creative ที่ชนะ** ⚠️: วิดีโอแนวตั้งสไตล์ UGC 15-30 วิ, hook ใน 3 วิแรก, เข้าใจได้โดยไม่เปิดเสียง → CTR สูงกว่า 4 เท่า CPA ต่ำกว่า ~50% เทียบโฆษณาสตูดิโอ
3. **นโยบาย** ⚠️: 47 policy update ใน มี.ค. 2026 รวมถึงบังคับเปิดเผย AI-generated content; หมวด "หาเงินออนไลน์" โดนตรวจหนัก **ห้ามสัญญาตัวเลขรายได้**
   - ❌ "ทำเงิน $10,000/เดือน"  ✅ "เข้าร่วมชุมชนนักพัฒนา 2,000 คน"
   - ตรวจต้นทางก่อนยิงจริง: transparency.meta.com/policies/ad-standards/

---

## 4. SEO ในยุค AI Overview

### ข้อมูลจริง ✅
| ผลการศึกษา | ตัวเลข |
|---|---|
| Ahrefs (300K keyword, ธ.ค. 2023 vs ธ.ค. 2025) | เมื่อมี AI Overview → **CTR อันดับ 1 ลดลง 58%** |
| Seer Interactive (53 แบรนด์, 5.47M query, ม.ค. 2025-ก.พ. 2026) | CTR หด **61%** (0.61% vs 1.62%) |
| Semrush 2026 | zero-click **67.1%** (จาก 49% ปี 2019); query ที่มี AI Overview **~83%**; Google AI Mode **~93%** |
| Semrush 2026 — แยกตาม intent | **query เชิงข้อมูล 74% จบแบบ zero-click แต่ query เชิงซื้อขายเหลือ 31%** |

> ⭐ บรรทัดสุดท้ายคือกุญแจทั้งหมด — **intent เชิงซื้อขายยังคลิกอยู่**

### สิ่งที่ยังได้ผล vs ตายแล้ว
| ประเภทคอนเทนต์ | สถานะ |
|---|---|
| "how to X" ทั่วไป | 💀 ตาย |
| **"[คู่แข่ง] alternative"** | 🟢 ยังแรง |
| **"[A] vs [B]"** | 🟢 ยังแรง |
| **"best X for Y" (เจาะจงมาก)** | 🟢 ยังแรง |
| **pricing / integration / use case page** | 🟢 intent ซื้อสูง |
| ข้อมูล/ผลวิจัยต้นฉบับ | 🟢 ได้ทั้ง traffic และ backlink |

**[ข้อเท็จจริง]** HeadshotPro ($300K MRR), PDF.ai, Bannerbear, ShipFast — **ทุกเคสใหญ่ใช้ comparison/alternative SEO เป็นช่องทางหลัก**

---

## 5. GEO/AEO — ทำให้ AI อ้างอิงเรา

**ยุทธวิธีที่เป็นรูปธรรม:**
1. **ส่ง sitemap เข้า Bing Webmaster Tools** — ChatGPT search ใช้ index ของ Bing (ทำได้ใน 10 นาที คนส่วนใหญ่ไม่ทำ)
2. ใส่ชื่อผู้เขียน + วันที่ + สัญญาณ E-E-A-T ให้ชัด
3. Schema markup (FAQPage, Article)
4. ผลิตสถิติ/ข้อมูลต้นฉบับ — AI ชอบอ้างตัวเลขที่มีแหล่งเดียว
5. ดูแล listing/directory/review — Yext (6.8M citation) พบว่า **86% ของการอ้างอิงโดย AI มาจากแหล่งที่แบรนด์ควบคุมเอง** (44% เว็บตัวเอง, 42% listing/review) ⚠️ *(vendor data)*

> 🔴 **ระวัง:** ตัวเลข "traffic จาก ChatGPT convert 14-16% vs Google 1.76%" และ "AI search visits +42.8% YoY" — **vendor ทั้งหมด ไม่เปิด methodology** ⚠️ ห้ามเอาไปวางแผน (ดู [99-open-questions Q7](99-open-questions.md))

---

## 6. ช่องทาง organic อื่น ๆ

| ช่องทาง | สภาพ 2026 |
|---|---|
| **Build in public (X)** | ยังใช้ได้ แต่กลไกเปลี่ยน: ยุค 2019 "โชว์ตัวเลข" → ยุค 2026 **"โชว์ workflow และวิธีคิด"** ⚠️ benchmark ที่อ้างกัน: follower engage จริง ~2,000+ ก่อน launch → signup 300-800 คนวัน launch ⚠️ เคสยืนยัน: Pieter Levels, Arvid Kahl (FeedbackPanda → $55K MRR ไม่ยิงแอดเลย) ✅ |
| **YouTube long-form** | 📈 มาแรง — สัดส่วนนักการตลาดที่บอกว่า long-form ให้ ROI สูงสุด 14% → 29% ใน 1 ปี ⚠️ *(HubSpot State of Marketing 2026 ผ่านตัวกลาง)*; 57%+ ของ watch time มาจากคลิป 20 นาที+ |
| **Short-form video** | ยังเป็นเครื่องยนต์ organic แรงสุด — TikTok Shop $15B ในสหรัฐปี 2025 ✅, social commerce สหรัฐคาดเกิน $100B ปี 2026 ✅ วิดีโอที่มีภาพใช้งานจริง 5 วิ+ convert สูงกว่า 2-3 เท่า ⚠️ |
| **Newsletter/Email** | benchmark 2026: open 19.21%, CTR 2.44%, unsub 0.89%, bounce 2.48% ⚠️ (**อย่าเชื่อ open rate — Apple MPP ดันขึ้น 15-20pp**) ROI ~$36-40 ต่อ $1 ⚠️ — **beehiiv รายงานเองว่า recommendation network สร้าง 67% ของ subscriber ใหม่ให้ publisher อันดับต้น และจ่ายให้ publisher รวม $1M+/เดือน** ✅ |
| **Newsletter sponsorship CPM** | consumer/lifestyle $25-55, **tech/dev $60-150**, B2B SaaS $90-180, finance $70-180 ⚠️ — ตลาดกำลังย้ายจาก CPM ไป CPA |
| **Pinterest** | ยังแข็งแรงมากสำหรับ template/printable/planner — pin สะสม traffic ยาว (evergreen) ⚠️ |
| **Reddit** | กฎ 90/10 (มีส่วนร่วมจริง 90% โปรโมท ≤10%), r/SideProject (300K) เปิดกว้างสุด — ⚠️ Reddit ปิดประตู API เชิงพาณิชย์: **GummySearch (founder ใช้ 135K คน) ปิดตัว พ.ย. 2025** |
| **Product Hunt** | คุ้มในแง่ credibility + branded search ระยะยาว ไม่ใช่ยอดขายวันนั้น: top 3 = 5,000-15,000 visitor, top 10 = 1,000-3,000, **หลุด top 10 = <500** ⚠️ ลิงก์เป็น nofollow |
| **Hacker News (Show HN)** | variance สูงมาก: หน้าแรก = 5,000-30,000 uniques/24 ชม. แต่ **มีแค่ 2.3% ของโพสต์ที่ขึ้นหน้าแรก** (median score = 2) ต้องได้ 30-50 upvote ใน 1 ชม.แรก, ลงอังคาร-พฤหัส 8-11am ET, conversion 0.5-2% ⚠️ |
| **LinkedIn organic** | โปรไฟล์ส่วนตัวได้ engagement มากกว่าเพจบริษัท ~8 เท่า ⚠️ (methodology ไม่ชัด) |
| **Indie Hackers / Skool / Discord** | IH ยังใช้งานได้ archive สัมภาษณ์มีค่า; Skool มี Stripe + LMS ในตัว; Discord ฟรีแต่ต้องต่อ Whop/Patreon เพื่อ monetize ⚠️ |

---

## 7. Launch Playbook 2026

```
เดือน -3 ถึง -1  สร้าง audience ก่อนมี product
                 • เปิด X account วันแรกที่เริ่มคิด
                 • โพสต์ workflow/บทเรียนเกือบทุกวัน
                 • เข้าไปอยู่ใน community เป้าหมายจริง (ไม่ใช่โผล่มาขาย)
                 • DM 20 คนที่มีปัญหานั้น → ทดสอบ/พรีเซล
       ↓
วัน Launch       ยิงพร้อมกัน 4 ช่อง: Product Hunt + Show HN + X thread + email list/community
                 ⚠️ ตอบทุกคอมเมนต์ใน 60-90 นาทีแรก (algorithm วัดตรงนี้)
       ↓
+1 ถึง +30       • SEO สาย alternative/vs สัปดาห์ละ 1-2 ชิ้น
                 • เก็บ testimonial
                 • มี pixel event 50-100 ครั้ง → เปิด retargeting
                 • ชวนคน engage สูงสุดเป็น affiliate
       ↓
+90              🚦 มี signup จาก "คนนอกเครือข่าย" หรือยัง → scale / kill
```

---

## 8. Affiliate

| แพลตฟอร์ม | คอมมิชชั่น | หมายเหตุ |
|---|---|---|
| **Gumroad** | ตั้งเอง 1-75% | ยืดหยุ่นสุด |
| **Lemon Squeezy** | ตั้งเอง (platform 5%+$0.50) | มีระบบในตัว, Refgrow เป็น 3rd-party ตัวเดียวที่ integrate ตรง |
| **Whop** | Whop หักถึง 30% ถ้าเขาหาลูกค้าให้ | แพงสำหรับ high-ticket |
| **Rewardful** | ตามโปรแกรม, usage-based | เร็วสุดถ้าใช้ Stripe อยู่แล้ว |
| **PartnerStack** | $800+/เดือน + 3-15% | B2B SaaS ใหญ่ |
| **Impact.com** | enterprise pricing | แบรนด์ใหญ่ |

**เรตมาตรฐาน digital product: 20-40%** (ต้นทุนต่อชิ้น = 0)
**[ข้อเท็จจริง]** HeadshotPro ($300K MRR) โตด้วย SEO + affiliate เป็นหลัก ไม่ใช่ paid ads

---

## 9. ตายแล้วปี 2026

| ตายแล้ว | หลักฐาน |
|---|---|
| Cold email แบบยิงหว่าน | reply rate ทั้งระบบ 8.5% → **3.43%** (2019→2026) ✅ *(Instantly, vendor-primary)* — คนที่ทำเจาะจงจริงยังได้ 10-18% |
| ซื้อ guest post ราคาถูก | โมเดล $50/โพสต์ + anchor keyword โดนลงโทษ ⚠️ |
| Hashtag บน Instagram | IG ลดความสำคัญเอง + ตัดจาก 30 เหลือ 5 ⚠️ |
| Organic reach ของ FB Page | **<2%** (จาก 16% ปี 2012) ⚠️ |
| เลือก audience ละเอียดบน Meta | ถูกยุบเข้า Advantage+ โดยตัวผลิตภัณฑ์ ⚠️ |
| คอนเทนต์ how-to ทั่วไปเพื่อ SEO | 74% ของ query เชิงข้อมูล zero-click ✅ |
| เครื่องมือโตที่พึ่ง Reddit API ถูก ๆ | GummySearch ปิดตัว พ.ย. 2025 ⚠️ |
