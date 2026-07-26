# 02 — แพลตฟอร์มขายและค่าธรรมเนียม

> เก็บข้อมูล 25 ก.ค. 2026 | ⚠️ ตรวจซ้ำ ต.ค. 2026 — ค่าธรรมเนียมเปลี่ยนบ่อย
> เรื่องข้อจำกัดคนไทยแยกไว้ที่ [05-thailand-constraints.md](05-thailand-constraints.md)

---

## 1. โครงสร้าง 3 ชั้นของการขาย

```
ชั้น 3: MARKETPLACE  — "มีคนเดินผ่านอยู่แล้ว"
        Etsy, Chrome Web Store, Unity Asset Store, Envato
        → ได้ traffic ฟรี แต่ลูกค้าเป็นของแพลตฟอร์ม ไม่ใช่ของเรา

ชั้น 2: STOREFRONT   — "หน้าร้านของเรา"
        Gumroad, Payhip, Polar, Whop, Podia
        → คุมทุกอย่าง แต่ต้องหาคนมาเองทั้งหมด

ชั้น 1: PAYMENT      — "ใครเป็นผู้ขายตามกฎหมาย"
        Stripe (เราเป็นผู้ขาย) vs MoR (เขาเป็นผู้ขายแทนเรา)
        → ชั้นที่คนพลาดกันเยอะสุด
```

---

## 2. Storefront (ชั้น 2)

| แพลตฟอร์ม | ค่าธรรมเนียม | ค่ารายเดือน | MoR | ไทย | เหมาะกับ | หลักฐาน |
|---|---|---|---|---|---|---|
| **Polar.sh** | 5%+$0.50 → 3.4%+$0.30 (tier สูง) | $0-400 | ✅ | ✅ ระบุชัด | dev / SaaS / digital product | ✅ polar.sh/docs/merchant-of-record/fees |
| **Payhip** | ฟรี 5% / $29→2% / $99→0% | $0-99 | 🟡 EU/UK VAT + US sales tax (จาก 1 ก.ค. 2026) ที่เหลือเป็นหน้าที่เรา | ✅ | คนที่ยอดเกิน $1K/เดือน | ✅ payhip.com/payment-gateways |
| ~~**Gumroad**~~ | 10%+$0.50 / 30% ผ่าน Discover | $0 | ✅ | ❌ **ปิดสำหรับโปรเจกต์นี้** — จ่ายผู้ขายไทยผ่าน PayPal เท่านั้น และเจ้าของโปรเจกต์ใช้ PayPal ไม่ได้ (26 ก.ค. 2026) | — | — |
| **Lemon Squeezy** | 5%+$0.50 | $0 | ✅ | ⚠️ | software/SaaS — **กำลังถูกยุบเป็น Stripe Managed Payments** (preview ก.พ. 2026) | ✅ lemonsqueezy.com/blog/2026-update |
| **Whop** | 2.7%+$0.30 + 3% platform ≈ 6-7% (+0.5% tax module) | $0 | ✅ | ⚠️ | community / cohort / membership | ⚠️ |
| **Stan Store** | 0% platform (จ่ายแค่ Stripe ~2.9%+30¢) | $29/$99 | ❌ | ⚠️ | link-in-bio สาย coach | ⚠️ |
| **Ko-fi** | ฟรี 0% tip / 5% shop; Gold 0% | $0/$12 | ❌ | ✅ | tip + ร้านเล็ก | ✅ help.ko-fi.com |
| **Beehiiv** | 0% จาก paid subscription | ฟรี-$290 | ❌ | ⚠️ | newsletter (ถูกกว่า Substack เมื่อยอดเกิน ~$500/เดือน) | ⚠️ |
| **Skool** | Hobby 10% / Pro 2.9% | $9/$99 | ❌ | ⚠️ | คอร์ส + community | ⚠️ |
| **Circle** | 0.5-2% + รายเดือน | $89-419 | ❌ | ⚠️ | community แบรนด์จริงจัง | ⚠️ |
| ~~Podia~~ | — | $42-150 | ❌ | ❌ **ไม่รองรับไทย** | — | ✅ |
| ~~Substack paid~~ | 10% + Stripe | $0 | ❌ | ❌ **ไม่รองรับไทย** | — | ✅ |
| ~~Kajabi~~ | 2.7-2.9%+30¢ | **$179-499** (ขึ้นราคา ม.ค. 2026 ไม่ grandfather → เกิด backlash) | ❌ | ❌ | — | ⚠️ |

---

## 3. Merchant of Record — เปรียบเทียบเฉพาะ

| | ค่าธรรมเนียม | MoR | หมายเหตุ |
|---|---|---|---|
| **Stripe ตรง** | 2.9%+$0.30 US, ~1.5%+€0.25 EU, **+1.5% บัตรต่างประเทศ, +1% FX** ✅ | ❌ | เราคือผู้ขายตามกฎหมาย → ต้องจด VAT เองทุกประเทศ |
| **Polar** | 5%+50¢ → 3.4%+30¢ ✅ | ✅ | ยืนยันรองรับไทย |
| **Paddle** | 5%+$0.50 ✅ | ✅ | ครบเรื่อง invoice/enterprise, custom pricing เมื่อเกิน $50k/เดือน |
| **Lemon Squeezy / Stripe Managed Payments** | 5%+$0.50 ✅ | ✅ | preview ก.พ. 2026 |
| **RevenueCat** | ฟรี <$2,500 MTR แล้ว 1% ของ gross MTR ✅ | ❌ (Apple/Google เป็น MoR ของ IAP) | เป็น layer บน app store ไม่ใช่ storefront |

---

## 4. Marketplace (ชั้น 3)

| Marketplace | ส่วนแบ่ง | สถานะ 2026 | หลักฐาน |
|---|---|---|---|
| **Chrome Web Store** | **0%** ($5 ครั้งเดียวตอนสมัคร) | ไม่มีระบบเก็บเงินในตัว ต้องทำ license เอง | ✅ developer.chrome.com/docs/webstore/register |
| **Shopify App Store** | **0% ของ $1M แรก/ปี** แล้ว 15% | ค่า partner $19 ครั้งเดียว | ✅ shopify.dev/docs/apps/launch/distribution/revenue-share |
| **Framer Marketplace** | **0%** — creator ได้ 100% | template $99-199 | ✅ framer.com/help/articles/how-the-creator-program-works |
| **Webflow Marketplace** | creator ได้ **95%** (ขึ้นจาก 60-80% ต.ค. 2025) | ต้องมี Workspace เสียเงิน ($16+) ถ้าลงเกิน 2 template | ✅ webflow.com/updates/template-creator-enhancements |
| **Fab** (เดิม Unreal Marketplace) | ได้ **88%** | แทนที่ marketplace เก่า ต.ค. 2024 | ✅ |
| **Unity Asset Store** | ได้ **70%** | ราคาขั้นต่ำ $4.99 | ✅ assetstore.unity.com/publishing/publish-and-sell-assets |
| **Ui8** | ได้ ~70% | สมัคร/ถูกเชิญ คัดเข้ม | ⚠️ |
| **Etsy** | $0.20 ลงสินค้า + 6.5% + ~3%+$0.25 (+15%/12% ถ้าเปิด Offsite Ads) | คนไทยรับเงินผ่าน Payoneer | ✅ |
| **Creative Market** | ~50-70% แล้วแต่ exclusivity | ตารางไม่เปิดเผยเต็ม | ⚠️ |
| **Envato / ThemeForest / CodeCanyon** | 12.5-55% → **เหมา 50% ทุกคน 1 ก.ค. 2026** | 🔴 **ปิดรับ author ใหม่ ตั้งแต่ มี.ค. 2026** + Shutterstock เทน้ำหนักไป Elements | ✅ help.author.envato.com |
| **VS Code Marketplace** | ไม่มีระบบเก็บเงิน | 30M+ users, extension แสนกว่าตัว monetize แค่ ~15% | ⚠️ |
| **Gumroad Discover** | **30%** | บังคับถ้าเปิด listing public ไม่มี opt-out | ⚠️ |
| **Notion Template Gallery** | ไม่เก็บเงินให้ — ลิงก์ออกไป checkout ของเรา | ฟรีที่จะ submit รออนุมัติหลายสัปดาห์ | ❓ |
| **Figma Community** | ไม่เปิดเผย | มี free trial ให้ paid plugin | ❓ |
| **AppSumo** | ต่อรองรายดีล ไม่มีเรตตายตัว | traffic ก้อนใหญ่ตอน launch ไม่ใช่ระยะยาว | ⚠️ |

> **[ความเห็น]** Chrome Web Store + Shopify App Store คือ marketplace ที่**ให้ traffic ฟรีโดยแทบไม่หักเงิน** — ถูกพูดถึงน้อยกว่าที่ควรมาก

---

## 5. แพลตฟอร์มใหม่ปี 2025-2026

| แพลตฟอร์ม | สถานะ | หลักฐาน |
|---|---|---|
| **Whop** | ยกเลิกการหัก 30% แบบ marketplace เมื่อ พ.ค. 2025 → วางตัวเป็นเครือข่ายจ่ายเงินข้ามพรมแดน 187+ ประเทศ โตเร็วมาก | ✅ Sacra |
| **Anthropic MCP/Connectors Directory** | 841 connector (ก.ค. 2026) นโยบาย **ไม่มีโฆษณา ไม่มีซื้อตำแหน่ง** — "Agentic Commerce" ยังเป็นทิศทางอนาคต **ยังไม่เปิด** | ✅ support.anthropic.com |
| **Claude Code marketplace** | 101 plugin (มี.ค. 2026) **ไม่มีระบบจ่ายเงินในตัว** | ⚠️ |
| **OpenAI Apps SDK / ChatGPT Apps** | เปิดแล้ว มี partner ใหญ่ (Canva, Figma, Spotify, Booking.com) — **monetization + directory + Agentic Commerce Protocol ประกาศแล้วแต่ยังทยอยปล่อย** ยังไม่ยืนยันว่า solo dev ใช้ได้เต็มที่ | ⚠️ openai.com/index/introducing-apps-in-chatgpt |
| **AI agent marketplace** | กระจัดกระจาย: enterprise (Salesforce AgentExchange, Google Agentspace, AWS/Azure) vs dev (Claude Skills, GPT Store, HuggingFace Spaces) rev share ทั่วไป 70-85% **ยังไม่มีเจ้าไหนชนะ** | ⚠️ |
| **Stripe Machine Payments Protocol** (มี.ค. 2026) + **x402** | โครงสร้างให้ AI agent จ่ายเงินกันเอง — ของจริงแต่ใหม่มาก | ✅ |
| **Apify** | จ่ายให้ dev รวม **$1M+/เดือน** (rev share 80%) — ช่องทาง monetize agent/scraper ที่พิสูจน์แล้วที่สุดตอนนี้ | ⚠️ |
| **MCPize** | rev share 85% | ⚠️ |
