# Demand Discovery Toolkit — วัดความต้องการยังไงในปี 2026

| | |
|---|---|
| วันที่ | 2026-07-26 |
| ที่มา | **กอบกู้จากรอบ recon ที่บานปลาย** (ดู [ADR-0003](../decisions/0003-agent-fanout-control.md)) — งานเสร็จแล้วและมี URL ครบ จึงเก็บไว้แทนที่จะทิ้ง |
| Stage | 0-1 |
| ⚠️ | บางส่วนได้มาตอนโควตา WebSearch หมดแล้ว — ระบุไว้ในแต่ละหัวข้อ |

> ปิดช่องว่างที่ red-team ชี้ว่า *"แผนที่ตลาดมีคำว่า search volume / โฆษณา / CAC รวมกัน 0 ครั้ง"*

---

## 1. เครื่องมือดู search volume

| เครื่องมือ | วัดอะไร | ราคา 2026 | เชื่อได้แค่ไหน |
|---|---|---|---|
| **Google Keyword Planner** | keyword ideas + forecast | **ฟรี** (ต้องมีบัญชี Ads ไม่ต้องยิงเงิน) | บัญชีที่ไม่ยิงแอดเห็นแค่ช่วงกว้าง (10 / 100 / 1K-10K) — **มีทางลัด: saved plan → Forecast tab → ลาก max-CPC slider → อ่านคอลัมน์ Impressions จะเห็นตัวเลขจริงฟรี** |
| **Google Trends** | ความสนใจเชิงเปรียบเทียบ 0-100 **ไม่ใช่ปริมาณจริง** | ฟรี | ✅ ดีสำหรับดูทิศทาง Google ยืนยันเองว่าเป็นค่า normalize |
| **Bing Webmaster Tools** | impression จากข้อมูล Bing เอง | **ฟรี** (ต้อง verify เว็บ) | ✅ ข้อมูล first-party จริง แต่สะท้อนแค่ส่วนแบ่งของ Bing |
| **Ahrefs** | volume, KD, backlink | Starter $29/mo · Lite $129/mo | ประมาณการจาก clickstream — อนุรักษ์นิยมกว่า Semrush |
| **Semrush** | volume, position tracking | ถูกสุด $139.95/mo | ประมาณการ ตัวเลขมักสูงกว่า Ahrefs |
| **Keywords Everywhere** | overlay บน Google/YouTube/Amazon | $84/ปี (100K credits) **ตัด free tier แล้ว** | ดีเมื่อเทียบราคา |
| **Ubersuggest** | volume + audit | ~$29/mo | ⚠️ ถูกวิจารณ์เรื่องความแม่นซ้ำ ๆ |
| **AlsoAsked / AnswerThePublic** | คำถามที่คนถามจริง | $12-47 / $20-199 | ยังใช้ได้ |

### 🔴 ปัญหาใหญ่: search volume ไม่ได้แปลว่า demand อีกแล้ว

| ข้อมูล | ตัวเลข |
|---|---|
| SparkToro (Datos, ก.ค. 2024) | zero-click สหรัฐฯ **58.5%** / EU 59.7% |
| SparkToro (Similarweb, มิ.ย. 2026) | zero-click สหรัฐฯ **68.01%** (ม.ค.-เม.ย. 2026) — พุ่ง 7.5 จุดใน 2 ปี **เร็วที่สุดในรอบ 10 ปี** |
| งานทดลอง randomized (ISB + CMU Heinz, SSRN เม.ย./มิ.ย. 2026) | AI Overview ตัด outbound click **39.8%** และดัน zero-click **+34.5%** |
| Ahrefs | CTR อันดับ 1 หายไป 34.5% (เม.ย. 2025) → **~58%** (ข้อมูล ธ.ค. 2025) |

**สิ่งที่คนทำจริงเปลี่ยนไปใช้แทน:**
- **Share of search** — ส่วนแบ่ง branded search เทียบทั้งหมวด (Search Engine Land, ธ.ค. 2025)
- **Google Search Console impressions** — เป็นสัญญาณ *supply* ไม่ใช่ *demand*
- **ขูด autocomplete** จาก Amazon / Etsy / TikTok Shop — สัญญาณ intent ดิบที่สุด

---

## 2. ดูว่าอะไรขายจริงบน marketplace

| เครื่องมือ | ข้อมูลจริงหรือประมาณ | ราคา | หมายเหตุ |
|---|---|---|---|
| **Chrome Web Store (หน้า listing)** | ✅ **ข้อมูลจริง** — โชว์ user count ตรง ๆ (เช่น AdBlock Plus "36,000,000 users") | ฟรี | 🥇 **สัญญาณจริงที่แข็งที่สุดในตารางนี้** |
| **Shopify App Store** | รีวิวจริง แต่ไม่โชว์ยอดติดตั้ง · 3rd-party (StoreLeads) ตรวจ storefront จริงได้ % adoption | ฟรี-หลากหลาย | ดีทั้งคู่ |
| **Unity Asset Store** | ranking จากยอดขายจริง (ไม่มีตัวเลขสัมบูรณ์) | ฟรี | ✅ สัญญาณเชิงเปรียบเทียบดี |
| **eRank / EverBee / Alura / Sale Samurai** (Etsy) | ❌ **ประมาณการทั้งหมด** — Etsy API ไม่เปิดยอดขายคู่แข่ง | $6-30/mo | สูตรร่วม: **รีวิว × 10-25** (digital 25-50) เพราะมีคนรีวิวแค่ 10-20% |
| **Publisher Rocket / KDSpy** (KDP) | keyword จริง / ยอดขายประมาณจาก BSR | $199 / $79 ขายขาด | ตัวเลขยอดขายเป็นทิศทางเท่านั้น |
| **Sensor Tower** (รวม data.ai แล้ว) | ประมาณการเชิงโมเดล | ~$500/mo ขึ้นไป มัธยฐาน **$74,415/ปี** | แพงมาก กล่องดำ |
| **AppFigures** | รีวิว/อันดับจริง + ยอดโหลดประมาณ | ฟรี-$599/mo | โปร่งใสกว่า Sensor Tower |
| **Gumroad Discover / Creative Market** | ❌ ไม่เปิดยอดขายเลย เรียงตาม algorithm ทึบ | ฟรี | ใช้ประเมินขนาดไม่ได้ |

---

## 3. ขุดเสียงคนบ่นหลัง Reddit ปิดประตู

### 🔴 สถานะ Reddit ปี 2026

| ทาง | สถานะ |
|---|---|
| **Reddit API เชิงพาณิชย์** | **~$12,000/เดือน** ต่อ 50M call · ไม่มีแพ็กเล็ก |
| **Reddit API ฟรี** | non-commercial เท่านั้น 100 req/min · **ปิดสมัครเองแล้วปลายปี 2025** ต้องขออนุมัติ 2-4 สัปดาห์ ห้ามใช้เชิงพาณิชย์ |
| **GummySearch** | ❌ **ปิดตัว 30 พ.ย. 2025** — ประกาศเองว่า *"shutting down to comply with Reddit's API policies, which forbid commercial applications"* |
| **จาก environment นี้** | ❌ **บล็อก 403 ทั้ง reddit.com และ old.reddit.com** และ WebSearch ไม่คืนผล Reddit เลย |

### ทางที่ยังใช้ได้

| เครื่องมือ | ใช้ทำอะไร | ราคา |
|---|---|---|
| **Google/Bing `site:reddit.com`** | ค้น Reddit ผ่าน search engine — **ครบกว่า search ในตัว Reddit เอง** | ฟรี |
| **F5Bot** | แจ้งเตือนอีเมลเมื่อมีคนพูดถึง keyword บน Reddit/HN/Lobsters (ตั้งแต่ 2017) | ฟรี + tier เสียเงิน |
| **PullPush.io / Arctic-Shift** | archive แบบ Pushshift — ค้นย้อนหลังได้ ได้ text เต็มพร้อม permalink | ฟรี (rate limit) |
| **Capterra / Sitejabber / Trustpilot** | รีวิว 1-2 ดาวของคู่แข่ง — **fetch ตรงได้ผลดี** (G2 มักบล็อก 403) | ฟรี |
| **App Store / Google Play reviews** | รีวิวจริงพร้อมชื่อผู้เขียน — **fetch ตรงได้** | ฟรี |
| **Stack Exchange Data Explorer** | query ข้อมูล SE ทางการ | ฟรี |
| **AppFollow / Helium 10 Review Insights** | รวมรีวิว + sentiment | $99-111/mo |
| Discord / Facebook Groups | ❌ **ไม่มีวิธีค้นเนื้อหาจริง** — Discord discovery ต้องมี 1,000+ สมาชิก, FB ให้คนนอกเห็นแค่ชื่อกลุ่ม | — |

---

## 4. ดูว่าคนจ่ายอะไรอยู่แล้ว

| แหล่ง | ข้อมูลจริงไหม | หมายเหตุ |
|---|---|---|
| **ClickBank Gravity** | ✅ metric จริง (จำนวน affiliate ที่ได้คอมใน 12 สัปดาห์) | เอียงไปทางอาหารเสริม/สุขภาพ · ปั่นได้ |
| **Patreon / Graphtreon** | ✅ คำนวณจาก tier × จำนวน patron ที่เปิดเผย | ตัวอย่างจริง: **Czepeku 110,964 members, $77,050 ต่อ map pack** |
| **Steam / SteamDB** | อันดับจริง ไม่มีตัวเลข · สูตรที่ใช้กัน **รีวิว × 30-40** หรือ peak CCU × 8-14 | ±30-50% |
| **Product Hunt leaderboard** | upvote จริง | ⚠️ **upvote = vanity metric** · Golden Kitty ยกเลิก 17 พ.ย. 2025 เปลี่ยนเป็น Orbit Awards ที่วัด traction |
| **Digistore24 Top Offers** | รายเดือน แต่เป็น**บทความคัดเอง ไม่ใช่ ranking จริง** | ความแม่นต่ำ |
| **itch.io / AppSumo** | อันดับ/สถานะ sold-out เท่านั้น | ไม่มีตัวเลข |
| **Hotmart ranking สาธารณะ** | ❌ ไม่มี | — |

---

## 5. ทดสอบ demand — ถูกสุดไปแพงสุด

| วิธี | ต้นทุน | เร็วแค่ไหน | เกณฑ์ที่แปลว่า "มีจริง" |
|---|---|---|---|
| **Concierge (ทำมือให้ลูกค้าก่อน)** | $0 + เวลา | ทันที | 🥇 ทดสอบทั้งความยอมจ่าย + ประสบการณ์จริง พร้อมกัน โดยไม่ต้องสร้าง |
| **โพสต์ในคอมมูนิตี้** | $0 | ชั่วโมง-วัน | **คอมเมนต์สำคัญกว่า upvote** · ธงแดง: upvote เยอะแต่ไม่มีใครเล่าว่าตอนนี้แก้ยังไง |
| **DM / cold outreach** | $0 | วัน | cold email เฉลี่ยทั้งระบบ **3.43%** · B2B ที่ดี 5-10% · LinkedIn DM ~10% · **cold DM: >25% ดี, <10% อ่อน** |
| **Pre-sell** | $0 + ค่าธรรมเนียม | 1-2 สัปดาห์ | มัดจำ **$1-10 ก็พอกรอง** — "ควักบัตรแม้แต่ $1 = intent จริง" · ตั้งเกณฑ์จำนวนออเดอร์ล่วงหน้า ไม่ถึงก็คืนเงินทั้งหมด |
| **Waitlist** | $0-หลักร้อย | วัน-สัปดาห์ | median **~11%** ของ visitor · เก่ง 20-40% · **waitlist → ลูกค้าจ่ายจริง >20% = สัญญาณ PMF แรง** |
| **Fake-door landing page** | โดเมน $10-15/ปี + Carrd $19/ปี (ทั้ง sprint มักต่ำกว่า $200) | วัน | median ทุกอุตสาหกรรม **6.6%** · 75th percentile 11.4% · **>10% จาก traffic เย็น = สนใจจริง** · ⚠️ **ต้องมี 300-500 visitor ที่ตรงกลุ่มก่อนสรุป** |
| **ยิงแอดทดสอบ** | Meta $50-150/วัน · Google CPC เฉลี่ย **$2.96** (Q1 2026, ขึ้นจาก $2.64) · TikTok €300-500 | วัน | **100 คลิก = ขั้นต่ำที่เห็น pattern · ~2,000 คลิกถึงจะมีนัยสำคัญทางสถิติจริง** |

---

## 6. เรื่องของฟรีและของเถื่อน

**คู่แข่งอันดับ 1 ของ digital product ส่วนใหญ่คือ YouTube ฟรี หรือไฟล์เถื่อนใน Telegram/Discord**

| ข้อมูล | ตัวเลข |
|---|---|
| MUSO 2024 | เข้าเว็บละเมิดลิขสิทธิ์ **216.3 พันล้านครั้ง** (-5.7% YoY) |
| แยกหมวด | **Publishing 66.4 พันล้าน (+4.3%) — หมวดเดียวที่โต** แต่ ~70% เป็นมังงะ · TV 44.6% ของทั้งหมด (-6.8%) · Software -2.1% · หนัง -18% · เพลง -18.6% |
| BSA/Revenera | ซอฟต์แวร์ไม่มีสิทธิ์ใช้งาน ~**$46B/ปี** · ตลาดเกิดใหม่อัตราละเมิด ~57% |
| Google Transparency Report | ⚠️ **หยุดอัปเดตตั้งแต่กลางเดือน เม.ย.** หลังทำต่อเนื่องมา 10 ปี — ใช้เป็น proxy ปี 2026 ไม่ได้แล้ว |
| ❓ ไม่มี tracker | **คอร์ส · Notion template · preset/LUT · ฟอนต์** — ไม่มีใครวัดเลย = จุดบอดจริง |

**สิ่งที่คนทำจริงทำ** (จาก Indie Hackers): ไม่มีใครไปดูสถิติ piracy — เขา **pre-sell**, ใส่ส่วนที่ลอกไม่ได้ (cohort/live), และ **ค้นชื่อ product ตัวเอง + "free/nulled/download" ก่อน launch** แล้วมองว่าเป็นความเสี่ยงเชิงราคา ไม่ใช่ตัวเลขที่ต้องวัด

---

## 7. ตัวอย่าง buyer voice ที่ได้มาจริง (2 segment)

### สาย TTRPG / battlemap
- **เงินอยู่ที่ Patreon ไม่ใช่ marketplace** — Czepeku **110,964 members, $77,050/map pack** · Forgotten Adventures 47,325 · Tom Cartos 36,675 · **top-10 ขายดีของ DriveThruRPG ปี 2024 ไม่มี map/token/VTT asset เลยแม้แต่ชิ้นเดียว**
- **ความเจ็บอันดับ 1 ไม่ใช่ราคา แต่คือการค้นหา** — *"their search is terrible"* · *"mostly results are battleships"* (หาเรือที่อยู่อาศัยแต่เจอแต่เรือรบ) · *"I saw it once and can't find it again"*
- **billing แบบ per-creation ทำให้เกิดพฤติกรรม "สมัคร 1 เดือน โหลดทั้งคลัง แล้วยกเลิก"** — คนซื้อพูดเองตรง ๆ
- ของฟรีมหาศาล: Dyson Logos **1,601 แผนที่ฟรี** · search engine รวม 5,000 แผนที่ฟรีจาก Discord · Forgotten Adventures แจก token SRD ฟรีหมด
- ฤดูกาล: **Black Friday/Cyber Monday + GM's Day (มี.ค.)** = ช่วงซื้อ · **20 ธ.ค. - 2 ม.ค. = ช่วงแจกฟรี** (creator ใช้หาสมาชิก ไม่ใช่ขาย)

### สายเทมเพลตธุรกิจ (Notion/Canva/สเปรดชีต)
- **ปัญหาที่แท้จริงคือคนเลิกใช้ ไม่ใช่ราคา** — *"I've downloaded like 37 Notion templates... Now I actively use zero of them. I tried. I promise."* · *"it became work to keep up with it"* · *"I can't be clicking 14 layers deep to add a thought"*
- **เพดานความยอมจ่ายต่ำและพูดออกมาตรง ๆ** — *"nothing can make a template worth that much"* ($199) · *"no reason to charge more than $10 for any digital product"* · คนหนึ่งบอกเพดานตัวเองที่ **€20**
- **ช่องว่างที่คนซื้อพูดเอง**: *"free templates... lack a feature I need"* แต่ *"paid Notion templates waay too overpriced"* → **ตลาดมีแต่สองปลาย ไม่มีตรงกลาง**
- **คนขอสิ่งของเฉพาะอาชีพ ไม่ได้ขอ "template"** — travel proposal, contractor quote, weekly delivery sheet, cash-flow forecast · และมักขอให้ **แชร์ฟรี** ไม่ใช่คิดจะซื้อ
- Supply: Notion marketplace **30,000+ templates, 348 หมวด** — หน้า Marketing (4,647) และ Social Media (1,738) **ทุกตัวที่เห็นเป็นของฟรี** · Gumroad "notion template" **19,737 ชิ้น**
- 🎯 **ช่องเดียวที่นับแล้วบาง: bookkeeping template = 98 ชิ้นบน Gumroad** (เทียบ notion template 19,737) และ r/Bookkeeping มี 77,112 สมาชิก
- **Etsy ไม่มีที่ให้คนซื้อคุยกันเลย** — forum ทางการเป็นของผู้ขายล้วน
