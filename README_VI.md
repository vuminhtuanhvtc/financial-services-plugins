# 🇻🇳 Financial Services Plugins — Phiên bản Việt Nam hóa

> **Fork từ:** [anthropics/financial-services-plugins](https://github.com/anthropics/financial-services-plugins)
> **Bổ sung bởi:** Chuyên gia phân tích tài chính — tối ưu hóa cho thị trường Việt Nam

---

## Tại sao cần phiên bản này?

Bộ plugins gốc của Anthropic được thiết kế hoàn toàn cho **thị trường Mỹ** — từ nguồn dữ liệu (SEC EDGAR, Bloomberg, S&P), chuẩn kế toán (US GAAP), đến tham số định giá (US Treasury, S&P 500 beta, ERP 5.5%). Khi áp dụng trực tiếp vào phân tích doanh nghiệp Việt Nam, AI sẽ đưa ra kết quả **sai lệch nghiêm trọng** — ví dụ:

- **WACC sai:** Dùng US Treasury 4.25% thay vì TPCP Việt Nam, bỏ qua Country Risk Premium 2.5-3.5% → WACC thấp hơn thực tế 3-5%
- **Thuế sai:** Áp dụng thuế TNDN 21% (US) thay vì 20% (VN), không biết đến thuế ưu đãi KCN 10-17%
- **Nguồn dữ liệu không tồn tại:** Gọi SEC EDGAR, Bloomberg — trong khi BCTC Việt Nam công khai miễn phí trên HOSE/HNX/CafeF
- **Kế toán sai cấu trúc:** Nhầm "Lợi nhuận thuần từ HĐKD" (VAS) với EBIT (US GAAP) — trong khi VAS đã trừ chi phí tài chính

Phiên bản này **giữ nguyên 100% nội dung gốc** và **bổ sung thêm** các module Việt Nam, tự động kích hoạt khi AI nhận diện doanh nghiệp niêm yết trên HOSE/HNX/UPCOM.

---

## Những gì đã bổ sung

### 📁 Files mới (4 files)

#### 1. [`vietnam-data-sources.md`](financial-analysis/skills/references/vietnam-data-sources.md)

Hệ thống phân cấp nguồn dữ liệu **miễn phí** cho thị trường Việt Nam — thay thế hoàn toàn SEC EDGAR và Bloomberg:

| Tier | Nguồn | Nội dung |
|------|-------|---------|
| **Tier 1** | HOSE/HNX, CafeF, Vietstock, Simplize | BCTC chính thức, dữ liệu giao dịch, consensus |
| **Tier 2** | SSI, VNDirect, HSC, Vietcap Research | Báo cáo phân tích, target price, DCF assumptions |
| **Tier 3** | Web search, TradingView, GSO/SBV | Tin tức, dữ liệu macro, biểu đồ |

Bao gồm: URL chính xác cho từng nguồn, timeline công bố BCTC (so sánh US vs VN), và danh sách dữ liệu **không có miễn phí** tại VN (institutional ownership, short interest, options).

#### 2. [`vas-accounting.md`](financial-analysis/skills/references/vas-accounting.md)

Bảng mapping **VAS ↔ US GAAP** chi tiết cho 8 khác biệt trọng yếu, bao gồm:

- **Revenue recognition:** VAS ghi nhận tại thời điểm bàn giao (bất động sản) → doanh thu rất lumpy
- **Goodwill:** VAS phân bổ ≤10 năm (US impairment-only) → NI thấp hơn sau M&A
- **Operating leases:** VAS ngoại bảng (US ASC 842 on-balance sheet) → debt metrics có vẻ thấp hơn
- **⚠️ EBIT mapping:** "LN thuần từ HĐKD" trong VAS **≠ EBIT**. VAS đã trừ chi phí tài chính. Công thức đúng: `EBIT = LN thuần từ HĐKD + Chi phí lãi vay − Doanh thu tài chính`

Mapping tiếng Việt ↔ tiếng Anh cho toàn bộ dòng trên IS: từ "Doanh thu bán hàng và CCDV" đến "LNST", bao gồm cả "Doanh thu hoạt động tài chính" — khoản mục thường bị bỏ sót nhưng rất quan trọng đối với doanh nghiệp có lượng tiền gửi lớn.

#### 3. [`vietnam-tax-legal.md`](financial-analysis/skills/references/vietnam-tax-legal.md)

Tham chiếu thuế và pháp lý phục vụ xây dựng financial model:

- **CIT:** 20% chuẩn, 10-17% ưu đãi KCN, 32-50% khai khoáng
- **CGT cổ phiếu:** 0.1% trên **giá bán** (không phải trên lợi nhuận) — khác căn bản so với US
- **FOL:** 49% mặc định, 30% ngân hàng, 0% quốc phòng/truyền thông
- **QSDĐ:** Không có quyền sở hữu đất → QSDĐ 50-70 năm cần amortize trong model
- **BHXH:** Doanh nghiệp đóng 21.5% lương → ảnh hưởng trực tiếp OpEx projections
- **M&A:** Approval framework (Bộ Công Thương, SSC, SBV) theo loại hình giao dịch

#### 4. [`vietnam-sectors/SKILL.md`](financial-analysis/skills/vietnam-sectors/SKILL.md) — **SKILL MỚI**

Framework phân tích **6 ngành trọng điểm** tại Việt Nam với KPIs chuyên biệt, peer groups, và bối cảnh quy định:

| Ngành | KPIs đặc thù | Peers chính |
|-------|-------------|-------------|
| **Ngân hàng** | NIM, CIR, NPL, Cost of Risk, Provision Coverage, CASA, Credit Growth quota | VCB, TCB, MBB, ACB, VPB |
| **Bất động sản** | Landbank, Presale, Backlog, NAV/share | VHM, NVL, KDH, KBC |
| **Tiêu dùng/Bán lẻ** | Same-store growth, Revenue/store, Inventory days | MWG, FRT, VNM, SAB |
| **Tiện ích/Hạ tầng** | Capacity factor, ASP, RAB | GAS, POW, BMP, NTP |
| **Thép/Vật liệu** | Utilization, HRC-spread, Export ratio | HPG, HSG, NKG |
| **Công nghệ** | Revenue growth, Gross margin, R&D/Revenue | FPT, CMG, VNG |

Bao gồm: valuation benchmarks (P/E, P/B, EV/EBITDA) theo ngành, và phân tích cấu trúc sở hữu đặc thù Việt Nam (DNNN, family-controlled, cross-holdings, SOTP với minority interest).

---

### 📝 Files đã bổ sung nội dung (16 files across 5 plugins)

#### Financial Analysis (P0)

| # | File | Thay đổi |
|---|------|---------|
| 5 | [`comps-analysis/SKILL.md`](financial-analysis/skills/comps-analysis/SKILL.md) | VN Market Exception, peer scarcity guidance, P/B emphasis |
| 6 | [`dcf-model/SKILL.md`](financial-analysis/skills/dcf-model/SKILL.md) | VN WACC params, nominal/real terminal growth, VN validation |
| 7 | [`3-statements/SKILL.md`](financial-analysis/skills/3-statements/SKILL.md) | VAS adjustments, filing sources, BHXH in OpEx |
| 8 | [`competitive-analysis/SKILL.md`](financial-analysis/skills/competitive-analysis/SKILL.md) | VN source hierarchy, sector metrics, SOE flagging |
| 9 | [`lbo-model/SKILL.md`](financial-analysis/skills/lbo-model/SKILL.md) | Bank-centric debt, 20% CIT, leverage 3-4x max |

#### Investment Banking (P1)

| # | File | Thay đổi |
|---|------|---------|
| 10 | [`merger-model/SKILL.md`](investment-banking/skills/merger-model/SKILL.md) | Goodwill amortization VAS, LNST/CP, SSC/SBV approval |
| 11 | [`cim-builder/SKILL.md`](investment-banking/skills/cim-builder/SKILL.md) | QSDĐ section, VN market sizing (GSO/VCCI), BCTC reference |

#### Equity Research (P1)

| # | File | Thay đổi |
|---|------|---------|
| 12 | [`earnings-analysis/SKILL.md`](equity-research/skills/earnings-analysis/SKILL.md) | ĐHĐCĐ plan thay consensus, VN filing timing, LNST metrics |
| 13 | [`morning-note/SKILL.md`](equity-research/skills/morning-note/SKILL.md) | VN-Index, khối ngoại, ĐHĐCĐ catalysts, VN trading hours |

#### Private Equity (P2)

| # | File | Thay đổi |
|---|------|---------|
| 14 | [`deal-screening/SKILL.md`](private-equity/skills/deal-screening/SKILL.md) | VNĐ criteria, VN PE players, FOL check |
| 15 | [`dd-checklist/SKILL.md`](private-equity/skills/dd-checklist/SKILL.md) | QSDĐ, BHXH, EIA, tax compliance, labor code |
| 16 | [`ic-memo/SKILL.md`](private-equity/skills/ic-memo/SKILL.md) | Regulatory/FDI risk, governance upgrade, FX risk |
| 17 | [`returns-analysis/SKILL.md`](private-equity/skills/returns-analysis/SKILL.md) | CGT 0.1%, FX impact, VN IRR benchmarks |

#### Wealth Management (P2)

| # | File | Thay đổi |
|---|------|---------|
| 18 | [`financial-plan/SKILL.md`](wealth-management/skills/financial-plan/SKILL.md) | BHXH replaces Social Security, VN products, estate tax |
| 19 | [`tax-loss-harvesting/SKILL.md`](wealth-management/skills/tax-loss-harvesting/SKILL.md) | No wash sale rule, 0.1% CGT, limited ETF swaps |
| 20 | [`portfolio-rebalance/SKILL.md`](wealth-management/skills/portfolio-rebalance/SKILL.md) | VN asset classes, VN-Index benchmark, gold/deposits |

---

## Nguyên tắc bổ sung

> **Additive, not destructive.** Tất cả nội dung gốc cho thị trường US giữ nguyên 100%. Các section VN được thêm vào cuối mỗi skill file, tự động kích hoạt khi nhận diện context Việt Nam (ticker HOSE/HNX, currency VNĐ, hoặc user chỉ định).

---

## Cách sử dụng

Repository này hoạt động giống hệt bản gốc — chỉ cần clone và cấu hình theo hướng dẫn trong README gốc. Khi phân tích doanh nghiệp Việt Nam, AI sẽ tự động:

1. Chuyển sang nguồn dữ liệu VN (CafeF, Simplize, CTCK reports)
2. Áp dụng VAS accounting thay US GAAP
3. Dùng WACC parameters phù hợp VN (Rf, ERP, tax, terminal growth)
4. Reference KPIs ngành và peer groups VN
5. Xem xét thuế/pháp lý đặc thù (FOL, QSDĐ, BHXH, M&A regulations)

---

## Roadmap

- [x] **P0 — Financial Analysis Core:** Data sources, VAS, WACC, 3-statements, comps, DCF, sectors
- [x] **P1 — Investment Banking & Equity Research:** Merger model, CIM, earnings analysis, morning note, competitive analysis, LBO
- [x] **P2 — Private Equity & Wealth Management:** Deal screening, DD, IC memo, returns, financial plan, TLH, portfolio rebalance
- [ ] **P3 — Partner Plugins:** LSEG (VN RIC codes, IBES coverage), S&P Global (VN tear sheets)

---

## Credits

- **Bản gốc:** [Anthropic](https://github.com/anthropics/financial-services-plugins) — framework plugins cho Claude
- **Bổ sung VN:** Review và Việt Nam hóa toàn diện bởi chuyên gia phân tích tài chính — bao gồm expert review 11 điểm nghiệp vụ đã fix
