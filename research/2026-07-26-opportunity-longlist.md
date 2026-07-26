# Longlist โอกาส — 30 รายการ (Stage 1)

| | |
|---|---|
| วันที่ | 2026-07-26 |
| Agent | niche-scout ×3 (Sonnet) แบ่งอาณาเขตไม่ทับกัน |
| Stage | 1 — SCOUT |
| สถานะ | ร่าง · **ยังไม่ผ่าน red-team · ยังไม่ให้คะแนน** |

> **กฎที่บังคับกับทุกแถว:** ต้องมี (1) คำพูดจริงของคนซื้อพร้อม URL (2) หลักฐานว่ามีคนจ่ายอยู่แล้ว (3) **supply count ที่นับได้** (4) ทางเลือกฟรี (5) ประเมิน AI durability
> **ไม่มี supply count = ไม่ได้เข้าลิสต์** — กฎข้อ 11 หลังจากรอบก่อนเคยเรียกตลาดว่า "ยังไม่อิ่มตัว" โดยไม่เคยนับ แล้วผิดไป 266,000 listing

---

## 🔴 ข้อจำกัดของงานรอบนี้ — อ่านก่อนใช้ข้อมูล

**1. Reddit เข้าไม่ได้เลยทั้ง session** — scout ทั้ง 3 ตัวรายงานตรงกันว่า `reddit.com` และ `old.reddit.com` ถูกบล็อก (403) และ WebSearch ก็ไม่คืนผลลัพธ์ Reddit เลยแม้ลอง query ต่างกัน ~15 แบบ
→ **แหล่งที่ควรเป็นแหล่งหลักของงานนี้ ใช้ไม่ได้เลย** ทุก quote ในรายงานนี้มาจาก Capterra / App Store / Google Play / Trustpilot / Sitejabber / Etsy / forum เฉพาะทาง แทน

**2. Etsy บล็อก 403 ทุกครั้ง** — ตัวเลข "5,000+" คือ**เพดานที่ Etsy แสดง** ไม่ใช่จำนวนจริง ของจริงอาจสูงกว่ามาก

**3. โควตา WebSearch หมดอีกครั้ง** ทั้ง 3 ตัว → ตัวเลขบางช่อง (ราคา baby shower bundle, wedding seating chart) ยืนยันไม่ทัน ระบุไว้แล้วในตาราง

---

## 🅐 ฝั่งผู้ซื้อสาย Technical (9 โอกาส)

| # | โอกาส | คำพูดจริงของคนซื้อ | ใครจ่าย เท่าไหร่ | Supply | ทางเลือกฟรี | AI ลอกได้ไหม |
|---|---|---|---|---|---|---|
| A1 | ตรวจความปลอดภัยแอปที่ "vibe code" ก่อนขึ้น production | audit 50 แอป: **RLS เปิดหลุด 44/50 (88%)**, key หลุดใน `NEXT_PUBLIC_*` 39/50 — *"vibe coding is magic until it isn't"* [dev.to](https://dev.to/rishabh_kumar_6d865c83a4d/i-audited-50-vibe-coded-apps-heres-what-broke-1pb6) | Sherlock Forensics เริ่ม **$1,500 CAD**/ครั้ง · Beesoul/Varyence **$2,500** | ≥9 เจ้า + freelancer Fiverr | checklist 47 ข้อฟรีบน GitHub | 🔴 สูง — moat คือ trust/liability ไม่ใช่ทักษะ |
| A2 | ทางเลือกถูกกว่า dbt Cloud หลังเปลี่ยนราคาเป็นตาม model-run | *"paying $820 solely to execute regular DBT commands seems excessive"* — คำนวณจริง $720/เดือน [substack](https://juhache.substack.com/p/dbt-labs-rate-increase) | ทีมที่ใช้ dbt Cloud Team ($100/mo + usage) | 2-3 ทางจริงจัง (SQLMesh, dbt Core+Dagster) | dbt Core (OSS เต็มรูป) | 🟢 ต่ำ-กลาง |
| A3 | Incident/on-call สำหรับทีมเล็ก | *"It was cost prohibitive for our team and really only solve one problem"* — System Engineer [Capterra](https://www.capterra.com/p/125693/PagerDuty/reviews/) | PagerDuty **$21-41+/user/เดือน** | ≥8 เจ้า | Better Stack free, Grafana OnCall | 🟢 ต่ำ — ต้อง page มือถือได้จริง |
| A4 | Auth ที่ราคาไม่กระโดดตอน scale | *"they could not offer a startup-friendly model where we could grow with the usage"* — founder [G2](https://www.g2.com/products/auth0/reviews?qs=pros-and-cons) | Auth0 **$525/เดือน**หลังพ้น 7.5K MAU | ≥7 เจ้า | Firebase ฟรีถึง 50K MAU, Keycloak | 🟢 ต่ำ (security-critical) |
| A5 | Terraform drift detection โดยไม่ต้องขึ้น TF Cloud | *"A sea of yellow '~'... one of the most annoying things a Terraform user can see"* [substack](https://devopsdaily.substack.com/p/i-built-a-terraform-drift-tool-to) | ทีมที่จ่าย TF Cloud tier ที่มี drift detection | ≥6 โปรเจกต์ **ไม่มีเจ้าไหนชนะ** | driftctl (เลิกดูแลแล้ว) | 🔴 กลาง-สูง |
| A6 | API client ทีมที่ไม่คิด per-seat | *"Paying for a full team plan made less sense than finding a free alternative"* [techbloat](https://www.techbloat.com/postman-ends-free-team-plans-in-march-2026-here-is-the-free-alternative-i-switched-to.html) | Postman Team **$19/user/เดือน** (ตัด free team collab มี.ค. 2026) | ≥6 เจ้า | **Bruno — OSS ชนะไปแล้ว** | 🔴 สูง — พิสูจน์แล้วว่า OSS แก้ฟรีได้ |
| A7 | Hard spend cap / circuit-breaker สำหรับ PaaS | *"$22,000 surprise bill was not forgiven by Vercel... offer a 25% discount"* [HN](https://news.ycombinator.com/item?id=32596367) | บิลตาม usage ไม่มีเพดาน | PaaS ที่ได้อานิสงส์ 4 เจ้า · Vantage/Infracost มีแต่ไม่ hard-cap | Coolify (self-host) | 🟢 ต่ำ-กลาง — ต้องอยู่ใน billing path |
| A8 | CI runner macOS/iOS ถูกกว่า GitHub-hosted | *"GitHub actions Mac CI minutes are so expensive so we run our own setup"* · *"build minutes cost 10x as much as Linux"* [HN](https://hn.algolia.com/api/v1/search?query=GitHub%20Actions%20minutes%20expensive&tags=comment) | GitHub คิด macOS ~10 เท่าของ Linux | 4 เจ้ามี traction จริง (WarpBuild 154pts, Depot 117pts) | self-host Mac mini | 🟢 ต่ำ — ดูแล fleet เครื่องจริง |
| A9 | คุมงบ AI coding agent | *"I consumed $50K worth of Claude Code tokens on a $200 plan"* [dev.to](https://dev.to/markliuyuxiang/i-consumed-50k-worth-of-claude-code-tokens-on-a-200-plan-should-i-be-blamed-4176) · *"spent $131 on Cursor... 700% increase"* | ⚠️ **ยังไม่มีหลักฐานว่ามีคนจ่าย 3rd-party** — ทุกคนแจกฟรี | ฟรี/OSS ≥8 ตัว · **Cursor ออก native cap เอง มิ.ย. 2026** | ccusage (npm ฟรี) | 🔴 สูง — จุดอ่อนที่สุดในลิสต์ |

---

## 🅑 ฝั่งผู้ซื้อสายกระบวนการธุรกิจ (10 โอกาส)

| # | โอกาส | คำพูดจริงของคนซื้อ | ใครจ่าย เท่าไหร่ | Supply | ตอนนี้ใช้อะไร | AI ลอกได้ไหม |
|---|---|---|---|---|---|---|
| B1 | จับ error/reconciliation ของ AP automation | *"BILL is a nice looking fintech product with infinite headaches... Expect to spend **10-20% of your work week** with BILL support"* — Accounting Clerk [Capterra](https://www.capterra.com/p/166559/BILL/reviews/) | Bill.com **$45-79/user/mo** + ค่าธุรกรรม | หลักสิบ+ (นับตรงไม่ได้ G2 บล็อก) | Bill.com + เช็คซ้ำมือใน Excel | 🟡 กลาง |
| B2 | co-pilot จับ error ของ QuickBooks Online | *"they told us it was all good and then lock us out of payroll"* — Julie F., Office Manager สาย construction [Capterra](https://www.capterra.com/p/190778/QuickBooks-Online/reviews/) | QBO **$35-235/เดือน** แทบไม่มีทางเลือก | 183 products (Capterra) | QBO คือ default | 🟢 ต่ำสำหรับ replace / 🔴 สูงสำหรับ layer |
| B3 | transaction-compliance สำหรับโบรกเกอร์อสังหาเล็ก | *"This company does not care or value smaller brokerages"* — Kevin F., Owner [Capterra](https://www.capterra.com/p/172896/SkySlope/reviews/) | ~**$400-600+/office/ปี** auto-renew ล็อก 60 วัน | **115 products** — อิ่มตัว | dotloop/SkySlope หรือ DocuSign+อีเมล | 🟡 กลาง (e-sign/MLS เป็น moat) |
| B4 | project/change-order สำหรับผู้รับเหมาที่ Procore แพงเกิน | sales บอกบริษัท remodel 6 คนตรง ๆ ว่าสินค้า *"wasn't designed for companies their size"* [Capterra](https://www.capterra.com/p/56250/Procore/reviews/) | รายใหญ่จ่าย Procore **$10K-60K+/ปี** — รายเล็กถูกเมิน | **820-986 products** | Excel + QuickBooks + โฟลเดอร์กระดาษ | 🟡 กลาง-สูง |
| B5 | ลด manual data entry ในระบบ inventory | *"Reporting can also be somewhat limited or difficult to customize"* — Jaisson M., Warehouse Manager (11-50 คน) [Capterra](https://www.capterra.com/p/123794/Fishbowl/reviews/) | Fishbowl หลักพัน USD + subscription | **933 products** — อิ่มตัวสุดในลิสต์ | Fishbowl + Excel ปะรู | 🟡 กลาง |
| B6 | trust-accounting/owner reporting ของ property mgmt | *"Customer support is awful, often taking weeks to reach a live person"* · *"100% of our business does not fit into their AppFolio system"* [Capterra](https://www.capterra.com/p/92228/AppFolio-Property-Manager/reviews/) | AppFolio ~**$1.50-3/unit/mo**, ขั้นต่ำ ~$400+/mo | 10+ ราย (ไม่ได้นับตรง) | AppFolio + Excel เสริม | 🟢 ต่ำ-กลาง (ต้องแม่นระดับ audit) |
| B7 | eligibility-check/front-office คลินิกเล็ก | *"one the most expensive VOIP services you will find out there"* — Practice Manager สัตวแพทย์ [Capterra](https://www.capterra.com/p/141842/Weave/reviews/) · **55% ของคลินิกทันตกรรมใช้เวลา verify ประกัน 6+ ชม./สัปดาห์** | Weave/Dentrix รายเดือน | **221 products** | โทรหาประกันเอง | 🔴 กลาง-สูง (มี AI-native แข่งแล้ว) |
| B8 | prior-authorization สำหรับ practice เล็ก | ⚠️ quote ที่มีเป็น **testimonial จาก vendor เอง ไม่ใช่รีวิวอิสระ** · **35% ของ practice จ้างคนเฉพาะทำ PA, เฉลี่ย 12-16 ชม./สัปดาห์/แพทย์ (AMA)** | จ้างพนักงานเฉพาะ | หลายสิบราย + AI startup ทุนหนา | โทร/แฟกซ์หาประกัน | 🔴 สูง — ชนกับ startup ทุนหนา |
| B9 | ระบบไล่ทวงเอกสารจากลูกค้าที่ไม่ยอมใช้ portal | หัวข้อจริง: *"Why clients ignore the portal you pay for"* [AccountingWEB](https://www.accountingweb.co.uk/community/industry-insights/why-clients-ignore-the-portal-you-pay-for) ⚠️ paraphrase จาก snippet เพจบล็อก 403 | หลายสำนักงานจ่าย portal อยู่แล้วแต่ลูกค้าไม่ใช้ | 183 products อ้างว่าแก้แล้ว | อีเมล + portal ที่ลูกค้าเมิน + โทรตาม | 🔴 สูงเชิงเทคนิค — **แต่ปัญหาจริงคือพฤติกรรมลูกค้า ไม่ใช่ tech** |
| B10 | ไล่ COI/vendor-compliance | *"Parts of the platform are slow and clunky. About 10 seconds of waiting every time you filter"* — EHS Leader [Capterra](https://www.capterra.com/p/177871/Contractor-Compliance/reviews/) · **อุตสาหกรรมเสียเวลาไล่ COI 8-13 ชม./สัปดาห์** | myCOI/SmartCompliance รายเดือน | **~7 ราย** ← **supply count ต่ำที่สุดในทั้ง 30 รายการ** | Excel ไล่วันหมดอายุ + อีเมลทวง | 🔴 สูง — OCR วันหมดอายุทำได้ แต่ incumbent ทำแล้ว |

---

## 🅒 ฝั่งผู้บริโภค / งานอดิเรก / ครู (11 โอกาส)

| # | โอกาส | คำพูดจริงของคนซื้อ | ใครจ่าย เท่าไหร่ | Supply | ทางเลือกฟรี/เถื่อน | ฤดูกาล |
|---|---|---|---|---|---|---|
| C1 | แอปงานบ้าน/ค่าขนมเด็ก | *"there's realistically nothing useful without having to pay"* · *"a better history option to review what's been completed"* [App Store](https://apps.apple.com/us/app/neat-kid-daily-kids-chore-app/id6480269902) | NeatKid $4.99 · S'moresUp ~$80/ปี · Acorns Early $5-10/เดือน | ≥16 แอป | ไวท์บอร์ด/สติกเกอร์กระดาษ | ม.ค. + ส.ค.-ก.ย. |
| C2 | จัดแผนการเรียน homeschool หลายลูก | *"I kept losing important papers and forgetting dates"* [homeschoolplanet](https://homeschoolplanet.com/homeschool-planning-for-the-disorganized-mom/) | Planner $3-18 (Gumroad/Etsy) | Etsy **5,000+** (เพดานแสดงผล) | planner ฟรีจากบล็อก/Pinterest | ก.ค.-ก.ย. + ม.ค. |
| C3 | ซอฟต์แวร์ลำดับวงศ์ตระกูล — ล็อกฟีเจอร์หลังจ่าย | *"Need subscription to view their hints!... HINTS ARE USELESS IF I CANNOT ACCESS THEM!"* [Sitejabber](https://www.sitejabber.com/reviews/rootsmagic.com) (2.2★) | Ancestry รายเดือน · RootsMagic ขายขาด | หลายสิบ (alternativeto) + เทมเพลตผัง Etsy 5,000+ | **FamilySearch ฟรีทั้งหมด**, Gramps | ต.ค. + พ.ย.-ธ.ค. |
| C4 | ภาพวาด/ของที่ระลึกสัตว์เลี้ยง | *"The quality and detail is amazing... brought tears to our eyes when we opened it"* [Etsy](https://www.etsy.com/shop/PetPortraitGalaxy) | **$19.99 (digital)** ถึง $300+ | Etsy 5,000+ | ฟิลเตอร์แปลงภาพฟรีในมือถือ | พ.ย.-ธ.ค. + ตอนสัตว์ตาย (ไม่มีฤดู) |
| C5 | เกมงาน baby shower | *"So happy I found these templates! Saved me a lot of time."* [Etsy](https://www.etsy.com/listing/1045589916) · อีกชิ้น **9,100 รีวิว 4.8★** | ⚠️ ราคายืนยันไม่ทัน (โควตาหมด) | Etsy 5,000+ | เว็บ free printable จำนวนมาก | มี.ค.-ส.ค. |
| C6 | ผังที่นั่งงานแต่งที่เปลี่ยนกะทันหัน | seller *"extremely helpful during a 911 emergency two days before my wedding"* [Etsy](https://www.etsy.com/market/wedding_seating_chart_template) | ⚠️ ราคายืนยันไม่ทัน | Etsy 5,000+ (หลาย sub-category ก็ 5,000+) | Canva ฟรี, Google Sheets | ก.พ.-เม.ย. + ส.ค.-ก.ย. |
| C7 | แปลงรูปเป็นลาย cross-stitch | *"Pro isn't worth it... it doesn't export a key/legend to tell you the DMC colors"* · *"this random crash and freeze makes the app completely unusable"* [App Store](https://apps.apple.com/us/app/cross-stitch-pattern-maker/id6479785282) (3.5★) | Stitchmate $4-150 · แอปเดี่ยว $1.99-9.99 | ≥12 โปรแกรม | pixel2stitch ฟรี | ต.ค.-ธ.ค. |
| C8 | ครู special ed เก็บข้อมูล IEP | *"Now, my weekends are consumed by paperwork. I spend hours gathering data for progress reports, monitoring goals..."* [NSEA](https://www.nsea.org/paperwork-trap) | IEP goal bank บน TPT **$3-15/ชิ้น** + ซอฟต์แวร์ระดับโรงเรียน | ≥9 สินค้า TPT + ≥5 ซอฟต์แวร์ | Google Sheets ครูทำเอง แจกกันในกลุ่ม | ส.ค.-ก.ย. + เม.ย.-พ.ค. |
| C9 | แอปติดตามทารกที่มี dark pattern | *"Pop-ups to get premium happen multiple times a day and it's super annoying"* + เคสเผลอกดจ่าย **$128** [Google Play](https://play.google.com/store/apps/details?id=com.huckleberry_labs.app) | Huckleberry premium · BabySteps $3-4/เดือน | ≥8 แอป | **Nara (ฟรี ไม่มี paywall)** | ไม่ผูกฤดู (ผูกวันคลอด) |
| C10 | สแกน/จัดคอลเลกชันการ์ด TCG | *"it sucks do not install it and please do not pay for the free trial"* [Google Play](https://play.google.com/store/apps/details?id=com.pokemon.scanner.value) · อีกแอปทำข้อมูลหายหลังลงใหม่ | แอปสแกน $4.99 หรือ subscription | ≥13 แอป | สเปรดชีตเอง, TCGplayer ฟรี | ตอนออกชุดใหม่ + พ.ย.-ธ.ค. |
| C11 | โบสถ์เล็กนำเสนอสไลด์นมัสการ | *"cost prohibitive to some smaller churches... a lean version would be amazing for small churches"* [Capterra](https://www.capterra.com/p/170172/ProPresenter/reviews/) (4.6★, 2,086 รีวิว) | ProPresenter เริ่ม **$29/เดือน** | ≥9 ทางเลือก | **OpenLP, OpenSong (OSS ฟรี)** | พ.ย.-ธ.ค. + ก.พ.-เม.ย. |

---

## โอกาสที่ scout เกือบตัดทิ้งแต่ไม่ตัด

| รายการ | เหตุผลที่เกือบตัด | เหตุผลที่เก็บไว้ |
|---|---|---|
| **A9 คุมงบ AI agent** | ไม่มีใครจ่าย 3rd-party จริง มีแต่แจกฟรี + Cursor แก้เองแล้ว | ตัวเลขเจ็บจริงและสดมาก (ก.ค. 2026) |
| **A5 Terraform drift** | 6 โปรเจกต์ที่เจอ traction ต่ำมาก (1-9 points) อาจแปลว่า**ตลาดเล็กเกินจะจ่าย** | pattern "มีคนพยายามซ้ำไม่เลิก" เองเป็นสัญญาณ pain |
| **Franchise multi-unit consolidation** | หลักฐานทั้งหมดมาจาก**บล็อกของ vendor ที่ขายของนี้เอง** = seller-side noise | pattern สมเหตุสมผล ควรไปยืนยันใน forum จริง |
| **Recruiting scheduling** | สถิติแน่น แต่หาคำพูดคนจริงไม่ได้ + **904 products** อิ่มตัวมาก | — |
| **Cricut/SVG bundle** | เจอลิสติ้งเดียวมี **75,000+ SVG** — ตลาดที่แก้ดีแล้วจนล้น | ⚠️ เก็บเป็น**เคสเตือนใจ** ไม่ใช่โอกาส |
| **C10 TCG scanner** | "กลิ่นอายเทคเกินไป" | คนซื้อจริงคือเด็ก/นักสะสม ไม่ใช่สายเทค |

---

## ช่องว่างที่ยังไม่รู้

**ระดับโครงสร้าง (กระทบงานทั้งหมดข้างหน้า)**
- 🔴 **Reddit เข้าไม่ได้เลย** — subreddit ที่โจทย์ระบุทั้งหมด (r/devops, r/msp, r/Bookkeeping, r/humanresources, r/realtors, r/Teachers, r/genealogy, r/weddingplanning ฯลฯ) ไม่ได้ถูกตรวจแม้แต่ thread เดียว **ต้องหาวิธีอื่นหรืออ่านเองด้วยมือ**
- 🔴 **Etsy บล็อก 403** — supply count ทุกตัวที่เขียน "5,000+" คือเพดานแสดงผล ไม่ใช่ตัวเลขจริง
- 🔴 G2 category page บล็อก 403 → supply count ของ AP automation, property mgmt, prior-auth **ไม่ได้นับจริง** เป็นรายชื่อคู่แข่งที่รู้จัก ไม่ใช่ census
- ไม่ได้แตะ Facebook Group / Discord / YouTube comments เลย

**ระดับรายการ**
- A: SOC2 renewal +30-50%, Retool per-seat ($30-60K/ปี), MSP/RMM per-endpoint, flaky test detection, Snowflake/MongoDB/New Relic/CircleCI cost shock — เจอสัญญาณตอนโควตาหมดพอดี
- B: procurement/vendor-onboarding, logistics/EDI, compliance officer (นอก COI), HR onboarding — ค้นแล้วเจอแต่ vendor content ไม่เจอ buyer complaint
- C: ราคาที่แน่นอนของ C5/C6 · ตลาดนอกภาษาอังกฤษ (ญี่ปุ่น เกาหลี เยอรมัน) ไม่ได้แตะเลย

**Quote ที่อ่อนกว่าแถวอื่น ควร verify ซ้ำก่อนใช้ตัดสินใจ:** B8 (testimonial จาก vendor) · B9 (paraphrase จาก snippet)
